A test quarto document
================
Damian Oswald
13. Oktober 2023

# Machen wir einen Titel

Hier können wir schreiben, was auch immer wir wollen. Quarto ist ein
Publiziersystem, welches sich besonders gut für technische Berichte
eignet. Wir können direkt im Dokument Quellcode schreiben und diesen
ausführen.

``` r
print("Hello, World!")
```

    [1] "Hello, World!"

## Python geht auch!

Dabei sind wir jedoch nicht auf eine Programmiersprache limitiert. Wir
können z.B. auch Python benützen.

``` python
print(1 + 5)
```

    6

# Und was ist mit Tabellen?

Mit einem Label können wir Tabellen über das gesamte Dokument
referenzieren – zum Beispiel die [Tabelle 1](#tbl-swiss).

<div id="tbl-swiss">

|              | Fruchtbarkeit | Landwirtschaft | Prüfung | Bildung | Katholisch | Kindersterblichkeit |
|:-------------|--------------:|---------------:|--------:|--------:|-----------:|--------------------:|
| Courtelary   |          80.2 |           17.0 |      15 |      12 |       9.96 |                22.2 |
| Delemont     |          83.1 |           45.1 |       6 |       9 |      84.84 |                22.2 |
| Franches-Mnt |          92.5 |           39.7 |       5 |       5 |      93.40 |                20.2 |
| Moutier      |          85.8 |           36.5 |      12 |       7 |      33.77 |                20.3 |
| Neuveville   |          76.9 |           43.5 |      17 |      15 |       5.16 |                20.6 |
| Porrentruy   |          76.1 |           35.3 |       9 |       7 |      90.57 |                26.6 |

Tabelle 1: Diese Tabelle zeigt Daten zur Kindersterblichkeit von 47
westschweizer Gemeinden aus dem 19. Jahrhundert.

</div>
