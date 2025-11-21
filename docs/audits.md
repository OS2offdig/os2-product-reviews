---
title: Evalueringer
layout: default
nav_order: 2
has_children: true
has_toc: false
---

# Evalueringsrapporter for OS2-produkter

OS2-sekretariatet er i gang med at udarbejde de første samlede evalueringer af produkter i porteføljen. Ikke alle produkter er vurderet endnu, og flere rapporter vil blive tilføjet løbende. Styregrupper og produktkoordinatorer vil også blive inddraget når rapporter er udarbejdet.

Bestyrelsen har igangsat arbejdet for at skabe et klart overblik over porteføljen og for at styrke den fælles professionalisering af OS2’s produkter. Evalueringerne giver et fælles grundlag for dialog, prioritering og videreudvikling i produktfællesskaberne.

Denne side opdateres, efterhånden som nye evalueringer bliver færdige.

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


%% --- Top: fælles start ---
A[Med afsæt i offentliggjort<br/>materiale og dokumentation]:::start
B[Sekretariatet gennemfører evaluering<br/>ud fra vurderingsgrundlaget]:::eval

A --> B

%% --- Lanes via subgraphs ---
subgraph L[Bestyrelsesspor]
direction TB
C1[Evaluering fremlægges<br/>for OS2's bestyrelse]:::board
D1[Bestyrelsen vurderer<br/>generelle tiltag]:::board
E1[Sekretariatet leder<br/>tiltag fra bestyrelsen]:::board
F1[Opdateret produktniveau og<br/>praksis på fælles niveau]:::boardOut
end

subgraph R[Styregruppespor]
direction TB
C2[Evaluering fremlægges<br/>for produktets styregruppe]:::sg
D2[Styregruppen giver feedback<br/>og peger på mangler]:::sg
E2[Sekretariatet samarbejder<br/>om forbedringer og årshjul]:::sg
F2[Opdateret dokumentation<br/>og governancerapport]:::sgOut
end

%% --- Flows for sporene ---
B --> C1
B --> C2

C1 --> D1
C2 --> D2

D1 --> E1
D2 --> E2

E1 --> F1
E2 --> F2

%% --- Cross-links ---
D1 <---> D2
E1 <---> E2

%% --- Bottom loop ---
G[Ny evaluering<br/>i årshjulet]:::loop

F1 --> G
F2 --> G
G --> B
F2 --> A
```

## Tilgængelige evalueringer

- [OS2-SkadesØkonomi](./docs/os2-skadesøkonomi_assessment)  
- [OS2autoproces](./docs/os2autoproces_assessment)  
- [OS2faktor](./docs/os2faktor_assessment)  
