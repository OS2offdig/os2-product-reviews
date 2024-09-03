# OS2Sofd findings

*Jeg har koncentreret mig om et enkelt repository i os2sofd organisationen på GitHub. Ved et hurtigt kig ned i repositoriet os2sofd er følgende fundet:*

#### os2sofd/os2sofd

Der anvendes ikke issues eller pull requests (PRs) på GitHub. Der er heller ikke i repoet et nemt tilgængeligt link til en alternativ issue-tracker. Produktets historiske udvikling og sammenhæng med kodeændringer er dermed ikke direkte transparent via os2sofd repositoriet. Der er ikke nogen beskrivelser af, hvordan man kan bidrage i form af en standard "CONTRIBUTING.MD" eller andet.

Der er heller ikke et "README.md" dokument i roden, der forklarer projektets formål, overordnede arkitektur eller en guide til at sætte et miljø op til udvikling eller test/demo.

os2sofd repositoriet består af primært af java kode der skal bygges med build toolet Maven, så man kan ikke bygge eksekverbare udgaver af kildekoden uden kendskab til Maven og java. Der bliver ikke bygget nemt genbrugelige container images af de forskellige komponenter og der er ikke nogen simpel "Getting Started" guide til hvordan man sætter et udviklingsmiljø op så man kan bidrage eller f.eks hvordan man spinner et test eller et produktionsmiljø op. Det kræver et forudgående kendskab til hvordan koden bygges med værktøjet Maven og hvordan man konfigurerer applikationen og afvikler den byggede kode. En guide eller forslag til dette placeret i repositoriet, vil have gjort det meget mere transparent hvordan kildekoden bygges og hvordan man kunne udrulle den i et udvikler/test eller demo miljø.

# Struktur

Der er ikke tydeligt dokumenteret hvad de forskellige undermapper med kildekode repræsenterer, men der er tre mapper, en "doc" en "UI" og en "webjar" mappe. Måske kan det findes ved at åbne de mange binære, properitært formatterede dokumenter en for en og søge dem igennem, men det er ikke direkte og tydeligt tilgængeligt i repositoriet. Så jeg har kigget lidt ind i mapperne og forsøgt at gennemskue dem.

#### doc

Indeholder en stor mængde properitære binære dokumentfiler, der ud fra titlen beskriver en masse integrationer. Formålet med at placere dem her er ikke kendt. Måske kan man læse disse statiske docs direkte inde fra applikationen?

#### UI

Ved et hurtigt gennemsyn indeholder denne mappe en del kildekode i java til en tætkoblet monolitisk applikation hvor forretningslogik, og frontend kode er placeret sammen. Mappenavnet kan måske forvirre lidt og der kunne med fordel laves ændringer i mappestruktur og navngivningerne for at øge transparensen.

Undermapperne indeholder en stor mængde javafiler og jeg har ikke ved et hurtigt gennemsyn kunne autoritativt relatere mappe eller filnavne til beskrivelserne af den overordnede system arkitektur der er beskrevet i nogle af de properitære, binære dokumentationsfiler. Dokumenterne er ikke direkte versions-styrbare p.g.a. deres binære natur, så jeg har ikke været 100% sikker på at jeg kiggede i de rette docs.  P.g.a. den ret uoroganiserede struktur i dokumentationen, vil det kræve noget gravearbejde, eller kontakt til Digital Identity for at kunne gennemskue disse koblinger og dermed kunne forstå kildekodens struktur og sammenhæng. Det er en stor ulempe for nytilkommere til repoet og er med til at gøre det unødigt tidskrævende at forstå koden eller bidrage til den. Jeg har læst et par enkelte af kodekommentarerne inline i selve kildekoden, men det var for omfattende at gennemlæse de mange filer for at få en forståelse. Som en anekdote kan jeg citere en enkelt kommentar: 

```text
// bit of a dirty hack to look at the first entry to decide the type for all of them
```

Når man falder over sådan en kommentar i et autoritativt system der kører i produktion ved mange af vores medlemmer, sætter det altid (måske unødige) bekymringer i gang og det burde nok professionaliseres lidt inden andre inviteres indenfor i kodebasen.

Det har dermed ikke været muligt inden for min tidsramme at vurdere om alt der skal til for at køre en os2sofdcore uden for DIs hosting, er til stede. Projeket mangler noget transparens for at dette vil være muligt uden mere dybdegående analyse eller dialog med leverandøren.

### webjar

En mappe der indeholder nogle dependencies (det ligner nogle frontend komponenter) der er pakket sammen som en binær .jar fil, bruges sandsynligvis når applikationen bygges med Maven værktøjet.

#### Releases

Releases leveres ikke med de tilgængelige GitHubs metoder. Der foretages manuelt meget store samlede kode-commits med nogle måneders mellemrum, hvor commit beskeden består af en tekststreng som f.eks ``` "release 2024 r2" ```

Der er ialt lavet 5 commits til os2sofd repoet siden starten:
https://github.com/OS2sofd/os2sofd/commits/main/

Det er tydeligt at softwaren udvikles, bygges og testes i et andet kildekode-repo end os2sofd GitHub repoet og så kommer der nogle større klumper kode til manuelt i ny og næ. Der er ikke opsat automatisering til at hjælpe med linting,scanning, security checks dependency updates eller lign. Løbende reviews foretaget af en en neutral 3. part, vurderes derfor at være så tidskrævende at det ikke vil være praktiskt muligt inden for et rimeligt drifts-budget.

# Konklusion

Der ligger en del javakode tilgænglig i os2sofd, men det er ikke transparent om alt koden er tilgængelig eller hvilket forhold den tilgængelige kode har til de kørende instanser anvenderne benytter til dagligt. Overenstemmelse med den overordnede arkitektur der er beskrevet i de binære dokumentationsfiler og den tilgængelige kildekode er heller ikke fuldt transparent eller nemt tilgængelig.

Umiddelbart vil jeg vurdere at os2sofdcore et endt med at være bundet til en enkelt leverandør, hvor produktet historisk altid har kørt og hvor den tekniske viden er forankret. Der har muligvis ikke været ønsker i produktet om at ændre på dette og det ser ikke ud til at der har været stillet arkitekturmæssige krav om at det skulle være nemt at komme i gang med at køre systemet på sin egen on-premise eller cloud infrastruktur. Der er indikationer på at det ikke har været prioritet at investere i et produkt der på lang sigt kunne tilbyde muligheder for vedligeholdelse eller udviddelse i et fler-leverandør samarbejde.

Os2sofdcore lader til at være billigest og nemmest at køre ved Digital Identity og bidrag fra andre leverandører for f.eks at øge interoperabiliteten vil kræve et tæt samarbejde med Digital Identity og en større dokumentations indsats. Indsatser der vil rejse risici for at opfyldelse af de forskellige Business Cases. Der er risiko for at arbejdet vil kræve så betragtelig en økonomisk investering, at det sandsynligvis ikke vil virke attraktivt for anvenderne, selvom det på den lange bane kunne være afgørende for et fremtidssikret produkt.

Hvis produktet ønsker at ændre på dette, kunne man lade en neutral 3.part udarbejde et ekstraordinært review der af- eller be-kræfter bekymringerne og lade 3.part, i dialog med leverandøren, udarbejde nogle anbefalinger der ville understøtte strategiske mål fra OS2 om øget Genbrugelighed, Løskoblethed og Dokumentationsgrad.
