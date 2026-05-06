---
title: OS2-test-assessment
layout: default
parent: Offentliggjorte selvevalueringer
---

# Governancerapport for OS2-test-selvevaluering

> **📄 Dokumentinformation** 
> **Version for anvendt governancerapport:** 1.1.0 
> **Dato for udfyldelse:** 2026-05-06 
> **Udfyldt af:** Rasmus Frey 
> **Link til Git organisation:** https://github.com/OS2offdig/os2-product-audits 

## RELEVANS

| # | Krav | Produktniveau | Retningslinjer | | --- | --------------------------------------------- | --------------| -------------- | | R1 | Løsningen skaber lokal værdi | sandkasse | Det er en løsning som hjælper OS2 med at evaluere produktniveau |
| R2 | Løsningen er accepteret af lokal linjeledelse | 2 | OS2 bestyrelse har bedt om og godkendt at alle produkter i OS2 skal foretage selvevaluering. |
| R3 | Løsningen har fælles offentligt potentiale | 2 | Løsningen anvendes bredt i OS2 og det data som løsningen generere er med til at hjælp kommuner og andre offentlig myndigheder i Deres vurdering af OS2-produkter. |
| R4 | Ophæng til nationale strategier er til stede | 3 | Det er et internt evalueringsværktøj og ikke umiddelbart relevant i henhold til nationale strategier. |

## FORMKRAV

| # | Krav | Produktniveau | Retningslinjer | | --- | --------------------------------------------- | --------------| -------------- | | F1 | Alt kildekode til projektet udvikles synligt og aktivt i et repositorie og versionskontrolsystem, anvist af OS2 | sandkasse | Løsningen udvikles, vedligeholdes og hostes i et OS2 repositorie på Github under organisationen OS2offdig. https://github.com/OS2offdig/os2-product-audits |
| F2 | Open Source licenskriterier overholdes | sandkasse | Der anvendes CC BY SA og MPL 2.0 |
| F3 | Udbudsregler og alm. lovformlighed er overholdt | sandkasse | Løsningen er egen udviklet. |
| F4 | Der er tænkt på sikkerheden i løsningen | sandkasse | Det er en simple løsning som ikke er kritisk og ikke giver adgang til andre systemer. Løsningen hostes på GitHub Pages and anvender GitHubs sikkerhedsmekanismer. |
| F5 | Løsningens formål og værdi er beskrevet | sandkasse | Er beskrevet i repo, https://github.com/OS2offdig/os2-product-audits |
| F6 | Kildekoden er overdraget og er placeret under OS2's kontrol | 1 | Kildekode forvaltes og udvikles af OS2-sekretariatet. Det foregår i følgende repo: https://github.com/OS2offdig/os2-product-audits |
| F7 | Alt dokumentation til projektet udarbejdes med og overholder OS2s standardskabelon for dokumentation. | 1 | Skabelonen anvendes en til en. |
| F10 | OS2's kommunikationskanaler anvendes (OS2.eu) | 1 | Værktøjes publiceres under OS2s governanceinformation of som et subdomæne til os2.eu. På audit.os2.eu. |
| F11 | Der anvendes offentlig issue-tracking anvist af OS2, hvor der tydeligt henvises til specifikke kodeændringer | 1 | Issue tracker er placeret i repo: https://github.com/OS2offdig/os2-product-audits |
| F12 | Der er kun en version af core koden | 2 | Der vedligeholdes og udvikles kun en version. |
| F13 | Der er udarbejdet præsentationsmateriale af løsningen | 2 | [Udfyldes i selvevaluering] |
| F14 | Der er udarbejdet kommunikationsmateriale til strategisk niveau | 2 | [Udfyldes i selvevaluering] |
| F15 | Best practice for implementering i organisationen dokumenteres | 2 | [Udfyldes i selvevaluering] |
| F16 | Teknisk dokumentation indeholder best practice for kodestandarder i forhold til de anvendte teknologier | 2 | [Udfyldes i selvevaluering] |
| F17 | Drifts og vedligeholdelses setup er beskrevet | 2 | [Udfyldes i selvevaluering] |
| F18 | Rammearkitekturen og standarder er fulgt og afvigelser er forklaret | 2 | [Udfyldes i selvevaluering] |
| F19 | Løsningen er leveret i et containerformat f.eks. docker (anbefaling) | 2 | [Udfyldes i selvevaluering] |
| F20 | Uddannelsesmateriale er udarbejdet (anbefaling) | 2 | [Udfyldes i selvevaluering] |
| F21 | Politisk kommunikation er udarbejdet (Lokal + Omverden) | 3 | [Udfyldes i selvevaluering] |
| F22 | Procesplan + procesansvar for driftsimplementering er udarbejdet | 3 | [Udfyldes i selvevaluering] |

