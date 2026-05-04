---
title: OS2 evalueringsrapport (generator)
layout: default
nav_order: 3
has_children: false
has_toc: false
---

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">

<div id="app" class="container-fluid my-4 px-3 px-md-5"></div>

<script>
const REQUIREMENTS = [
  ["relevans","R1","Sandkasse","Løsningen skaber lokal værdi","Standard: Produktet giver konkret og dokumenterbar værdi for den enkelte myndighed."],
  ["relevans","R2","2","Løsningen er accepteret af lokal linjeledelse","Standard: Linjeledelsen har bakket op om deltagelsen i udviklingen og anvendelsen."],
  ["relevans","R3","2","Løsningen har fælles offentligt potentiale","Standard: Kan skabe værdi og genbruges på tværs af myndigheder."],
  ["relevans","R4","3","Ophæng til nationale strategier er til stede","Standard: Understøtter fx digitaliseringsstrategi og fællesoffentlige mål."],
  ["formkrav","F1","Sandkasse","Kildekode til projektet udvikles synligt og aktivt i et OS2-repositorie","Standard: Kodebasen er tilgængelig og udvikles åbent på GitHub i OS2-kontrolleret organisation."],
  ["formkrav","F2","Sandkasse","Open Source-licenskriterier overholdes","Standard: Godkendt Open Source Licens (fx MPL-2.0) er tydeligt angivet og anvendt."],
  ["formkrav","F3","Sandkasse","Udbudsregler og almindelig lovformlighed er overholdt","Standard: Projektet følger udbudsregler og gældende lovgivning."],
  ["formkrav","F4","Sandkasse","Der er tænkt på sikkerheden i løsningen","Standard: Der forefindes dokumenteret sikkerhedsarbejde og/eller procedurer."],
  ["formkrav","F5","Sandkasse","Løsningens formål og værdi er beskrevet","Standard: Formål og værdi er klart beskrevet, gerne i en README tilknyttet kodebasen."],
  ["formkrav","F6","1","Kildekoden er overdraget og placeret under OS2's GitHub","Standard: Koden er juridisk overdraget og hostes under OS2's GitHub."],
  ["formkrav","F7","1","Dokumentation udarbejdes med og overholder OS2's standardskabelon","Standard: Dokumentation i åbent format (fx Markdown) og OS2’s skabelon anvendt."],
  ["formkrav","F10","1","OS2's kommunikationskanaler anvendes","Standard: Information findes på os2.eu."],
  ["formkrav","F11","1","Offentlig issue-tracking anvendes","Standard: Opgaver (issues) og kodeændringer spores offentligt og tilknyttes GitHub."],
  ["formkrav","F12","2","Kun én version af core-koden (master)","Standard: Ingen parallelle versioner af kodebasen."],
  ["formkrav","F13","2","Præsentationsmateriale af løsningen er udarbejdet","Standard: Der findes præsentationer om produktet."],
  ["formkrav","F14","2","Kommunikationsmateriale til strategisk niveau","Standard: Der findes materialer målrettet ledelse og strategi."],
  ["formkrav","F15","2","Best practice for implementering i organisationen dokumenteres","Standard: Vejledninger og erfaringer er beskrevet."],
  ["formkrav","F16","2","Teknisk dokumentation indeholder best practice for kodestandarder","Standard: Kodestandarder dokumenteret, relevant dokumentation til udviklere."],
  ["formkrav","F17","2","Drifts- og vedligeholdelsessetup er beskrevet","Standard: Driftmiljø og procedurer for vedligehold beskrevet."],
  ["formkrav","F18","2","Rammearkitektur og standarder er fulgt og afvigelser forklaret","Standard: Overensstemmelse med rammearkitektur er beskrevet."],
  ["formkrav","F19","2","Løsningen leveret i containerformat","Standard: Fx Docker anvendes."],
  ["formkrav","F20","2","Uddannelsesmateriale er udarbejdet","Standard: Undervisningsmaterialer findes."],
  ["formkrav","F21","3","Politisk kommunikation er udarbejdet","Standard: Materialer målrettet politikere og offentlighed er udarbejdet."],
  ["formkrav","F22","3","Procesplan og procesansvar for drift er udarbejdet","Standard: Dokumenteret proces og ansvar ifm. idriftsættelse."],
  ["strategisk","S1","1","Produktet har kobling til OS2's strategi","Standard: Understøtter OS2’s mission og vision."],
  ["strategisk","S2","1","Løsningen understøtter innovation og open source","Standard: Fremmer innovation og åbenhed."],
  ["strategisk","S3","2","Kobling til OS2's mission, vision og strategi er beskrevet","Standard: Forbindelsen er beskrevet."],
  ["strategisk","S4","2","Vision og strategi for produktet er udarbejdet","Standard: Der findes en formel vision og strategi for produktet."],
  ["strategisk","S5","3","Produktets overensstemmelse med OS2's vision og strategi","Standard: Tydelig sammenhæng og beskrivelse."],
  ["governance","G1","1","Produktet er oprettet i OS2's porteføljestyring","Standard: Findes i OS2’s porteføljedatabase, hjemmeside og årshjul."],
  ["governance","G2","1","Der koordineres løbende med OS2-sekretariatet","Standard: Der er løbende kontakt med sekretariatet."],
  ["governance","G3","1","Projektleder/tovholder er udpeget","Standard: Der er udpeget en fast kontaktperson/koordinator."],
  ["governance","G4","1","Bestyrelsen er orienteret","Standard: Bestyrelsen kender til projektet."],
  ["governance","G5","2","Bestyrelsen har godkendt produktet","Standard: Formelt godkendt i referater."],
  ["governance","G6","2","Der er nedsat en styregruppe","Standard: Der findes en aktiv styregruppe."],
  ["governance","G7","2","Der er nedsat en koordinationsgruppe","Standard: Der findes en aktiv koordinationsgruppe."],
  ["governance","G8","2","Projektmodel anvendes og dokumenteret (anbefaling)","Standard: Der arbejdes efter en dokumenteret projektmodel."],
  ["governance","G9","2","Review af kode foretages af tredjepart (anbefaling)","Standard: Uafhængig kodegennemgang gennemføres og procedure er beskrevet."],
  ["governance","G10","2","Tilslutningserklæring til sikring af økonomi (anbefaling)","Standard: OS2-tilslutningsaftale findes og er effektueret."],
  ["governance","G11","3","Bestyrelsen har godkendt styregruppen","Standard: Formelt godkendt i referater."],
  ["governance","G12","3","Bestyrelsen er repræsenteret i styregruppen","Standard: Bestyrelsesmedlem deltager."],
  ["governance","G13","3","Aftale sikrer økonomi til koordinering og videreudvikling","Standard: Aftaler om finansiering er på plads og budget udarbejdet."],
  ["governance","G14","3","Fagligt fællesskab bag løsningen","Standard: Aktivt fællesskab, fx brugerklub, forum eller andet netværk."]
];

