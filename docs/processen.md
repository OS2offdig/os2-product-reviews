---
title: Processen
layout: default
nav_order: 15
has_children: false
has_toc: false
---

# Introduktion til evalueringsprocessen

OS2 gennemfører evalueringer af alle produkter og projekter to gange årligt som en fast del af fællesskabets kvalitetssikring.

Processen tager afsæt i produktets egen selvevaluering og governancerapport, som opdateres løbende af produktorganisationen. På den baggrund gennemfører sekretariatet en samlet evaluering i dialog med produktet.

Evalueringen behandles i to spor. I produktets styregruppe med fokus på konkrete forbedringer, dokumentation og videre udvikling. Og i OS2’s bestyrelse med fokus på tværgående prioriteringer, produktniveau og fælles praksis.

Resultatet er både en status og et arbejdsgrundlag. Evalueringen peger på udviklingsområder i det enkelte produkt og kan samtidig føre til justeringer på tværs af porteføljen.

Processen gentages som en del af et fast årshjul, hvor opdateret selvevaluering er forudsætningen for næste evaluering. Over tid bør det opleves at arbejdet lettes i takt med, at produkter holder deres selvevaluering ajour og arbejder aktivt med OS2’s styringsmodel.

## Processen

```mermaid
flowchart TD

%% --- Styles ---
classDef start fill:#E5E5E5,stroke:#444,color:#111;
classDef eval fill:#FFF3C4,stroke:#D6A900,color:#333;

classDef board fill:#D7E8FF,stroke:#5A8FD8,color:#111;
classDef boardOut fill:#ABC9FF,stroke:#5A8FD8,color:#111;

classDef sg fill:#DFF4D8,stroke:#3FA34D,color:#111;
classDef sgOut fill:#B3E6A5,stroke:#3FA34D,color:#111;

classDef loop fill:#EFEFEF,stroke:#666,color:#111;
classDef invisible fill:none,stroke:none;

%% --- Top ---
A1[Projekt/produkt opdaterer<br/>selvevaluering og governancerapport]:::start
A2[Projekt/produkt afholder dialog<br/>med sekretariatet]:::start
B[Sekretariatet gennemfører evaluering<br/>ud fra opdateret selvevaluering]:::eval

A1 --> A2 --> B

%% --- Layout control ---
X(( )):::invisible
B --> X

%% --- Lanes ---
subgraph L[Styregruppespor]
direction TB
C1[Evaluering fremlægges<br/>for produktets styregruppe]:::sg
D1[Styregruppen giver feedback<br/>og peger på mangler]:::sg
E1[Sekretariatet samarbejder<br/>om forbedringer og årshjul]:::sg
F1[Opdateret dokumentation<br/>og governancerapport]:::sgOut
end

subgraph R[Bestyrelsesspor]
direction TB
C2[Evaluering fremlægges<br/>for OS2's bestyrelse]:::board
D2[Bestyrelsen vurderer<br/>generelle tiltag]:::board
E2[Sekretariatet leder<br/>tiltag fra bestyrelsen]:::board
F2[Opdateret produktniveau og<br/>praksis på fælles niveau]:::boardOut
end

%% --- Force layout ---
X --> C1
X --> C2

%% --- Flows ---
C1 --> D1 --> E1 --> F1
C2 --> D2 --> E2 --> F2

%% --- Cross-links ---
D1 <---> D2
E1 <---> E2

%% --- Loop ---
G[Årshjul udløser<br/>ny selvevaluering]:::loop

F1 --> G
F2 --> G
G --> A1
F1 --> A1
```