---
title: 'Uvod u osnove R'
description: 'U ovom poglavlju napravićete svoje prve korake u R. Naučićete kako da koristite konzolu kao kalkulator i kako da dodeljujete promenljive (varijable). Takođe ćete se upoznati sa osnovnim tipovima podataka u R. '
free_preview: true
---

## Kako funkcioniše platforma

```yaml
type: NormalExercise
key: 15d729634a
xp: 100
skills: 1
```

U editoru koji je sa desne strane kucate R kod da biste rešili zadatke. Kada kliknete na dugme 'Submit Answer' svaka linija koda se interpetira i izvršava u R, i dobijate poruku da li je Vaš kod ispravan. Rezultat R koda se prikazuje u konzoli u donjem desnom uglu.

R koristi znak `#` za dodavanje komentara, tako da možete da saznate šta radi određena linija R koda. Kao Twitter! Komentari se ne izvršavaju kao R kod, tako da ne utiču na rezultat. Na primer, _Izračunajte 3 + 4_ u editoru sa desne strane je komentar.

R komande možete da izvršavate i direktno u konzoli. To je dobar način za eksperimentisanje jer se ne proverava da li ste tačno uradili zadatak.

`@instructions`
- U editoru sa desne strane već postoji primer koda. Da li možete da razlikujete koje su linije R kod a koje komentari?
- Dodajte liniju koda koja izračunava sumu brojeva 6 i 12 i kliknite na 'Submit Answer' dugme.

`@hint`
Samo dodajte liniju R koda koja izračunava sumu brojeva 6 i 12, isto kao i primer koda!

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Izračunajte 3 + 4
3 + 4
# Izračunajte 6 + 12
```

`@solution`
```{r}
# Izračunajte 3 + 4
3 + 4
# Izračunajte 6 + 12
6 + 12
```

`@sct`
```{r}
test_output_contains("18", incorrect_msg = "Ukucajte `6 + 12` u novi red. Ne započinjite red sa `#`, inače se R kod neće izvršiti!")
success_msg("Odlično! Primetili ste kako konzola prikazuje rezultat R koda koji ste priložili? Sada kad ste se upoznali sa interfejsom, možemo da krenemo sa R!")
```

---

## Aritmetičke operacije u R

```yaml
type: NormalExercise
key: 720745eda5
xp: 100
skills: 1
```

U osnovi, R može da se koristi kao kalkulator jer podržava sledeće aritmetičke operatore:

- Sabiranje: `+`
- Oduzimanje: `-`
- Množenje: `*`
- Deljenje: `/`
- Stepenovanje: `^`
- Modulo: `%%`

Pojasnićemo poslednje dve operacije:

- Operator `^` daje stepen broja sa leve strane na broj sa desne strane: na primer `3^2` je 9.
- Modulo vraća ostatak deljenja broja sa leve strane sa brojem sa desne strane, na primer 5 modulo 3 ili `5 %% 3` je 2.

Na osnovu prethodnog, rešite zadatak prateći instrukcije.

`@instructions`
- Ukucajte `2^5` u editor da biste izračunali 2 na 5.
- Ukucajte `28 %% 6` da biste izračunali 28 modulo 6.
- Kliknite 'Submit Answer' i pogledajte rezultat u izlaznoj konzoli.
- Primetićete da se simbol `#` koristi za dodavanje komentara R kodu.

`@hint`
Još jedan primer modulo operatora: `9 %% 2` jednako je `1`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Sabiranje
5 + 5 
# Oduzimanje
5 - 5 
# Množenje
3 * 5
 # Deljenje
(5 + 5) / 2 
# Stepenovanje
# Modulo
```

`@solution`
```{r}
# Sabiranje
5 + 5
# Oduzimanje
5 - 5 
# Množenje
3 * 5
# Deljenje
(5 + 5) / 2 
# Stepenovanje
2 ^ 5
# Modulo
28 %% 6
```

`@sct`
```{r}
msg = "Ne uklanjajte ostale primere!"
test_output_contains("2^5", incorrect_msg = "Primer stepenovanje nije tačan. Ukucajte `2 ^ 5` u novi red.")
test_output_contains("28 %% 6", incorrect_msg = "Postoji problem sa primerom modulo. Ukucajte `28 %% 6` u novi red.")
success_msg("Odlično! Pređite na sledeći zadatak.")
```

---

## Dodeljivanje vrednosti promenljivima

```yaml
type: NormalExercise
key: 5f200ffd43
xp: 100
skills: 1
```

Osnovni koncept statističkog programiranja su **promenljive** (variables). 

Promenljiva nam omogućava da dodelimo vrednost (npr 4) ili objekat (npr opis funkcije) u R. Kasnije možete koristi naziv promenljive da biste iskoristili vrednost ili objekat koji je dodeljen toj promenljivoj. 

Možete dodeliti vrednost 4 promenljivoj `my_var` pomoću komande

```
my_var <- 4
```

`@instructions`
Dovršite kod u editoru tako što ćete dodeliti vrednost 42 promenljivoj `x`. Kliknite 'Submit Answer'. Primetićete da kad ukucate komandu `x`, dobijate vrednost 42.

`@hint`
Pogledajte kako je vrednost 4 dodeljena promenljivoj `my_variable` u opisu vežbe. Uradite isto u editoru, ali sad dodelite vrednost 42 promenljivoj `x`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Dodelite vrednost 42 promenljivoj x
x <- 
# Prikažite vrednost promenljive x
x
```

