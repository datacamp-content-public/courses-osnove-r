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

Osnovni koncept statističkog programiranja su **varijable**. 

Varijabla nam omogućava da dodelimo vrednost (npr 4) ili objekat (npr opis funkcije) u R. Kasnije možete koristi naziv varijable da biste iskoristili vrednost ili objekat koji je dodeljen toj varijabli. 

Možete dodeliti vrednost 4 varijabli `moja_var` pomoću komande

```
moja_var <- 4
```

`@instructions`
Over to you: complete the code in the editor such that it assigns the value 42 to the variable `x` in the editor. Click 'Submit Answer'. Notice that when you ask R to print `x`, the value 42 appears.

`@hint`
Look at how the value 4 was assigned to `my_variable` in the exercise's assignment. Do the exact same thing in the editor, but now assign 42 to the variable `x`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Assign the value 42 to x
x <- 
# Print out the value of the variable x
x
```

`@solution`
```{r}
# Assign the value 42 to x
x <- 42
# Print out the value of the variable x
x
```

`@sct`
```{r}
test_object("x", undefined_msg = "Make sure to define a variable `x`.",
            incorrect_msg = "Make sure that you assign the correct value to `x`.") 
success_msg("Good job! Have you noticed that R does not print the value of a variable to the console when you did the assignment? `x <- 42` did not generate any output, because R assumes that you will be needing this variable in the future. Otherwise you wouldn't have stored the value in a variable in the first place, right? Proceed to the next exercise!")
```

---

## Dodeljivanje vrednosti promenljivima (2)

```yaml
type: NormalExercise
key: c5944b90eb
xp: 100
skills: 1
```

Suppose you have a fruit basket with five apples. As a data analyst in training, you want to store the number of apples in a variable with the name `my_apples`.

`@instructions`
- Type the following code in the editor: `my_apples <- 5`. This will assign the value 5 to `my_apples`.
- Type: `my_apples` below the second comment. This will print out the value of `my_apples`.
- Click 'Submit Answer', and look at the console: you see that the number 5 is printed. So R now links the variable `my_apples` to the value 5.

`@hint`
Remember that if you want to assign a number or an object to a variable in R, you can make use of the assignment operator `<-`. Alternatively, you can use `=`, but `<-` is widely preferred in the R community.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Assign the value 5 to the variable my_apples
# Print out the value of the variable my_apples
```

`@solution`
```{r}
# Assign the value 5 to the variable my_apples
my_apples <- 5
# Print out the value of the variable my_apples
my_apples
```

`@sct`
```{r}
test_object("my_apples", 
            undefined_msg = "Please make sure to define a variable `my_apples`.",
            incorrect_msg = "Make sure that you assign the correct value to `my_apples`.")
test_output_contains("my_apples", incorrect_msg = "Have you explicitly told R to print out the `my_apples` variable to the console?")
success_msg("Great! Continue to the next exercise!")
```

---

## Dodeljivanje vrednosti promenljivima (3)

```yaml
type: NormalExercise
key: 1c1bd25045
xp: 100
skills: 1
```

Every tasty fruit basket needs oranges, so you decide to add six oranges. As a data analyst, your reflex is to immediately create the variable `my_oranges` and assign the value 6 to it. Next, you want to calculate how many pieces of fruit you have in total. Since you have given meaningful names to these values, you can now code this in a clear way: 

```
my_apples + my_oranges
```

`@instructions`
- Assign to `my_oranges` the value 6.
- Add the variables `my_apples` and `my_oranges` and have R simply print the result.
- Assign the result of adding `my_apples` and `my_oranges` to a new variable `my_fruit`.

`@hint`
`my_fruit` is just the sum of `my_apples` and `my_oranges`. You can use the `+` operator to sum the two and `<-` to assign that value to the variable `my_fruit`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Assign a value to the variables my_apples and my_oranges
my_apples <- 5
# Add these two variables together
# Create the variable my_fruit
```

`@solution`
```{r}
# Assign a value to the variables my_apples and my_oranges
my_apples  <- 5
my_oranges <- 6
# Add these two variables together
my_apples + my_oranges
# Create the variable my_fruit
my_fruit <- my_apples + my_oranges
```

`@sct`
```{r}
test_object("my_apples", incorrect_msg = "Keep the line that assigns 5 to `my_apples`.")
test_object("my_oranges", incorrect_msg = "Keep the line that assigns 6 to `my_oranges`.")
test_output_contains("my_apples + my_oranges",
                     incorrect_msg = "Make sure to print out the result of adding `my_apples` and `my_oranges`. The code example in the description already gives away the answer to this instruction!")
msg <- "Have you used `my_fruit <- my_apples + my_oranges` to create the `my_fruit` variable?"
test_object("my_fruit", undefined_msg = msg, incorrect_msg = msg)
success_msg("Nice one! The great advantage of doing calculations with variables is reusability. If you just change `my_apples` to equal 12 instead of 5 and rerun the script, `my_fruit` will automatically update as well. Continue to the next exercise.")
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
