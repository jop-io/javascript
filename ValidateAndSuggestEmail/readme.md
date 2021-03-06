# Validera och föreslå förbättringar av inmatade e-postadresser
Funktion för att att validera en e-postadress som giltig, samt kontrollera om vanliga stavfel eller felskrivningar förekommer.

### Exempel 1 - Giltig e-postadress (inga förbättringsförslag hittades)
```javascript
validateSuggestEmail("namn@gmail.com");
```
...returnerar...
```javascript
true
```

### Exempel 2 - Ogiltig e-postadress
```javascript
validateSuggestEmail("namn@@gmail.");
```
...returnerar...
```javascript
false
```

### Exempel 3 - Giltig e-postadress (förbättringsförslag hittades)
```javascript
validateSuggestEmail("namn@gmail.se");
```
...returnerar...
```javascript
{
  // Förslag på bättre e-postadress
  suggestion: "namn@gmail.com",
  // Användarnamn
  user: "namn",
  // Hostname
  host: "gmail",
  // Toppdomän
  tld: "com",
  // Domän
  domain: "gmail.com",
  // Vilken del av den föreslagna e-postadressen som har förbättrats
  diff: "tld" // Kan vara 'host', 'tld' eller 'domain'
  // HTML-sträng där förslaget på förbättring är inkapslat i en em-tagg
  html: "namn@gmail.<em>com</em>"
}
```

