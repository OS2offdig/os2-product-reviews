---
title: OS2 governancerapport (generator)
layout: default
parent: Evalueringer
nav_order: 3
has_children: false
has_toc: false
---

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">

<div id="app" class="container-fluid my-4 px-3 px-md-4"></div>

<script>
const REQUIREMENTS = [
  ["relevans","R1","Løsningen skaber lokal værdi","sandkasse","Beskriv den konkrete værdi løsningen skaber i organisationen. F.eks. økonomisk, organisatorisk eller brugerrelateret."],
  ["relevans","R2","Løsningen er accepteret af lokal linjeledelse","2","Beskriv eller henvis til en formel accept fra ledelse hos initiativtagerne til løsningen."],
  ["relevans","R3","Løsningen har fælles offentligt potentiale","2","Redegør for hvordan løsningen kan bruges på tværs af kommuner og/eller offentlige myndigheder."],
  ["relevans","R4","Ophæng til nationale strategier er til stede","3","Henvis til relevante strategier og forklar hvordan løsningen understøtter disse."],

  ["formkrav","F1","Alt kildekode til projektet udvikles synligt og aktivt i et repositorie og versionskontrolsystem, anvist af OS2","sandkasse","Upload al kildekode i et offentligt OS2 repository med aktiv versionshistorik."],
  ["formkrav","F2","Open Source licenskriterier overholdes","sandkasse","Angiv hvilken OSI-godkendt licens projektet bruger. OS2 standard er MPL 2.0"],
  ["formkrav","F3","Udbudsregler og alm. lovformlighed er overholdt","sandkasse","Bekræft at udbudspligt er overholdt eller redegør for undtagelse. Vedlæg evt. beslutningsnotat."],
  ["formkrav","F4","Der er tænkt på sikkerheden i løsningen","sandkasse","Beskriv hvordan sikkerhed er indtænkt i design, kode og drift – f.eks. kryptering, adgangsstyring."],
  ["formkrav","F5","Løsningens formål og værdi er beskrevet","sandkasse","Henvis til dokumentation (f.eks. README) hvor formål og målgruppe fremgår."],
  ["formkrav","F6","Kildekoden er overdraget og er placeret under OS2's kontrol","1","Bekræft og link til det officielle repository i OS2s versionskontrol."],
  ["formkrav","F7","Alt dokumentation til projektet udarbejdes med og overholder OS2s standardskabelon for dokumentation.","1","Brug OS2’s standard template til dokumentation. [Documentation template for OS2 projects](http://github.com/OS2offdig/os2-docs-template)"],
  ["formkrav","F10","OS2's kommunikationskanaler anvendes (OS2.eu)","1","Bekræft og link til omtale på f.eks. os2.eu, nyhedsbrev eller andet."],
  ["formkrav","F11","Der anvendes offentlig issue-tracking anvist af OS2, hvor der tydeligt henvises til specifikke kodeændringer","1","Henvis til f.eks. Issues, hvor opgaver er koblet til pull-requests/commits."],
  ["formkrav","F12","Der er kun en version af core koden","2","Bekræft at der kun findes én ‘main’ version og at den er aktivt vedligeholdt."],
  ["formkrav","F13","Der er udarbejdet præsentationsmateriale af løsningen","2","Link til f.eks. slides, brochurer eller andet introduktionsmateriale."],
  ["formkrav","F14","Der er udarbejdet kommunikationsmateriale til strategisk niveau","2","F.eks. businesscase, one-pager til direktionsniveau og præsentation til udvalg."],
  ["formkrav","F15","Best practice for implementering i organisationen dokumenteres","2","Angiv implementeringsvejledning, erfaringsopsamling eller cases."],
  ["formkrav","F16","Teknisk dokumentation indeholder best practice for kodestandarder i forhold til de anvendte teknologier","2","Beskriv Hvilke kodestandarder projektet følger. Evt. med links til eksterne guides og supplerende retningslinjer."],
  ["formkrav","F17","Drifts og vedligeholdelses setup er beskrevet","2","Redegør for driftspartner(e), ansvar og finansiering. Hvem drifter, hvem vedligeholder og hvem koordinere. Beskriv også Hvordan kører løsningen? (on-prem, cloud, container, SaaS). Hvilke komponenter indgår? (fx databaser, API’er, microservices). Hvilke værktøjer bruges til monitorering, deployment og backup."],
  ["formkrav","F18","Rammearkitekturen og standarder er fulgt og afvigelser er forklaret","2","Beskriv om/hvordan løsningen følger fællesoffentlig rammearkitektur – eller forklar hvorfor ikke."],
  ["formkrav","F19","Løsningen er leveret i et containerformat f.eks. docker (anbefaling)","2","Angiv om løsningen tilbydes i en containeriseret version som definerer hvordan applikationen bygges og køres."],
  ["formkrav","F20","Uddannelsesmateriale er udarbejdet (anbefaling)","2","Henvis til manual, brugervejledning eller andet brugerrelateret materiale."],
  ["formkrav","F21","Politisk kommunikation er udarbejdet (Lokal + Omverden)","3","Angiv indhold der kan bruges i politiske fora – f.eks. beslutningsoplæg eller pressemeddelelse."],
  ["formkrav","F22","Procesplan + procesansvar for driftsimplementering er udarbejdet","3","Tilføj en implementeringsplan med ‘hvem gør hvad hvornår’."],

  ["strategisk","S1","Produktet har en kobling til OS2's strategi","1","Beskriv hvordan produktet understøtter tværoffentlige behov, deling og fællesskab."],
  ["strategisk","S2","Løsningen understøtter innovation og open source","1","Angiv hvordan open source-værdier og nyskabelse er tænkt ind."],
  ["strategisk","S3","Produktets (forventlige) kobling til OS2's mission, vision og strategi er beskrevet","2","Angiv hvor produktet matcher med OS2's formål og indsatser."],
  ["strategisk","S4","Der er udarbejdet en vision og strategi for produktet","2","Beskriv produktvision og strategiske mål."],
  ["strategisk","S5","Produktets kobling til og overensstemmelse med OS2's vision og strategi er tilstede og beskrevet","3","Forklar hvordan løsningen passer ind i OS2’s overordnede værdisæt og visioner."],

  ["governance","G1","Produktet er oprettet i OS2's porteføljestyring","1","Produktet er oprettet på OS2s hjemmeside og indgår i årshjul. Dette koordineres med sekretariatet i OS2."],
  ["governance","G2","Der koordineres løbende med OS2-sekretariatet","1","Bekræft, evt. med årshjul/datoer/mails for koordinering."],
  ["governance","G3","Der er udpeget en projektleder/tovholder","1","Navngiv og beskriv rolle og opgaver."],
  ["governance","G4","Bestyrelsen er orienteret","1","Vedlæg dokumentation for orientering."],
  ["governance","G5","Bestyrelsen har godkendt produktet","2","Vedlæg dokumentation for godkendelse."],
  ["governance","G6","Der er nedsat en styregruppe","2","Beskrivelse af styregruppen og roller/ansvar/opgaver."],
  ["governance","G7","Der er nedsat en koordinationsgruppe (anbefaling)","2","Beskrivelse af koordinationsgruppen og roller/ansvar/opgaver."],
  ["governance","G8","En projektmodel anvendes og er dokumenteret (anbefaling)","2","Beskiv den anvendte projektmodel eller metode."],
  ["governance","G9","Review af kode foretages af tredjepart (anbefaling)","2","Angiv hvilken ekstern part som udfører eller har udført review. Link til processbeskrivelse samt revisionsrapporter."],
  ["governance","G10","Der er udarbejdet en tilslutningserklæring til sikring af økonomi (anbefaling)","2","Vedlæg eller henvis til dokument for tilslutning og økonomi."],
  ["governance","G11","Bestyrelsen har godkendt styregruppen","3","Vedlæg dokumentation for beslutning."],
  ["governance","G12","Bestyrelsen er repræsenteret i styregruppen","3","Angiv hvilket medlem som deltager på vegne af bestyrelsen."],
  ["governance","G13","Der foreligger en aftale der sikrer økonomi til koordinering og videreudvikling","3","Vedlæg eller beskriv finansieringsaftalen."],
  ["governance","G14","Der er etableret et fagligt fællesskab bag løsningen hvor erfaringer kan udveksles","3","Henvis til brugerforum og/eller årshjul for aktiviteter."]
];

