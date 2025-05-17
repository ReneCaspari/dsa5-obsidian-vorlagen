### 💰 **Geldbeutel**

| Münze             | Wert in der nächstkleineren Einheit  | Beispiel              |
| ----------------- | ------------------------------------ | --------------------- |
| **1 Dukat**       | = **10 Silbertaler**                 | 1 D = 10 S            |
| **1 Silbertaler** | = **10 Heller**                      | 1 S = 10 H            |
| **1 Heller**      | = **10 Kreuzer**                     | 1 H = 10 K            |
| **1 Dukat**       | = **100 Heller** = **1.000 Kreuzer** | 1 D = 100 H = 1.000 K |

| Dukaten | Silbertaler | Heller | Kreuzer |
| ------- | ----------- | ------ | ------- |
|         | 500         |        |         |
|         |             |        |         |

### 💰 **Inventar**

```dataviewjs
const items = [
{ name: "Dolch", anzahl: 1, gewicht: 0.5, wert: 0 },
{ name: "Fellrüstung", anzahl: 1, gewicht: 1.5, wert: 20 },
];

let totalGewicht = 0;
let totalWert = 0;

dv.table(
  ["Gegenstand", "Anz.", "Gew. (Stn)", "Wert/Stück", "GesGew", "GesWert"],
  items.map(i => {
    const gesGew = i.anzahl * i.gewicht;
    const gesWert = i.anzahl * i.wert;
    totalGewicht += gesGew;
    totalWert += gesWert;
    return [
      i.name,
      i.anzahl,
      i.gewicht.toFixed(2),
      `${i.wert} S`,
      gesGew.toFixed(2),
      `${gesWert.toFixed(2)} S`
    ];
  })
);

dv.paragraph(`**Gesamtgewicht:** ${totalGewicht.toFixed(2)} Stn`);
dv.paragraph(`**Gesamtwert:** ${totalWert.toFixed(2)} S`);

```

