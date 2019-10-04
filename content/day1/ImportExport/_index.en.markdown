---
date: "2016-04-09T16:50:16+02:00"
title: Import Data inot R
output: 
  learnr::tutorial
weight: 8
---

It’s the first big hurdle to dealing with data in R. 

You are most likelly to have looked at, organised and examined your data files in Excel.

Opening data in R is fairly simply, but organising it for analysis might take some thought and consideration. You'll guess that it is possible to use **File | Import Dataset** menu option in RStudio to import your data, however we’re going to do it the proper way with a command.

There are many packages that let R import all types of data, but with the restriction of time in this bootcamp we will focus on `CSV` files and you can try to explore the rest for yourself.

Comma separated files are the most common way to save spreadsheets that don’t require a licenced, usually not free program to open. Importing `CSV` is part of base R and you can use `read.csv()` function to do so. 


##### `read.csv()`

Let us go to <https://data.gov.rs/> Serbian open data portal. In particular, let us try to access ["Подаци из Огласа јавних набавки са Портала јавних набавки"](https://data.gov.rs/sr/datasets/podatsi-iz-oglasa-javnikh-nabavki-sa-portala-javnikh-nabavki/) and import this data to R.

We are not going to download it onto our local computers, but rather we will import it to R directly from the web using the link.


```r
df_csv <- read.csv("http://portal.ujn.gov.rs/OpenD/Tekuci_Mesec.csv", stringsAsFactors = FALSE)
head(df_csv, 10)
```

