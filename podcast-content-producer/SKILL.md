---
name: podcast-content-producer
description: Analizuoja NotebookLM podkasto tekstinį transkriptą ir gamina pilnus „Content paketus" kiekvienam Audiogram klipui Instagram Reels formatui. NAUDOK šį skill'ą kai vartotojas įklijuoja podkasto transkriptą ir prašo sukurti klipus, content paketą, išskirti atkarpas, arba mini frazę „NotebookLM", „audiogram", „podcast klipai", „reels iš podkasto" ar pan. Taip pat trigger'ink kai vartotojas sako „išanalizuok tekstą klipams" arba „padaryk content paketą".
---

# Podcast Content Producer

Šis skill'as paverčia NotebookLM podkasto transkriptą į pilnus Instagram Reels Audiogram content paketus lietuvių auditorijai.

---

## Kontekstas ir taisyklės

**Inputas:** Lietuviškas podkasto tekstinis transkriptas (be timestamps).  
**Outputas:** Struktūruotas content paketas kiekvienam klipui.  
**Platforma:** Instagram Reels pirma; tie patys klipai → TikTok, YouTube Shorts.  
**Formatas:** Audiogram (stacionarus vaizdas + podkasto audio + subtitrai).  
**Kalba:** Gyva, šnekamoji lietuvių kalba. Jokių akademizuotų ar tiesmukai išverstų frazių.  
**Tonas:** Šaltas, inžinerinis, tikslus. Jokių atsiprašymų, emocinio balasto ar tuščių komplimentų.

---

## Dialogo pjaustymo taisyklė (2 kalbėtojai) — KRITINIS SAUGIKLIS

NotebookLM generuoja **dviejų kalbėtojų dialogą**. Karpymas pagal žodžių skaičių draudžiamas.

**Klipas privalo turėti mini-scenarijaus struktūrą:**
```
[Stipri pradžia / Klausimas → Trumpas argumentas / Atsakymas → Taškas pokalbyje]
```

**Draudžiama:**
- Baigti klipą viduryje vieno kalbėtojo sakinio
- Palikti klausimą be atsakymo
- Nutraukti mintį ten, kur techniškai baigiasi laikas

**Taisyklė:** Jei užbaigta mintis reikalauja +10–15 sek. viršijant limitą — pratęsti. Dialogo integrumas svarbesnis už tikslius skaičius.

---

## Žingsnis 1 — Matematinis įvertinimas

Prieš pjaustant transkriptą, reikia apskaičiuoti **teorinę audio trukmę**.

**Skaičiavimo formulė:**
- Lietuviškas šnekamasis tempas: ~120–140 žodžių per minutę
- Suskaičiuok transkripto žodžius
- Apskaičiuok trukmę minutėmis: `žodžiai ÷ 130`
- Pagal tą trukmę nustatyk **klipų skaičių**

**Klipų skaičiaus logika:**

| Audio trukmė | Klipų kiekis |
|---|---|
| iki 3 min | 2–3 klipai |
| 3–6 min | 3–5 klipai |
| 6–10 min | 4–6 klipai |
| 10–15 min | 6–8 klipai |
| 15–20 min | 8–10 klipai |
| 20+ min | 10–13 klipai |

**Svarbu:** Klipas turi turėti loginę pradžią ir pabaigą. Geriau 4 stiprūs klipai nei 10 dirbtinai sukapotų.  
Tikslinė trukmė: **30–60 sekundžių** (~65–130 žodžių). Jei mintis stipri ir reikia 75 sek. — leisti.

---

## Žingsnis 2 — Transkripto analizė

Skaitant transkriptą, ieškoti šių klipų tipų:

1. **Kontroversiška tezė** — teiginys, su kuriuo dalis sutiks, dalis nesutiks
2. **„Aha" momentas** — netikėta įžvalga ar faktas
3. **Praktinis patarimas** — konkretus, veiksminis
4. **Emocinis momentas** — autentiškas, žmogiškas
5. **Klausimas–atsakymas** — natūrali dialoginė struktūra

Pirmenybė teikiama **savaimingiems fragmentams** — kur viena mintis turi aiškią pradžią ir pabaigą be konteksto iš kitos dalies.

---

## Žingsnis 3 — Content paketo struktūra

Kiekvienam klipui pateikti **tokią struktūrą**:

```
────────────────────────────────────────
KLIPAS [N] — [Temos pavadinimas] (~XX sek.)
────────────────────────────────────────

🎙️ AUDIO IŠKARPA:
[„...tikslus pirmasis žodis ar frazė" → „...paskutinis žodis ar frazė..."]
⚠️ Patikrinti: ar klipas baigiasi užbaigta abiejų kalbėtojų mintimi?

⚡ HOOK (ekrane 0–3 sek.):
[Trumpas, provokuojantis tekstas — max 6–8 žodžiai]
⚠️ Tonas turi atitikti šio klipo nuotaiką (provokuojanti / edukacinė / ironiška / skandalinga)

📝 CAPTION:
[2–4 sakiniai gyva kalba. Pirmas sakinys — hook'o pratęsimas arba klausimas. 
Antras/trečias — kontekstas ar vertė. Paskutinis — CTA arba klausimas auditorijai.]
⚠️ Sakiniai trumpi — max 12–15 žodžių vienoje eilutėje (CapCut subtitrų optimizacija)

#️⃣ HASHTAGS:
[8–12 hashtag'ų: 3–4 nišiniai LT, 3–4 bendri LT, 2–3 anglų kalba platesniam pasiekiamumui]
────────────────────────────────────────
```