const THEMES = ["relevans","formkrav","strategisk","governance"];
const THEME_LABELS = { relevans: "RELEVANS", formkrav: "FORMKRAV", strategisk: "STRATEGISK SAMMENHÆNG", governance: "GOVERNANCE" };

function esc(s){ return String(s || "").replace(/\|/g, "\\|").replace(/\n/g, "<br/>"); }

function render() {
  document.getElementById("app").innerHTML = `
    <h1>OS2 governancerapport generator</h1>
    <blockquote class="note-title">
      <p>Denne formular anvendes til at generere en governancerapport baseret på data fra en selvevaluering.</p>
      <p>Upload JSON fra selvevaluering og generér en udfyldt rapport i Markdown-format.</p>
    </blockquote>
    <div class="row g-3 mb-3">
      <div class="col-12 col-md-4"><label class="form-label">JSON-fil</label><input id="jsonFile" class="form-control" type="file" accept=".json,application/json"></div>
      <div class="col-12 col-md-4"><label class="form-label">Udfyldt af</label><input id="filledBy" class="form-control" placeholder="Navn"></div>
      <div class="col-12 col-md-4"><label class="form-label">Git organisation/repo</label><input id="githubLink" class="form-control" placeholder="https://github.com/..." ></div>
      <div class="col-12 col-md-4"><label class="form-label">Dato for udfyldelse</label><input id="reportDate" class="form-control" type="date"></div>
    </div>
    <div class="d-flex gap-2 mb-3">
      <button id="generate" class="btn btn-primary" type="button">Generér rapport</button>
      <button id="download" class="btn btn-outline-secondary" type="button">Download .md</button>
    </div>
    <label class="form-label">Genereret markdown</label>
    <textarea id="output" class="form-control" rows="22"></textarea>
  `;

  document.getElementById("generate").onclick = generate;
  document.getElementById("download").onclick = download;
}