const LEVELS = ["Sandkasse", "1", "2", "3"];
const LEVEL_LABELS = {"Sandkasse":"Sandkasse","1":"Niveau 1","2":"Niveau 2","3":"Niveau 3"};
const THEMES = ["relevans","formkrav","strategisk","governance"];
const THEME_LABELS = {relevans:"Relevans", formkrav:"Formkrav", strategisk:"Strategisk sammenhæng", governance:"Governance"};
const levelOrder = {"Sandkasse":0,"1":1,"2":2,"3":3};

function mapStatus(v) {
  if (v === "Ja") return { emoji: "🟢", key: "green" };
  if (v === "Nej") return { emoji: "🔴", key: "red" };
  if (v === "Ved ikke") return { emoji: "🟡", key: "yellow" };
  return { emoji: "🔴", key: "red" };
}

function esc(s){ return String(s||"").replace(/\|/g, "\\|").replace(/\n/g,"<br/>"); }

function render() {
  document.getElementById("app").innerHTML = `
    <h1>OS2 evalueringsrapport generator</h1>
    <p>Upload JSON fra selvevaluering og generér en udfyldt rapport i Markdown-format.</p>
    <div class="row g-3 mb-3">
      <div class="col-12 col-md-4"><label class="form-label">JSON-fil</label><input id="jsonFile" class="form-control" type="file" accept=".json,application/json"></div>
      <div class="col-12 col-md-4"><label class="form-label">Audit made by</label><input id="auditBy" class="form-control" placeholder="Navn"></div>
      <div class="col-12 col-md-4"><label class="form-label">GitHub organisation/repo</label><input id="githubLink" class="form-control" placeholder="https://github.com/..." ></div>
      <div class="col-12 col-md-4"><label class="form-label">Dato for udfyldelse</label><input id="reportDate" class="form-control" type="date"></div>
      <div class="col-12"><label class="form-label">Resumé</label><textarea id="summary" class="form-control" rows="2"></textarea></div>
      <div class="col-12"><label class="form-label">Overordnet vurdering</label><textarea id="overall" class="form-control" rows="3"></textarea></div>
      <div class="col-12"><label class="form-label">Anbefaling</label><textarea id="recommendation" class="form-control" rows="3"></textarea></div>
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
    const rows = REQUIREMENTS.filter(r => r[0] === theme).map(([_, id, lvl, req, crit]) => {
      const k = byId.get(id) || {};
      const m = mapStatus(k.efterlevet);
      const grundlag = (k.dokumentation || "").trim() || "Ingen data i selvevalueringsrapport.";
      return `| ${id} | ${lvl} | ${esc(req)} | ${esc(crit)} | ${m.emoji} | ${esc(grundlag)} |`;
    }).join("\n");
    tableBlocks[theme] = rows;
  });

  function bucketFor(levelMax, theme = null) {
    const acc = {green:0,yellow:0,red:0};
    REQUIREMENTS.forEach(([t,id,lvl]) => {
      if (theme && t !== theme) return;
      if (levelOrder[lvl] > levelOrder[levelMax]) return;
      const m = mapStatus((byId.get(id) || {}).efterlevet).key;
      acc[m]++;
    });
    return acc;
  }
  function bucketExact(level, theme = null) {
    const acc = {green:0,yellow:0,red:0};
    REQUIREMENTS.forEach(([t,id,lvl]) => {
      if (theme && t !== theme) return;
      if (lvl !== level) return;
      const m = mapStatus((byId.get(id) || {}).efterlevet).key;
      acc[m]++;
    });
    return acc;
  }

  const bSand = bucketExact("Sandkasse");
  const b1 = bucketExact("1");
  const b2 = bucketExact("2");
  const b3 = bucketExact("3");
  const total = bucketFor("3");

  const assertMax = (bucket, max, label) => {
    const sum = bucket.green + bucket.yellow + bucket.red;
    if (sum > max) throw new Error(`Optælling for ${label} overstiger maks (${sum}/${max}).`);
  };
  assertMax(bucketFor("3", "relevans"), 4, "Relevans");
  assertMax(bucketFor("3", "formkrav"), 20, "Formkrav");
  assertMax(bucketFor("3", "strategisk"), 5, "Strategisk sammenhæng");
  assertMax(bucketFor("3", "governance"), 14, "Governance");
  assertMax(bucketExact("Sandkasse"), 6, "Sandkasse");
  assertMax(bucketExact("1"), 10, "Niveau 1");
  assertMax(bucketExact("2"), 19, "Niveau 2");
  assertMax(bucketExact("3"), 8, "Niveau 3");
  assertMax(bucketFor("3"), 43, "Samlet");

  const levelTable = `| Niveau      | 🟢 Grøn | 🟡 Gul | 🔴 Rød |\n|-------------|---------|--------|--------|\n| Sandkasse   | ${bSand.green} | ${bSand.yellow} | ${bSand.red} |\n| Niveau 1    | ${b1.green} | ${b1.yellow} | ${b1.red} |\n| Niveau 2    | ${b2.green} | ${b2.yellow} | ${b2.red} |\n| Niveau 3    | ${b3.green} | ${b3.yellow} | ${b3.red} |\n| **Samlet**  | ${total.green} | ${total.yellow} | ${total.red} |`;

  const themeRows = THEMES.map(theme => {
    const s = bucketExact("Sandkasse", theme), n1 = bucketExact("1", theme), n2 = bucketExact("2", theme), n3 = bucketExact("3", theme), tt = bucketFor("3", theme);
    return `| ${THEME_LABELS[theme]} | 🟢 ${s.green} 🟡 ${s.yellow} 🔴 ${s.red} | 🟢 ${n1.green} 🟡 ${n1.yellow} 🔴 ${n1.red} | 🟢 ${n2.green} 🟡 ${n2.yellow} 🔴 ${n2.red} | 🟢 ${n3.green} 🟡 ${n3.yellow} 🔴 ${n3.red} | 🟢 ${tt.green} 🟡 ${tt.yellow} 🔴 ${tt.red} |`;
  }).join("\n");

  function mermaid(levelTitle, totalCount, b) {
    const p = (n) => totalCount ? Math.round((n / totalCount) * 100) : 0;
    const ranked = [
      {key: "green", value: b.green, color: "#008000"},
      {key: "yellow", value: b.yellow, color: "#FFFF00"},
      {key: "red", value: b.red, color: "#FF0000"}
    ].sort((a, c) => c.value - a.value);
    const themeVars = `{"pie1": "${ranked[0].color}", "pie2": "${ranked[1].color}", "pie3": "${ranked[2].color}"}`;
    return `\`\`\`mermaid
%%{init: {"themeVariables": ${themeVars}}}%%
pie showData
`+
      `  title ${levelTitle} (${totalCount} krav)
`+
      `  "Grøn ${p(b.green)}%" : ${b.green}
`+
      `  "Gul ${p(b.yellow)}%"  : ${b.yellow}
`+
      `  "Rød ${p(b.red)}%"  : ${b.red}
`+
      "```";
  }

  const dateVal = document.getElementById("reportDate").value || new Date().toISOString().slice(0,10).split("-").reverse().join("-");
  const md = `# Evaluering af OS2-produkt: ${esc(data.productName || "[Produktnavn]")}\n\n> **📄 Dokumentinformation**<br/>\n> **Evalueringsskabelon version:** 0.9.1<br/>\n> **Dato for udfyldelse:** ${esc(dateVal)}<br/>\n> **Audit made by:** ${esc(document.getElementById("auditBy").value || "[Navn]")}<br/>\n> **GitHub organisation:** ${esc(document.getElementById("githubLink").value || "[indsæt link til github organisation/repo]")}<br/>\n\n## 📝 Resumé\n${esc(document.getElementById("summary").value || "Udfyldes senere.")}\n\n### 🔍 Overordnet vurdering\n${esc(document.getElementById("overall").value || "Udfyldes senere.")}\n\n### 📈 Anbefaling\n${esc(document.getElementById("recommendation").value || "Udfyldes senere.")}\n\n## 🌍 RELEVANS\n\n| #   | Niveau    | Krav | Vurderingskriterie | Vurdering | Vurderingsgrundlag |\n|-----|-----------|------|--------------------|-----------|--------------------|\n${tableBlocks.relevans}\n\n## 🛠️ FORMKRAV\n\n| #    | Niveau    | Krav | Vurderingskriterie | Vurdering | Vurderingsgrundlag |\n|------|-----------|------|--------------------|-----------|--------------------|\n${tableBlocks.formkrav}\n\n## 🏛️ STRATEGISK SAMMENHÆNG\n\n| #   | Niveau    | Krav | Vurderingskriterie | Vurdering | Vurderingsgrundlag |\n|-----|-----------|------|--------------------|-----------|--------------------|\n${tableBlocks.strategisk}\n\n## 👥 GOVERNANCE\n\n| #    | Niveau    | Krav | Vurderingskriterie | Vurdering | Vurderingsgrundlag |\n|------|-----------|------|--------------------|-----------|--------------------|\n${tableBlocks.governance}\n\n### 📊 Optælling af vurderinger pr. niveau og tema\n\n${levelTable}\n\n| Tema / Niveau | Sandkasse | Niveau 1 | Niveau 2 | Niveau 3 | Total |\n|---|---|---|---|---|---|\n${themeRows}\n\n${mermaid("Sandkasse", 6, bSand)}\n\n${mermaid("Niveau 1", 10, b1)}\n\n${mermaid("Niveau 2", 19, b2)}\n\n${mermaid("Niveau 3", 8, b3)}\n\n${mermaid("Samlet", 43, total)}\n\n## 🏷️ Hvad betyder trafiklysene?\n- 🟢 **Grøn** → Kravet er fuldt opfyldt og fungerer som forventet.\n- 🟡 **Gul** → Kravet er delvist opfyldt, men der er mangler, som bør adresseres.\n- 🔴 **Rød** → Kravet er ikke opfyldt, og der er behov for handling.\n\n## 📋 Hvordan bruges optællingen?\n\n- **Sandkasse:** Grundlæggende formalia – mange 🔴 her betyder, at produktet skal løftes bare for at blive betragtet som OS2-kompatibelt.  \n- **Niveau 1:** Basis governance og dokumentation – – mange 🟡 eller 🔴 her peger på udfordringer med at skabe overblik og ejerskab.   \n- **Niveau 2:** Drift, vedligehold og strategisk understøttelse – mange 🟡 eller 🔴 her peger på modenhedsproblemer.  \n- **Niveau 3:** Avanceret governance og fællesskab – et område, hvor ikke alle produkter nødvendigvis når i mål, men som er ønskværdigt for stabile og bæredygtige produkter.\n\nUd fra optællingen kan vi vurdere, hvor produktet står samlet set:\n\n- Mange 🟢 → Produktet er solidt forankret i governance-kravene.\n- Mange 🟡 → Produktet har et godt grundlag, men kræver en prioriteret indsats på udvalgte områder.\n- Mange 🔴 → Produktet har alvorlige governance-mangler og kræver en struktureret genopretning.\n\n### ➡️ Antal krav fordelt på tema\n* Relevans: *4 krav* (R1–R4)\n* Formkrav: *20 krav* (F1–F22, minus F8 og F9 som er sammenlagt med F7)\n* Strategisk sammenhæng: *5 krav* (S1–S5)\n* Governance: *14 krav* (G1–G14)\n* *I alt: 43 krav*\n\n### ➡️ Antal krav fordelt på niveau\n\nBemærk at der nedarves så et niveau 2 produkt skal også efterleve sandkasse og niveau 2.\n\n* Sandkasse: *6 krav*\n* Niveau 1: *10 krav* (16 i alt)\n* Niveau 2: *19 krav* (35 i alt)\n* Niveau 3: *8 krav* (43 i alt)\n* *I alt: 43 krav*`;

  lastMarkdown = md;
  document.getElementById("output").value = md;
}

function download() {
  if (!lastMarkdown) return alert("Generér rapporten først.");
  const blob = new Blob([lastMarkdown], {type: "text/markdown;charset=utf-8"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url;
  a.download = "os2-evalueringsrapport.md";
  a.click();
  URL.revokeObjectURL(url);
}

render();
</script>
