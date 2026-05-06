---
title: OS2-test-assessment
layout: default
parent: Selvevalueringer
---

# Governancerapport for OS2-test-selvevaluering

> **📄 Dokumentinformation**<br/>
> **Version for anvendt governancerapport:** 1.1.0<br/>
> **Dato for udfyldelse:** 06-05-2026<br/>
> **Udfyldt af:** Rasmus Frey, OS2-sekretariatet<br/>
> **Link til Git organisation:** [indsæt link til git organisation/repo]<br/>

## RELEVANS

| # | Krav | Produktniveau | Retningslinjer | Efterlevet? | Dokumentation |
| --- | --------------------------------------------- | ------------- | -------------- | ----------- | ------------- |
| R1 | Løsningen skaber lokal værdi | sandkasse | Beskriv den konkrete værdi løsningen skaber i organisationen. F.eks. økonomisk, organisatorisk eller brugerrelateret. | Ja | Det er en løsning som hjælper OS2 med at evaluere produktniveau |
| R2 | Løsningen er accepteret af lokal linjeledelse | 2 | Beskriv eller henvis til en formel accept fra ledelse hos initiativtagerne til løsningen. | Ja | OS2 bestyrelse har bedt om og godkendt at alle produkter i OS2 skal foretage selvevaluering. |
| R3 | Løsningen har fælles offentligt potentiale | 2 | Redegør for hvordan løsningen kan bruges på tværs af kommuner og/eller offentlige myndigheder. | Ja | Løsningen anvendes bredt i OS2 og det data som løsningen generere er med til at hjælp kommuner og andre offentlig myndigheder i Deres vurdering af OS2-produkter. |
| R4 | Ophæng til nationale strategier er til stede | 3 | Henvis til relevante strategier og forklar hvordan løsningen understøtter disse. | Ikke relevant | Det er et internt evalueringsværktøj og ikke umiddelbart relevant i henhold til nationale strategier. |

## FORMKRAV

