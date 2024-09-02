# os2mo quick-glance

*Organisationen består af mange repositorier, nogle lader til at være integrationer, andre tilknyttede værktøjer.  Det er ikke afdækket i dette arbejde hvordan os2mo/os2mo forholder sig til det leverandør ejede repositorie https://github.com/magenta-aps/os2mo, der umiddelbart ikke ligner en fork. Jeg er i dette abejde primlært dykket ned i hovedrepositoriet os2mo for at gøre det sammenligneligt med quick-glance arbejdet på os2sofd*

os2mo Projektet har en README i roden af repositoriet der kort beskriver et formål. Man kan diskutere om ordlyden er lidt indforstået og om det er med til at skabe klarhed for nye interesserede parter, men den er dog til stedet. Der er i README linket til et dokumentations site hosted ved Magenta med det lidt pudsige navn https://rammearkitektur.docs.magenta.dk/os2mo

Sitet indeholder en blanding af anvender vendt manual, samt en hel del teknisk dokumentation og udrulnings beskrivelser. Denne dokumentation er omfattende i omfang og det er derfor uden for scope for et quick-glance at gennemlæse den fra ende til anden.

## docs

Dokumenterne der udgør docs ligger ikke i et selvstændigt repositorie men er placeret i docs/src mappen inde i os2mo repositoriet og benytter ved et hurtigt overblik primært Markdown

Dokumentationen kan bygges, men det er ikke uddybende dokumenteret og kræver viden om Sphinx og byggeprocesser. Jeg formoder dette køres automatiskt i Magentas infrastruktur, der linkes ud til teknisk dokumentation for Sphinx, hvis man har evnerne til at bygge docs selv.

Det er ikke ved første øjekast tydeligt i selve repoet, hvordan den officielle metode til at rulle en udviklings, test eller demo miljø op foretages. Jeg har kunnet grave et par meget tekniske READMEs frem fra nogle undermapper, der godt kunne være mere klare og inviterende for tilkommende bidragydere. Hvis man leder lidt kan dette kan findes beskrevet i en undersektion af den tekniske dokumentation i den Magenta hostede doc-server rammearkitektur.docs.magenta.dk/os2mo, ved at søge eller klikke sig frem til det... Der kunne godt ønskes nogle eksempler eller skabeloner til dette i selve repositoriet, men det er dog tilgængligt hvis man leder.

I en sektion af docs kan findes en guide til at afvikle os2mo i Cloud på Microsoft Azure med AKS og en række Azure properitære maneged services. Dette er ikke en generel guide til at køre på en Kubernetes Cluster, men det noteres at der findes et selvstændigt repo der hedder "os2mo-helm-chart" som ved kort gennemsyn indeholder nogle filer til at udrulle på en K8s. Det er ikke klart om det er Magentas eget Saas setup der er målet for dette og linket fra README til en "Getting Started guide" er ummidddelabrt et dødt link. Jeg kunne dog grave den frem ved manuelt at finde den i undermappen docs, måske er dette bare ikke vedligeholdt. Men der findes altså en beskrivelse til en manuel cluster deployment. Der kommer ikke nogle hits på søgning efter "Helm"  i den officielle dokumentation, så der mangler lidt sammenhænge, men alle byggestenene er nok til stede hvis man dykker lidt mere ned i det. Der er yderligere et par repositories der beskriver en terraform-provider og et sæt container image repos, det er dog meget uklart, om og isåfald hvor disse passer ind i implementering af os2mo og flere er ikke opdateret for nyligt. Det er ikke inden for scope at dykke ned i disse, men måske ville en oprydning eller nogle klarere formåls bekrivelser være med til at os2mo fremstår mere sammenhængende, tilgængelig og transparent for udefrakommende.

Der nævnes at os2mo kan udrulles på en VM On-Prem med værktøjet SALT, men jeg kunne ikke umiddelbart finde uddybet hvordan eller finde links til scripts eller lign. Midt i on-prem guiden forklares  *"Vi vil kraftigt anbefale at Magenta hoster OS2mo."* Denne metode tyder på en hård binding til den enkelte leverandør.

Den nemmeste måde at sætte en instans op, til test, demo eller til produktion, virker ved et hurtigt gennemsyn til at være ved at tage kontakt til den eksisterende udviklings-leverandør og lade dem stå for dette, eller købe løsningen som SaaS i Magentas Microsoft Azure instans.

Der er ikke umiddelbart en CONTRIBUTING.md fil tilgængelig og søgning på "contrib, contributing" etc. i docs giver et enkelt hit til en tekniske dokumentation omkring oprulning med docker-compose.. 


## Offentlig Issue-tracker

Projektet indeholder flere feature branches der følger standard flowet med at merge via Pull Requests. Issue-trackeren i repositoriet benyttes dog ikke og der linkes istedet til enten en lukket projektstyring (redmine) ved Magenta eller en lukket instans af GitLab Enterprise ejet af Magenta, så det er ikke umiddelbart transparent hvilken forretningsværdi eller brugerhistorier de enkelte PRs bidrager til og det lader ikke til at der er direkte i repoet er en tilgænglig historik over ændringer og hvilke valg der er taget løbende. Der er adgang til en Changelog på den Magenta hostede rammearkitektur side, og der er spor af ældre statiske changelogs rundtom i docs mappen, som man vil kunne stykke dette sammen af, så længe magenta hoster denne side. Det er sikkert muligt at kunne tilgå en historik f.eks ved at få et login til Magentas systemer og denne måde fungerer uden tvivl fint i hverdagen for Magentas kunder. Metoden bidrager dog ikke til en større tilgængelighed og transparens og sætter baren lidt højere for at kunne evaluere og deltage som bidrag-yder eller for at kunne udvidde med flere leverandører som samarbejdspartnere på produktet både som udviklings eller driftsleverandører.

## Releases

Der bygges ikke standard OCI container images direkte i repo med githubs Actions CI og der releases ikke færdigpakkede container images på packages.github.com. Der forefindes en dockerfil, så dettte ville være muligt at udføre manuelt eller tilpasse den til eget CI system. Dykker man ned i en af kilde-filerne til container deployment, kan man udlede at der foregår byg og push af containerimages til magentas organisation på Docker-Hub. Så de er tilgængelige derffra, men altså styret og underlagt leverandørens kontrol.

Releases består af simple pakkede filtræer der svarer til repo strukturen på tidspunktet for tagget.

## Afslutning

Os2mo virker som et komplekst produkt i transisition med en del ældre arbejde og noget nyere arbejde. Der kunne med fordel kunne prioteres midler til at ensarte, beskrive og simplificere tilgængelighed for at øge transparensen og dermed samarbejds potentialet.
