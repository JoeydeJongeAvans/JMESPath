

### JMESPath Tips & Voorbeelden

#### Basisstructuur
- **Selecteren van een veld:**
  ```json
  {
    "naam": "Jan",
    "leeftijd": 30
  }
  ```
  **Query:** `naam`  
  **Resultaat:** `"Jan"`

- **Toegang tot geneste objecten:**
  ```json
  {
    "adres": {
      "straat": "Hoofdweg",
      "stad": "Amsterdam"
    }
  }
  ```
  **Query:** `adres.straat`  
  **Resultaat:** `"Hoofdweg"`

#### Lijsten en Filters
- **Elementen uit een lijst selecteren:**
  ```json
  {
    "namen": ["Jan", "Piet", "Klaas"]
  }
  ```
  **Query:** `namen[0]`  
  **Resultaat:** `"Jan"`

- **Filteren op basis van een waarde:**
  ```json
  {
    "personen": [
      {"naam": "Jan", "leeftijd": 30},
      {"naam": "Piet", "leeftijd": 25}
    ]
  }
  ```
  **Query:** `personen[?leeftijd > 28].naam`  
  **Resultaat:** `["Jan"]`

#### Werken met meerdere niveaus
- **Meerdere waarden ophalen:**
  ```json
  {
    "auto": {
      "merk": "Toyota",
      "model": "Corolla",
      "jaar": 2020
    }
  }
  ```
  **Query:** `auto.{merk: merk, model: model}`  
  **Resultaat:** `{"merk": "Toyota", "model": "Corolla"}`

#### Aggregatiefuncties
- **Tellen van elementen:**
  ```json
  {
    "nummers": [1, 2, 3, 4, 5]
  }
  ```
  **Query:** `length(nummers)`  
  **Resultaat:** `5`

- **Maximale waarde vinden:**
  ```json
  {
    "scores": [7, 8, 9, 6]
  }
  ```
  **Query:** `max(scores)`  
  **Resultaat:** `9`

#### Miscellaneous
- **Nulwaarden hanteren:**
  ```json
  {
    "items": [null, "a", null, "b"]
  }
  ```
  **Query:** `items[?!null]`  
  **Resultaat:** `["a", "b"]`

#### Nesten en Combinaties
- **Samengestelde queries:**
  ```json
  {
    "producten": [
      {"naam": "Boek", "prijs": 10},
      {"naam": "Pen", "prijs": 2}
    ]
  }
  ```
  **Query:** `producten[*].{naam: naam, prijs: prijs}`  
  **Resultaat:** `[{"naam": "Boek", "prijs": 10}, {"naam": "Pen", "prijs": 2}]`

Met deze voorbeelden kun je een goede start maken en je collega's op weg helpen met JMESPath. Het kan handig zijn om te experimenteren met een online JMESPath tester om snel resultaten te zien.