```
##    SifraNabavke
## 1       2447521
## 2       2453300
## 3       2458195
## 4       2479362
## 5       2479757
## 6       2479911
## 7       2483293
## 8       2488566
## 9       2495880
## 10      2495922
##                                                                                                    NazivDokumenta
## 1                                                                                          Прехрамбени  производи
## 2                                                                      Набавка добара - рачунарска опрема 10/2019
## 3  Екскурзија ученика трећег, четвртог, шестог, седмог и осмог разреда и настава у природи ученика другог разреда
## 4                                     ЗАКУП АУТОДИЗАЛИЦЕ И АУТОПЛАТФОРМЕ, ПАРТИЈА 1 - ЗАКУП АУТОДИЗАЛИЦЕ M2019-18
## 5                                                                                                       Ауто гуме
## 6                            Ангажовање стручне куће за безбедност на раду и против пожарне заштите, ЈНМВ 41-2019
## 7                                                                        Настава у природи  у пролеће 2020.године
## 8                              Набавка ужине за децу у подручним групама - радна 2019/20. год. - Поновни поступак
## 9                                                  Екскурзија и настава у природи за ученике ОШ "Коста Абрашевић"
## 10                                                  Екскурзија ученика ОШ '' Дубрава '' у школској 2019/20 години
##                                          NazivNarucioca MaticniBroj
## 1               Установа Геронтолошки центар Младеновац    17413805
## 2  Факултет инжењерских наука Универзитета у Крагујевцу     7151314
## 3                                ОШ "Доситеј Обрадовић"     7141106
## 4                       ЈКП Зеленило и гробља Смедерево    20782633
## 5                  ЈАВНО КОМУНАЛНО ПРЕДУЗЕЋЕ "СТАНДАРД"     7208324
## 6                              Здравствени центар Врање     7205805
## 7                        ОШ''Николај Велимировић''Шабац     7120451
## 8                                 ПУ "Чаролија" Ћићевац     7291825
## 9                                  ОШ "КОСТА АБРАШЕВИЋ"     7004010
## 10                          Основна школа '' Дубрава ''     6950841
##          PIB IdMesto IdOpstina IdVrstaPostupka
## 1  101477704  704458     70173               1
## 2  101576499  718980     70645               1
## 3  101521949  733083     70947               1
## 4  107333843  740527     71099               7
## 5  100630696  717657     70602               7
## 6  100548147  711306     70432               7
## 7  101896237  746606     71269               7
## 8  101510485  744328     71196               7
## 9  100169916  791083     70211               1
## 10 100407439  717657     70602               7
##                                                                                                                                                PredmetNabavke
## 1                                                                                                                                            храна, намирнице
## 2                                                                                                                 рачунарска опрема (хардверска и софтверска)
## 3  услуге копненог саобраћаја (осим услуга железничког саобраћаја ), укључујући и услуге превоза у оклопљеним возилима и курирске услуге (осим превоза поште)
## 4                                                                       техничка опрема за обављање делатности (уређаји, машине, апарати, механизација и сл.)
## 5                                                                                                                                                 друга добра
## 6                                                                                                                                                друге услуге
## 7                                                                                                                                   услуге хотела и ресторана
## 8                                                                                                                                            храна, намирнице
## 9                                                                                                                                                друге услуге
## 10                                                                                                            услуге у областима рекреације, културе и спорта
##    VrstaPredmeta
## 1          добра
## 2          добра
## 3         услуге
## 4          добра
## 5          добра
## 6         услуге
## 7         услуге
## 8          добра
## 9         услуге
## 10        услуге
##                                                                                                                                                                                   OpstiRecnikNabavki
## 1              Свеже живинско месо,Месни производи,Припремљена и конзервисана риба,Животињска или биљна уља и масти,Млеко,Млинарски производи, скроб и скробни производи,Разни прехрамбени производи
## 2                                                                                                                                                                      Рачунарска опрема и материјал
## 3                                                                                                                                                                       Услуге организације путовања
## 4                                                                                                                                                                Изнајмљивање дизалица са оператером
## 5                                                                                                                                                                        Гуме за тешка и лака возила
## 6                                                                                                                                                           Услуге у области здравства и безбедности
## 7  Услуге друмског превоза,Најам возила за превоз путника са возачем,Пратеће и помоћне услуге превоза; услуге превозних агенција,Услуге путничких агенција и тур-оператера и услуге помоћи туристима
## 8                                                                                                                                                              Храна, пиће, дуван и сродни производи
## 9                                                                                                                                                                       Услуге организације путовања
## 10                                                                                                                                                                      Услуге организације путовања
##                                   KontaktOsoba       Telefon
## 1                              Новаковић Ђорђе    0118230865
## 2  Марија Петровић, службеник за јавне набавке   034/330-196
## 3                           Весна Димитријевић     012223371
## 4                                  Милица Бера   064-8476886
## 5                                Tasić Emilija   019/731-112
## 6                             Весна Стојановић     017427832
## 7                               Весна Павловић 350-483 (015)
## 8                                Zvezdan Babic   037/811-354
## 9                              ВЕРИЦА ПЕТРОВИЋ       8041792
## 10                             Татјана Алексић   019/739-606
##    DatumPoslednjeIzmene IdDelatnost IdOblikOrg IdOblikSvoj IdKategorija
## 1   2019-10-01 13:14:13        8730         85           5            6
## 2   2019-10-01 09:03:04        8542         85           5            5
## 3   2019-10-01 11:16:50        8520         85           5            5
## 4   2019-10-01 12:39:21        9603         17           5            7
## 5   2019-10-01 13:35:25        3600         17           5            7
## 6   2019-10-02 08:33:48        8610         85           5            3
## 7   2019-10-01 11:58:27        8520         85           5            5
## 8   2019-10-01 15:10:02        8510         85           5            5
## 9   2019-10-02 15:52:54        8520         85           5            5
## 10  2019-10-01 07:44:09        8520         85           5            5
##    PozivZaPodnosenjePonuda PozivZaPodnosenjePrijava
## 1                        1                        0
## 2                        1                        0
## 3                        1                        0
## 4                        2                        0
## 5                        1                        0
## 6                        1                        0
## 7                        0                        0
## 8                        1                        0
## 9                        1                        0
## 10                       1                        0
##    ObavestenjeOSistemuDinamickeNabavke PozivZaUcesceNaKonkursZaDizajn
## 1                                    0                              0
## 2                                    0                              0
## 3                                    0                              0
## 4                                    0                              0
## 5                                    0                              0
## 6                                    0                              0
## 7                                    0                              0
## 8                                    0                              0
## 9                                    0                              0
## 10                                   0                              0
##    ObavestenjeOPriznavanjuKvalifikacije
## 1                                     0
## 2                                     0
## 3                                     0
## 4                                     0
## 5                                     0
## 6                                     0
## 7                                     0
## 8                                     0
## 9                                     0
## 10                                    0
##    ObavestenjeOPriznavanjuKvalifikacijeURestriktivnomPostupku
## 1                                                           0
## 2                                                           0
## 3                                                           0
## 4                                                           0
## 5                                                           0
## 6                                                           0
## 7                                                           0
## 8                                                           0
## 9                                                           0
## 10                                                          0
##    PodaciOObjaviIDodeliUgovora ObavestenjeOZakljucenomOkvirnomSporazumu
## 1                            0                                        0
## 2                            0                                        0
## 3                            0                                        0
## 4                            0                                        0
## 5                            0                                        0
## 6                            0                                        0
## 7                            0                                        0
## 8                            0                                        0
## 9                            0                                        0
## 10                           0                                        0
##    ObavestenjeOZakljucenomUgovoru ObavestenjeORezultatuKonkursa
## 1                               0                             0
## 2                               0                             0
## 3                               0                             0
## 4                               0                             0
## 5                               0                             0
## 6                               0                             0
## 7                               0                             0
## 8                               0                             0
## 9                               0                             0
## 10                              0                             0
##    ObavestenjeOObustaviPostupkaJavneNabavke
## 1                                         0
## 2                                         1
## 3                                         0
## 4                                         1
## 5                                         0
## 6                                         0
## 7                                         0
## 8                                         0
## 9                                         0
## 10                                        0
##    PodaciOIzmeniUgovoraOJavnojNabavci KonkursnaDokumentacija
## 1                                   0                      1
## 2                                   0                      1
## 3                                   0                      1
## 4                                   0                      1
## 5                                   0                      1
## 6                                   0                      1
## 7                                   0                      1
## 8                                   0                      1
## 9                                   0                      1
## 10                                  0                      1
##    ObavestenjeOProduzenjuRoka PregovarackiBezPonuda
## 1                           0                     0
## 2                           0                     0
## 3                           1                     0
## 4                           0                     0
## 5                           0                     0
## 6                           0                     0
## 7                           0                     0
## 8                           0                     0
## 9                           0                     0
## 10                          0                     0
##    ObavestenjeOZastitiPrava MisljenjeUpraveJN
## 1                         0                 0
## 2                         0                 0
## 3                         0                 0
## 4                         0                 0
## 5                         0                 0
## 6                         0                 0
## 7                         0                 0
## 8                         0                 0
## 9                         0                 0
## 10                        0                 0
##    OdlukaOPriznavanjuKvalifikacije OdlukaOIskljucenjuKandidata
## 1                                0                           0
## 2                                0                           0
## 3                                0                           0
## 4                                0                           0
## 5                                0                           0
## 6                                0                           0
## 7                                0                           0
## 8                                0                           0
## 9                                0                           0
## 10                               0                           0
##    OdlukaODodeliUgovora OdlukaODodeliOkvirnogSporazuma
## 1                     7                              0
## 2                     0                              0
## 3                     2                              0
## 4                     0                              0
## 5                     1                              0
## 6                     1                              0
## 7                     0                              0
## 8                     1                              0
## 9                     0                              0
## 10                    0                              0
##    ObavestenjeOPonistenjuPostupka OdlukaOObustaviPostupka
## 1                               0                       0
## 2                               0                       1
## 3                               0                       0
## 4                               0                       1
## 5                               0                       0
## 6                               0                       0
## 7                               0                       0
## 8                               0                       0
## 9                               0                       0
## 10                              0                       0
##    OdlukaONastavkuPostupka OdlukaKomisijeOZakljucenjuUgovora
## 1                        0                                 0
## 2                        0                                 0
## 3                        0                                 0
## 4                        0                                 0
## 5                        0                                 0
## 6                        0                                 0
## 7                        0                                 0
## 8                        0                                 0
## 9                        0                                 0
## 10                       0                                 0
##    ObavestenjeOPriznavanjuKvalifikacijeOpste
## 1                                          0
## 2                                          0
## 3                                          0
## 4                                          0
## 5                                          0
## 6                                          0
## 7                                          0
## 8                                          0
## 9                                          0
## 10                                         0
##                                                                Link
## 1  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2447521
## 2  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2453300
## 3  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2458195
## 4  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479362
## 5  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479757
## 6  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479911
## 7  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2483293
## 8  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2488566
## 9  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2495880
## 10 http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2495922
```