`@solution`
```{r}
# Dodelite vrednost 42 promenljivoj x
x <- 42
# Prikažite vrednost promenljive x
x
```

`@sct`
```{r}
test_object("x", undefined_msg = "Proverite da li ste definisali promenljivu `x`.",
            incorrect_msg = "Proverite da li ste dodelili dobru vrednost promenljivoj `x`.") 
success_msg("Odlično! Da li ste primetili da R ne prikazuje vrednost promenljive u konzoli kad ste joj dodelili istu? `x <- 42` ne generiše izlaz, jer R pretpostavlja da ćete ovu promenljivu koristiti kasnije. Inače ne biste ni dodeljivali vrednost, zar ne? Možete preći na sledeću vežbu!")
```

---

## Dodeljivanje vrednosti promenljivima (2)

```yaml
type: NormalExercise
key: c5944b90eb
xp: 100
skills: 1
```

Pretpostavimo da imate korpu sa 5 jabuka. Kao Analitičar podataka hoćete da dodelite broj jabuka promenljivoj koja se zove `my_apples`.

`@instructions`
- Ukucajte sledeći kod u editoru: `my_apples <- 5`. Ova komanda će dodeliti vrednost 5 promenljivoj `my_apples`.
- Ukucajte: `my_apples` ispod drugog komentara. Rezultat će prikazati vrednost promenljive `my_apples`.
- Kliknite 'Submit Answer', i pogledajte šta je ispisano u konzoli: primetićete da je ispisan broj 5. R je povezao promenljivu `my_apples` sa vrednošću 5.

`@hint`
Zapamtite da ako želite da dodelite vrednost ili objekat promenljivoj u R, možete da koristite operator `<-`. Možete da koristite i `=`, ali je `<-` široko rasprostranjen u R zajednici.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Dodelite vrednost 5 promenljivoj my_apples
# Prikažite vrednost promenljive my_apples
```

`@solution`
```{r}
# Dodelite vrednost 5 promenljivoj my_apples
my_apples <- 5
# Prikažite vrednost promenljive my_apples
my_apples
```

`@sct`
```{r}
test_object("my_apples", 
            undefined_msg = "Budite sigurni da ste definisali promenljivu `my_apples`.",
            incorrect_msg = "Budite sigurni da ste dodelili dobru vrednost promenljivoj `my_apples`.")
test_output_contains("my_apples", incorrect_msg = "Da li ste ukucali komandu u R koja prikazuje (ispisuje) promenljivu `my_apples` u konzoli?")
success_msg("Odlično! Nastavite dalje!")
```

---

## Dodeljivanje vrednosti promenljivima (3)

```yaml
type: NormalExercise
key: 1c1bd25045
xp: 100
skills: 1
```

Svaka ukusna korpa sa voćem ima pomorandže, tako da ste odlučili da dodate 6 pomorandži. Pošto ste analitičar podataka, odlučujete da odmah kreirate promenljivu `my_oranges` i dodelite joj vrednost 6. Sledeće, hoćete da izračunate koliko komada voća imate ukupno. Pošto ste dali promenljivima logične naziva to možete da uradite na sledeći način: 

```
my_apples + my_oranges
```

`@instructions`
- Dodelite promenljivoj `my_oranges` vrednost 6.
- Dodajte promenljive `my_apples` i `my_oranges` i prikažite rezultat.
- Dodelite rezultat tako što ćete sabrati `my_apples` i `my_oranges` novoj promenljivoj `my_fruit`.

`@hint`
`my_fruit` je zbir `my_apples` i `my_oranges`. Možete da koristite operator `+` da biste ih sabrali i `<-` da biste dodelili dobijenu vrednost promenljivoj `my_fruit`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Dodelite vrednost promenljivima my_apples i my_oranges
my_apples <- 5
# Saberite ove dve promenljive
# Napravite promenljivu my_fruit
```

`@solution`
```{r}
# Dodelite vrednost promenljivima my_apples i my_oranges
my_apples  <- 5
my_oranges <- 6
# Saberite ove dve promenljive
my_apples + my_oranges
# Napravite promenljivu my_fruit
my_fruit <- my_apples + my_oranges
```