| # | Krav | Produktniveau | Retningslinjer | Efterlevet? | Dokumentation |
| --- | --------------------------------------------- | ------------- | -------------- | ----------- | ------------- |
| F1 | Alt kildekode til projektet udvikles synligt og aktivt i et repositorie og versionskontrolsystem, anvist af OS2 | sandkasse | Upload al kildekode i et offentligt OS2 repository med aktiv versionshistorik. | Ja | Løsningen udvikles, vedligeholdes og hostes i et OS2 repositorie på Github under organisationen OS2offdig. https://github.com/OS2offdig/os2-product-audits |
| F2 | Open Source licenskriterier overholdes | sandkasse | Angiv hvilken OSI-godkendt licens projektet bruger. OS2 standard er MPL 2.0 | Ja | Der anvendes CC BY SA og MPL 2.0 |
| F3 | Udbudsregler og alm. lovformlighed er overholdt | sandkasse | Bekræft at udbudspligt er overholdt eller redegør for undtagelse. Vedlæg evt. beslutningsnotat. | Ja | Løsningen er egen udviklet. |
| F4 | Der er tænkt på sikkerheden i løsningen | sandkasse | Beskriv hvordan sikkerhed er indtænkt i design, kode og drift – f.eks. kryptering, adgangsstyring. | Ja | Det er en simple løsning som ikke er kritisk og ikke giver adgang til andre systemer. Løsningen hostes på GitHub Pages and anvender GitHubs sikkerhedsmekanismer. |
| F5 | Løsningens formål og værdi er beskrevet | sandkasse | Henvis til dokumentation (f.eks. README) hvor formål og målgruppe fremgår. | Ja | Er beskrevet i repo, https://github.com/OS2offdig/os2-product-audits |
| F6 | Kildekoden er overdraget og er placeret under OS2's kontrol | 1 | Bekræft og link til det officielle repository i OS2s versionskontrol. | Ja | Kildekode forvaltes og udvikles af OS2-sekretariatet. Det foregår i følgende repo: https://github.com/OS2offdig/os2-product-audits |
| F7 | Alt dokumentation til projektet udarbejdes med og overholder OS2s standardskabelon for dokumentation. | 1 | Brug OS2’s standard template til dokumentation. [Documentation template for OS2 projects](http://github.com/OS2offdig/os2-docs-template) | Ja | Skabelonen anvendes en til en. |
| F10 | OS2's kommunikationskanaler anvendes (OS2.eu) | 1 | Bekræft og link til omtale på f.eks. os2.eu, nyhedsbrev eller andet. | Ja | Værktøjes publiceres under OS2s governanceinformation of som et subdomæne til os2.eu. På audit.os2.eu. |
| F11 | Der anvendes offentlig issue-tracking anvist af OS2, hvor der tydeligt henvises til specifikke kodeændringer | 1 | Henvis til f.eks. Issues, hvor opgaver er koblet til pull-requests/commits. | Ja | Issue tracker er placeret i repo: https://github.com/OS2offdig/os2-product-audits |
| F12 | Der er kun en version af core koden | 2 | Bekræft at der kun findes én ‘main’ version og at den er aktivt vedligeholdt. | Ja | Der vedligeholdes og udvikles kun en version. |
| F13 | Der er udarbejdet præsentationsmateriale af løsningen | 2 | Link til f.eks. slides, brochurer eller andet introduktionsmateriale. | Nej | [Udfyldes i selvevaluering] |
| F14 | Der er udarbejdet kommunikationsmateriale til strategisk niveau | 2 | F.eks. businesscase, one-pager til direktionsniveau og præsentation til udvalg. | Nej | [Udfyldes i selvevaluering] |
| F15 | Best practice for implementering i organisationen dokumenteres | 2 | Angiv implementeringsvejledning, erfaringsopsamling eller cases. | Nej | [Udfyldes i selvevaluering] |
| F16 | Teknisk dokumentation indeholder best practice for kodestandarder i forhold til de anvendte teknologier | 2 | Beskriv Hvilke kodestandarder projektet følger. Evt. med links til eksterne guides og supplerende retningslinjer. | Nej | [Udfyldes i selvevaluering] |
| F17 | Drifts og vedligeholdelses setup er beskrevet | 2 | Redegør for driftspartner(e), ansvar og finansiering. Hvem drifter, hvem vedligeholder og hvem koordinere. Beskriv også Hvordan kører løsningen? (on-prem, cloud, container, SaaS). Hvilke komponenter indgår? (fx databaser, API’er, microservices). Hvilke værktøjer bruges til monitorering, deployment og backup. | Nej | [Udfyldes i selvevaluering] |
| F18 | Rammearkitekturen og standarder er fulgt og afvigelser er forklaret | 2 | Beskriv om/hvordan løsningen følger fællesoffentlig rammearkitektur – eller forklar hvorfor ikke. | Nej | [Udfyldes i selvevaluering] |
| F19 | Løsningen er leveret i et containerformat f.eks. docker (anbefaling) | 2 | Angiv om løsningen tilbydes i en containeriseret version som definerer hvordan applikationen bygges og køres. | Nej | [Udfyldes i selvevaluering] |
| F20 | Uddannelsesmateriale er udarbejdet (anbefaling) | 2 | Henvis til manual, brugervejledning eller andet brugerrelateret materiale. | Nej | [Udfyldes i selvevaluering] |
| F21 | Politisk kommunikation er udarbejdet (Lokal + Omverden) | 3 | Angiv indhold der kan bruges i politiske fora – f.eks. beslutningsoplæg eller pressemeddelelse. | Ikke relevant | [Udfyldes i selvevaluering] |
| F22 | Procesplan + procesansvar for driftsimplementering er udarbejdet | 3 | Tilføj en implementeringsplan med ‘hvem gør hvad hvornår’. | Ikke relevant | [Udfyldes i selvevaluering] |

## STRATEGISK SAMMENHÆNG

| # | Krav | Produktniveau | Retningslinjer | Efterlevet? | Dokumentation |
| --- | --------------------------------------------- | ------------- | -------------- | ----------- | ------------- |
| S1 | Produktet har en kobling til OS2's strategi | 1 | Beskriv hvordan produktet understøtter tværoffentlige behov, deling og fællesskab. | Ja | Der er en direkte kobling til OS2s strategiske indsatser. Særligt indsats 3 og 4 - https://www.os2.eu/os2s-vision-og-mission |
| S2 | Løsningen understøtter innovation og open source | 1 | Angiv hvordan open source-værdier og nyskabelse er tænkt ind. | Ja | Løsningen anvender open source teknologier |
| S3 | Produktets (forventlige) kobling til OS2's mission, vision og strategi er beskrevet | 2 | Angiv hvor produktet matcher med OS2's formål og indsatser. | Ja | Løsningen understøtter direkte arbejdet med OS2s styringsmodel og indplacering af produkter på rette niveau. |
| S4 | Der er udarbejdet en vision og strategi for produktet | 2 | Beskriv produktvision og strategiske mål. | Ja | Visionen er at gøre det let for et OS2-produkt at vedligeholde sin egen evaluering i henhold til OS2s styringsmodel. Det er en målsætningen at løsningen skal udvikle sig til i høj grad at automatisere arbejdet med at udfærdige produktevalueringer. |
| S5 | Produktets kobling til og overensstemmelse med OS2's vision og strategi er tilstede og beskrevet | 3 | Forklar hvordan løsningen passer ind i OS2’s overordnede værdisæt og visioner. | Ja | Løsningen er direkte koblet til OS2s formål og bygger på OS2s værdier og vision om at styrke digitaliseringen i Danmark. |

## GOVERNANCE

| # | Krav | Produktniveau | Retningslinjer | Efterlevet? | Dokumentation |
| --- | --------------------------------------------- | ------------- | -------------- | ----------- | ------------- |
 | G1 | Produktet er oprettet i OS2's porteføljestyring | 1 | Produktet er oprettet på OS2s hjemmeside og indgår i årshjul. Dette koordineres med sekretariatet i OS2. | Ja | Løsningen er en del at OS2s værktøjskasse og er tilgængelig via OS2s github og dermed også hjemmeside. |
| G2 | Der koordineres løbende med OS2-sekretariatet | 1 | Bekræft, evt. med årshjul/datoer/mails for koordinering. | Ja | Sekretariatet ejer og drive løsningen. |
| G3 | Der er udpeget en projektleder/tovholder | 1 | Navngiv og beskriv rolle og opgaver. | Ja | Sekretariatschefen er produktejer. |
| G4 | Bestyrelsen er orienteret | 1 | Vedlæg dokumentation for orientering. | Ja | Løsningen er et resultat af en bestyrelsesbeslutning. |
| G5 | Bestyrelsen har godkendt produktet | 2 | Vedlæg dokumentation for godkendelse. | Nej | Løsningen er ikke formelt præsenteret og godkendt. |
| G6 | Der er nedsat en styregruppe | 2 | Beskrivelse af styregruppen og roller/ansvar/opgaver. | Ja | Projektet referere til OS2s bestyrelse. |
| G7 | Der er nedsat en koordinationsgruppe (anbefaling) | 2 | Beskrivelse af koordinationsgruppen og roller/ansvar/opgaver. | Ja | [Udfyldes i selvevaluering] |
| G8 | En projektmodel anvendes og er dokumenteret (anbefaling) | 2 | Beskiv den anvendte projektmodel eller metode. | Ja | Continuous development and deployment. |
| G9 | Review af kode foretages af tredjepart (anbefaling) | 2 | Angiv hvilken ekstern part som udfører eller har udført review. Link til processbeskrivelse samt revisionsrapporter. | Nej | [Udfyldes i selvevaluering] |
| G10 | Der er udarbejdet en tilslutningserklæring til sikring af økonomi (anbefaling) | 2 | Vedlæg eller henvis til dokument for tilslutning og økonomi. | Ja | Udgifter dækkes via OS2s centrale budget. |
| G11 | Bestyrelsen har godkendt styregruppen | 3 | Vedlæg dokumentation for beslutning. | Ja | Det er en kerneopgave for OS2-sekretariatet at porteføljestyre. Betyrelsen har til januar seminar i 2026 besluttet at produkter skal selvevaluere. Heri ligger beslutningen om Audit værktøj. |
| G12 | Bestyrelsen er repræsenteret i styregruppen | 3 | Angiv hvilket medlem som deltager på vegne af bestyrelsen. | Ja | Bestyrelsen udgør styregruppen. |
| G13 | Der foreligger en aftale der sikrer økonomi til koordinering og videreudvikling | 3 | Vedlæg eller beskriv finansieringsaftalen. | Ja | Dækkes af OS2s budget. |
| G14 | Der er etableret et fagligt fællesskab bag løsningen hvor erfaringer kan udveksles | 3 | Henvis til brugerforum og/eller årshjul for aktiviteter. | Ikke relevant | [Udfyldes i selvevaluering] |