The other way is to download it and to save it to your working directory.

Let us download ["Регистар повлачћених произвођача електричне енергије"](https://data.gov.rs/s/resources/registar-povlashtshenikh-proizvodjacha-elektrichne-energije/20170221-142908/povlasceni.csv) and save it on your computers.

Make sure you save the file into your R-Project working directory before you ask R to execute the following

```
df_csv <- read.csv("poslodavci.csv", stringsAsFactors = FALSE)
```

What do you think about this dataset?

##### readr::read_csv()

Just so you can see how easy it is to use other packages for importing data into R the code below illustrates the use of read_csv().

```
## If you don't have readr installed yet, uncomment and run the line below
#install.packages("readr")
library(readr)
df_csv <- read_csv("poslodavci.csv")
df_csv
```

You can use R with appropriate packages to access other data formats. For example `jsonlite` package for `json` files or `foreign` package for `SPSS` data files. Try to look through the help of the packages you've been introduced to and discover other options.


## YOUR TURN 👇

1)	Open source software such as R and Git are extensively used in data science. Can you research the tools that are available for data science, both open and closed source. Write a short brief about the pros and cons for both types of software.

2)	Investigate the importance of open source data and identify where open source data can readily be found on the Internet. 

3) Write an explanation of the benefits of open source models for policy makings by local authorities and governments in general.


-----------------------------
© 2019 Tatjana Kecojevic