`@sct`
```{r}
test_object("my_apples", incorrect_msg = "Ukucajte komandu da biste dodelili vrednost 5 promenljivoj `my_apples`.")
test_object("my_oranges", incorrect_msg = "Ukucajte komandu da biste dodelili vrednost 6 promenljivoj `my_oranges`.")
test_output_contains("my_apples + my_oranges",
                     incorrect_msg = "Proverite da li ste ispisali rezultat sabiranja promenljivih `my_apples` i `my_oranges`. Primer koda u opisu daje odgovor na ovo pitanje!")
msg <- "Da li ste koristili `my_fruit <- my_apples + my_oranges` da biste kreirali `my_fruit` promenljivu?"
test_object("my_fruit", undefined_msg = msg, incorrect_msg = msg)
success_msg("Odlično! Velika prednost promenljivih je njihova ponovna korišćenost. Ako dodelite vrednost 12 umesto vrednosti 5 promenljivoj `my_apples` i ponovo pokrenete skriptu, `my_fruit` će se takođe automatski ponovo izračunati. Nastavite sa sledećom vežbom.")
```

---

## Jabuke i pomorandže

```yaml
type: NormalExercise
key: 915fcc7c99
xp: 100
skills: 1
```

Common knowledge tells you not to add apples and oranges. But hey, that is what you just did, no :-)? The `my_apples` and `my_oranges` variables both contained a number in the previous exercise. The `+` operator works with numeric variables in R. If you really tried to add "apples" and "oranges", and assigned a text value to the variable `my_oranges` (see the editor), you would be trying to assign the addition of a numeric and a character variable to the variable `my_fruit`. This is not possible.

`@instructions`
- Click 'Submit Answer' and read the error message. Make sure to understand why this did not work.
- Adjust the code so that R knows you have 6 oranges and thus a fruit basket with 11 pieces of fruit.

`@hint`
You have to assign the numeric value `6` to the `my_oranges` variable instead of the character value `"six"`. Note how the quotation marks are used to indicate that `"six"` is a character.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Assign a value to the variable my_apples
my_apples <- 5 
# Fix the assignment of my_oranges
my_oranges <- "six" 
# Create the variable my_fruit and print it out
my_fruit <- my_apples + my_oranges 
my_fruit
```

`@solution`
```{r}
# Assign a value to the variable my_apples
my_apples <- 5  
# Fix the assignment of my_oranges
my_oranges <- 6
# Create the variable my_fruit and print it out
my_fruit <- my_apples + my_oranges 
my_fruit
```

`@sct`
```{r}
test_error(incorrect_msg = "You can do this by setting the `my_oranges` variable to a numeric value, not a string!")
test_object("my_apples", incorrect_msg = "Make sure that `my_apples` still contains `5`.")
test_object("my_oranges", incorrect_msg = "Make sure that `my_oranges` is equal to `6`.")
test_object("my_fruit", incorrect_msg = "The value of `my_fruit` is not correct. It should be 11, the sum of `my_apples` and `my_oranges`.")
test_output_contains("my_fruit", incorrect_msg = "Don't remove the line that prints out `my_fruit`.")
success_msg("Awesome, keep up the good work! Continue to the next exercise.")
```

---

## Osnovni tipovi podataka u R

```yaml
type: NormalExercise
key: 0f23107394
xp: 100
skills: 1
```

R works with numerous data types. Some of the most basic types to get started are:

- Decimal values like `4.5` are called **numerics**.
- Natural numbers like `4` are called **integers**. Integers are also numerics.
- Boolean values (`TRUE` or `FALSE`) are called **logical**.
- Text (or string) values are called **characters**.

Note how the quotation marks on the right indicate that "some text" is a character.

`@instructions`
Change the value of the:

- `my_numeric` variable to `42`.
- `my_character` variable to `"universe"`. Note that the quotation marks indicate that `"universe"` is a character.
- `my_logical` variable to `FALSE`.

Note that R is case sensitive!

`@hint`
Replace the values in the editor with the values that are provided in the exercise. For example: 
`my_numeric <- 42` assigns the value 42 to the variable `my_numeric`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Change my_numeric to be 42
my_numeric <- 42.5
# Change my_character to be "universe"
my_character <- "some text"
# Change my_logical to be FALSE
my_logical <- TRUE
```

`@solution`
```{r}
# Change my_numeric to be 42
my_numeric <- 42
# Change my_character to be "universe"
my_character <- "universe"
# Change my_logical to be FALSE
my_logical <- FALSE
```

`@sct`
```{r}
test_object("my_numeric", incorrect_msg = "Have you correctly changed the declaration of `my_numeric` so it contains the value 42?")
test_object("my_character", incorrect_msg = "Have you correctly changed `my_character` to `\"universe\"`? Don't forget the quotes!")
test_object("my_logical", incorrect_msg = "Have you correctly changed `my_logical` to `FALSE`? All letters of `FALSE` should be capitalized!")
success_msg("Great work! Continue to the next exercise.")
```

---

## Koji tip podataka?

```yaml
type: NormalExercise
key: 99b549229d
xp: 100
skills: 1
```

Do you remember that when you added `5 + "six"`, you got an error due to a mismatch in data types? You can avoid such embarrassing situations by checking the data type of a variable beforehand. You can do this with the `class()` function, as the code on the right shows.

`@instructions`
Complete the code in the editor and also print out the classes of `my_character` and `my_logical`.

`@hint`
The code that prints the data type of `my_numeric` is already included; do a similar things for `my_character` and `my_logical`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```