---

## Žingsnis 4 — Hook'o rašymo principai

Hook'as yra **svarbiausias elementas**. Jis lemia ar žmogus sustoja ar slenka toliau.

**Veikiančios formulės:**
- Prieštaravimas: „[Populiarus įsitikinimas] yra melas."
- Skaičius: „[X] priežasčių kodėl [Y] neveikia."
- Intriga: „Niekas tau nepasakė apie [X]."
- Klausimas: „Ar tikrai žinai, [ką/kaip/kodėl]...?"
- Provokacija: „[Dalykas] nėra tai, ką manai."

**Tono atitikimas (SAUGIKLIS #3):**  
Hook'o formulę parinkti pagal konkretaus klipo emocinį toną — ne universalų šabloną:

| Klipo nuotaika | Rekomenduojama formulė |
|---|---|
| Edukacinė / faktinė | Skaičius arba Klausimas |
| Ironija / humoras | Prieštaravimas arba Provokacija |
| Skandalinga / drąsi tezė | Provokacija arba Intriga |
| Emocinis / žmogiškas momentas | Klausimas arba Intriga |

**Kalba:** Šnekamoji, trumpa, be kabučių. Rašoma taip, kaip žmogus šneka.

---

## Žingsnis 4b — Subtitrų optimizacija (CapCut)

Kadangi subtitrai generuojami automatiškai per CapCut ant stacionaraus vaizdo, caption'o ir transkripto tekstai turi būti pritaikyti ekrano skaitymui.

**Taisyklės:**
- Vienas subtitro blokas: **max 5–7 žodžiai**
- Sakiniai, viršijantys 12 žodžių, **skaidyti per kablelį ar brūkšnį** į trumpas frazes
- Vengti ilgų sudėtinių sakinių su keliais jungtukiniais dėmenimis
- Dinamiška struktūra: trumpas sakinys → vidutinis sakinys → trumpas sakinys

**Pavyzdys:**
- ❌ „Dirbtinis intelektas šiandien keičia viską, ką žinojome apie kūrybiškumą ir darbo rinką."
- ✅ „AI keičia viską. / Kūrybiškumą. Darbo rinką. / Viską, ką žinojome."

---

## Žingsnis 5 — Caption'o rašymo principai

- Pirmasis sakinys: pratęsia hook'ą arba stato klausimą
- Vidurys: suteikia kontekstą, bet **nepersako** klipo — intriguoja
- Pabaiga: CTA („Klausyk iki galo", „Parašyk komentare", „Pasidalink su tuo, kuriam tai aktualu")
- Max ilgis: ~150 žodžių
- Emodziai: naudoti minimaliai (1–3), tik prasmingai

---

## Žingsnis 6 — Hashtag'ų strategija

Struktūra kiekvienam klipui:
- **3–4 nišiniai LT** (pvz. `#podkastaslt`, `#versloslt`, `#technologijoslt`)
- **3–4 bendri LT** (pvz. `#lietuviskaipasaka`, `#lietuviškaipasaka`, `#lietuvakkalba`)
- **2–3 anglų** (pvz. `#podcast`, `#aitools`, `#shortformcontent`)

Vengti generinių, perkrautų hashtag'ų (pvz. `#love`, `#instagood`).

---

## Kritinės klaidos, kurių vengti

❌ **Matematiška klaida:** Niekada neskaidyti teksto į daugiau klipų nei leidžia trukmė.  
❌ **Dirbtinė pabaiga:** Klipas negali baigtis „ore" — mintis turi būti užbaigta.  
❌ **Dialogo sulaužymas:** Klipas negali baigtis vieno kalbėtojo vidury sakinio ar palikti klausimą be atsakymo.  
❌ **Kontekstas iš oro:** Klipas turi būti suprantamas be kito klipo konteksto.  
❌ **Akademinė kalba:** „Šiame fragmente aptariamas..." — draudžiama. Rašyti žmogiškai.  
❌ **Pasikartojantys hook'ai:** Kiekvienas iš [N] klipų turi turėti skirtingą hook'o formulę.  
❌ **Tono neatitikimas:** Hook'as negali būti provokuojantis jei klipas emocinis, ir atvirkščiai.  
❌ **Ilgi subtitrai:** Sakiniai virš 12 žodžių turi būti skeliami — CapCut ekranui optimizuoti.

---

## Rezultato pateikimas

Po visų klipų pateikti:

```
────────────────────────────────────────
📊 SESIJOS SUVESTINĖ
────────────────────────────────────────
Transkripto žodžių: ~[X]
Apskaičiuota trukmė: ~[X] min.
Išskirta klipų: [N]
Bendras klipų laikas: ~[X] sek.
Vidutinė klipo trukmė: ~[X] sek.
────────────────────────────────────────
```