## STRATEGISK SAMMENHÆNG

| # | Krav | Produktniveau | Retningslinjer | | --- | --------------------------------------------- | --------------| -------------- | | S1 | Produktet har en kobling til OS2's strategi | 1 | Der er en direkte kobling til OS2s strategiske indsatser. Særligt indsats 3 og 4 - https://www.os2.eu/os2s-vision-og-mission |
| S2 | Løsningen understøtter innovation og open source | 1 | Løsningen anvender open source teknologier |
| S3 | Produktets (forventlige) kobling til OS2's mission, vision og strategi er beskrevet | 2 | Løsningen understøtter direkte arbejdet med OS2s styringsmodel og indplacering af produkter på rette niveau. |
| S4 | Der er udarbejdet en vision og strategi for produktet | 2 | Visionen er at gøre det let for et OS2-produkt at vedligeholde sin egen evaluering i henhold til OS2s styringsmodel. Det er en målsætningen at løsningen skal udvikle sig til i høj grad at automatisere arbejdet med at udfærdige produktevalueringer. |
| S5 | Produktets kobling til og overensstemmelse med OS2's vision og strategi er tilstede og beskrevet | 3 | Løsningen er direkte koblet til OS2s formål og bygger på OS2s værdier og vision om at styrke digitaliseringen i Danmark. |

## GOVERNANCE

| # | Krav | Produktniveau | Retningslinjer | | --- | --------------------------------------------- | --------------| -------------- | | G1 | Produktet er oprettet i OS2's porteføljestyring | 1 | Løsningen er en del at OS2s værktøjskasse og er tilgængelig via OS2s github og dermed også hjemmeside. |
| G2 | Der koordineres løbende med OS2-sekretariatet | 1 | Sekretariatet ejer og drive løsningen. |
| G3 | Der er udpeget en projektleder/tovholder | 1 | Sekretariatschefen er produktejer. |
| G4 | Bestyrelsen er orienteret | 1 | Løsningen er et resultat af en bestyrelsesbeslutning. |
| G5 | Bestyrelsen har godkendt produktet | 2 | Løsningen er ikke formelt præsenteret og godkendt. |
| G6 | Der er nedsat en styregruppe | 2 | Projektet referere til OS2s bestyrelse. |
| G7 | Der er nedsat en koordinationsgruppe (anbefaling) | 2 | [Udfyldes i selvevaluering] |
| G8 | En projektmodel anvendes og er dokumenteret (anbefaling) | 2 | Continuous development and deployment. |
| G9 | Review af kode foretages af tredjepart (anbefaling) | 2 | [Udfyldes i selvevaluering] |
| G10 | Der er udarbejdet en tilslutningserklæring til sikring af økonomi (anbefaling) | 2 | Udgifter dækkes via OS2s centrale budget. |
| G11 | Bestyrelsen har godkendt styregruppen | 3 | Det er en kerneopgave for OS2-sekretariatet at porteføljestyre. Betyrelsen har til januar seminar i 2026 besluttet at produkter skal selvevaluere. Heri ligger beslutningen om Audit værktøj. |
| G12 | Bestyrelsen er repræsenteret i styregruppen | 3 | Bestyrelsen udgør styregruppen. |
| G13 | Der foreligger en aftale der sikrer økonomi til koordinering og videreudvikling | 3 | Dækkes af OS2s budget. |
| G14 | Der er etableret et fagligt fællesskab bag løsningen hvor erfaringer kan udveksles | 3 | [Udfyldes i selvevaluering] |