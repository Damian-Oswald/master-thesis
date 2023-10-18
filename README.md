Ein Quarto-Testdokument
================
Damian Oswald
18. Oktober 2023

# Machen wir einen Titel

Hier können wir schreiben, was auch immer wir wollen. Quarto ist ein
Publiziersystem, welches sich besonders gut für technische Berichte
eignet. Wir können direkt im Dokument Quellcode schreiben und diesen
ausführen.

``` python
print("Hello, World!")
```

    Hello, World!

## Es werden verschiedene Programmiersprachen unterstützt!

Quarto unterstützt das Ausführen verschiedener Programme in
verschiedenen Sprachen in demselben Dokument. Es könnte zum Beispiel die
Vorbereitung von Daten von einem kleinen Python-Programm gemacht werden,
wobei die Resultate dann von R eingelesen und ausgewertet werden.

Dabei sind wir jedoch nicht auf eine Programmiersprache limitiert. Wir
können z.B. auch R benützen.[^1]

``` r
sieveOfEratosthenes <- function(n){
  values <- rep(TRUE, n)
  values[1] <- FALSE
  prev.prime <- 2
  for(i in prev.prime:sqrt(n)){
    values[seq.int(2 * prev.prime, n, prev.prime)] <- FALSE
    prev.prime <- prev.prime + min(which(values[(prev.prime + 1) : n]))
  }
  return(which(values))
}
sieveOfEratosthenes(100)
```

     [1]  2  3  5  7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97

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

# Einbettung von Bildern

Auch Bilder können mühelos in ein Dokument eingebettet werden. Entweter,
sie werden direkt duch einen Code-Block erzeugt, oder sie werden extern
eingelesen. Für extern eingelesene Bilder wird die folgende Syntax
verwendet. Bilder wie zum Beispiel das
[Abbildung 1](#fig-dreizehenspecht) können über einen Schlüssel auch
referenziert werden.

<figure>
<img src="resources/dreizehenspecht.jpg" id="fig-dreizehenspecht"
alt="Abbildung 1: Normalerweise haben Spechte, wie auch die meisten anderen Vögel, insgesamt vier Zehen. Warum die vierte Zehe bei den Dreizehenspechten fehlt, ist allerdings unklar. Foto: Tom Dove" />
<figcaption aria-hidden="true">Abbildung 1: Normalerweise haben Spechte,
wie auch die meisten anderen Vögel, insgesamt vier Zehen. Warum die
vierte Zehe bei den Dreizehenspechten fehlt, ist allerdings unklar.
<em>Foto: Tom Dove</em></figcaption>
</figure>

# Formeln

Die Formel zur Lösung quadratischer Gleichungen
([Gleichung 1](#eq-quadratic)) – auch Mitternachtsformel gennant –
versetzt Schüler aus Allerwelt in Angst und Schrecken.

<span id="eq-quadratic">$$
x_1, x_2 = \frac{-b\pm\sqrt{b^2-4ac}}{2a}
 \qquad(1)$$</span>

Dafür können natürlich auch sauber formatierte Referenzen geliefert
werden ([1](#ref-zong2018deep)–[3](#ref-shyu2003novel)).

# Referenzen

<div id="refs" class="references csl-bib-body">

<div id="ref-zong2018deep" class="csl-entry">

<span class="csl-left-margin">1. </span><span
class="csl-right-inline">B. Zong, Q. Song, M. R. Min, W. Cheng, C.
Lumezanu, D. Cho, H. Chen, "Deep Autoencoding Gaussian Mixture Model for
Unsupervised Anomaly Detection" in *International Conference on Learning
Representations* (2018;
<https://openreview.net/forum?id=BJJLHbb0->).</span>

</div>

<div id="ref-samarati1998protecting" class="csl-entry">

<span class="csl-left-margin">2. </span><span
class="csl-right-inline">P. Samarati, L. Sweeney, Protecting privacy
when disclosing information: k-anonymity and its enforcement through
generalization and suppression (1998) (available at
<https://dataprivacylab.org/dataprivacy/projects/kanonymity/paper3.pdf>).</span>

</div>

<div id="ref-shyu2003novel" class="csl-entry">

<span class="csl-left-margin">3. </span><span
class="csl-right-inline">M.-L. Shyu, S.-C. Chen, K. Sarinnapakorn, L.
Chang, "A novel anomaly detection scheme based on principal component
classifier" in *Proceedings of the IEEE foundations and new directions
of data mining workshop* (IEEE Press, 2003), S. 172–179.</span>

</div>

<div id="ref-korkaric2023nationale" class="csl-entry">

<span class="csl-left-margin">4. </span><span
class="csl-right-inline">M. Korkaric, M. Lehto, T. Poiger, L. de Baan,
M. Mathis, L. Ammann, I. Hanke, M. Balmer, J. F. Blom, Nationale
Risikoindikatoren für Pflanzenschutzmittel. *Agroscope Science*. **154**
(2023), doi:[10.34776/as154g](https://doi.org/10.34776/as154g).</span>

</div>

<div id="ref-kwitt2006robust" class="csl-entry">

<span class="csl-left-margin">5. </span><span
class="csl-right-inline">R. Kwitt, U. Hofmann, Robust methods for
unsupervised PCA-based anomaly detection. *Proc. of IEEE/IST WorNshop on
Monitoring, AttacN Detection and Mitigation*, 1–3 (2006).</span>

</div>

<div id="ref-rousseeuw2018anomaly" class="csl-entry">

<span class="csl-left-margin">6. </span><span
class="csl-right-inline">P. J. Rousseeuw, M. Hubert, [Anomaly detection
by robust statistics](https://doi.org/10.1002/widm.1236). *WIREs Data
Mining and Knowledge Discovery*. **8**, e1236 (2018).</span>

</div>

<div id="ref-fedlex2018strategie" class="csl-entry">

<span class="csl-left-margin">7. </span><span
class="csl-right-inline">Schweizerische Eidgenossenschaft, Strategie für
offene Verwaltungsdaten in der Schweiz 2019-2023
(Open-Government-Data-Strategie, OGD-Strategie) (2018), (available at
<https://fedlex.data.admin.ch/eli/fga/2019/125>).</span>

</div>

<div id="ref-fedlex2023embag" class="csl-entry">

<span class="csl-left-margin">8. </span><span
class="csl-right-inline">Schweizerische Eidgenossenschaft, Bundesgesetz
über den Einsatz elektronischer Mittel zur Erfüllung von
Behördenaufgaben (2023), (available at
<https://fedlex.data.admin.ch/eli/fga/2023/787>).</span>

</div>

<div id="ref-liu2008isolation" class="csl-entry">

<span class="csl-left-margin">9. </span><span
class="csl-right-inline">F. T. Liu, K. M. Ting, Z.-H. Zhou, "[Isolation
forest](https://doi.org/10.1109/ICDM.2008.17)" in *2008 eighth ieee
international conference on data mining* (IEEE, 2008), S.
413–422.</span>

</div>

</div>

[^1]: Die primären unterstützten Programmiersprachen (welche während dem
    rendern des Dokumentes ausgeführt werden können) sind R, Python,
    Julia, und Observable JS. Für die meisten weiteren Sprachen wird die
    Syntax entsprechend erkannt und markiert, sie können jedoch nicht
    direkt ausgeführt werden.