let lastMarkdown = "";

async function generate() {
  const f = document.getElementById("jsonFile").files[0];
  if (!f) return alert("Vælg først en JSON-fil.");
  const data = JSON.parse(await f.text());
  const byId = new Map((data.krav || []).map(k => [k.id, k]));

  const tableBlocks = {};
  THEMES.forEach(theme => {
    const rows = REQUIREMENTS.filter(r => r[0] === theme).map(([_, id, req, level, guideline]) => {
      const k = byId.get(id) || {};
      const doc = (k.dokumentation || "").trim() || "[Udfyldes i selvevaluering]";
      return `| ${id} | ${esc(req)} | ${level} | ${esc(doc)} |`;
    }).join("\n");
    tableBlocks[theme] = rows;
  });

  const dateVal = document.getElementById("reportDate").value || new Date().toISOString().slice(0,10).split("-").reverse().join("-");
  const md = `# Governancerapport for ${esc(data.productName || "[produktnavn]")}\n\n> **📄 Dokumentinformation**  \n> **Version for anvendt governancerapport:** 1.1.0  \n> **Dato for udfyldelse:** ${esc(dateVal)}  \n> **Udfyldt af:** ${esc(document.getElementById("filledBy").value || data.filledBy || "[Navn]")}  \n> **Link til Git organisation:** ${esc(document.getElementById("githubLink").value || "[indsæt link til git organisation/repo]")}  \n\n## RELEVANS\n\n| #   | Krav                                          | Produktniveau | Retningslinjer |
| --- | --------------------------------------------- | --------------| -------------- |
${tableBlocks.relevans}\n\n## FORMKRAV\n\n| #   | Krav                                          | Produktniveau | Retningslinjer |
| --- | --------------------------------------------- | --------------| -------------- |
${tableBlocks.formkrav}\n\n## STRATEGISK SAMMENHÆNG\n\n| #   | Krav                                          | Produktniveau | Retningslinjer |
| --- | --------------------------------------------- | --------------| -------------- |
${tableBlocks.strategisk}\n\n## GOVERNANCE\n\n| #   | Krav                                          | Produktniveau | Retningslinjer |
| --- | --------------------------------------------- | --------------| -------------- |
${tableBlocks.governance}`;

  lastMarkdown = md;
  document.getElementById("output").value = md;
}

function download() {
  if (!lastMarkdown) return alert("Generér rapporten først.");
  const blob = new Blob([lastMarkdown], {type: "text/markdown;charset=utf-8"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url;
  a.download = "os2-governancerapport.md";
  a.click();
  URL.revokeObjectURL(url);
}

render();
</script>
