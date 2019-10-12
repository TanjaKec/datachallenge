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

There are many packages that let R import all types of data, and we will start by focus on `CSV` files as they are the most frequent tipe.

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
## 1       2408810
## 2       2445282
## 3       2447521
## 4       2453300
## 5       2458195
## 6       2468141
## 7       2468533
## 8       2479362
## 9       2479757
## 10      2479911
##                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      NazivDokumenta
## 1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Стручни надзор над извођењем 3 истражно-експлоатациона (ИЕ) бунара и техничка контола техничке документације неопходне за добијање експлоатационог права за потребе грејања одн. хлађења објеката социјалног и приступачног становања, у оквиру комплекса у Овчи
## 2  Предмет набавке је услуга - брокерска услуга, у смислу Закона о извозу и увозу наоружања и војне опреме ("Службени гласник РС", број 107/14), а ради спровођења послова уговарања и посредовања у уговарању, у вези са испоруком из увоза – опреме која је сходно Одлуци о утврђивању националне контролне листе наоружања и војне опреме («Сл.гласник РС» бр.42/18), категоризоване под редним бројем 11. «Електронска опрема, «свемирске летелице» и њихове компоненте које се не контролишу ни по једној другој основи на НКЛ НВО», тачка а) «Електронска опрема специјално пројектована за војну употребу и за њу специјално пројектоване компоненте» подтачка ј) "Аутоматизовани системи за командовање и контролу» НКЛ НВО, ЈН број 90/18.
## 3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            Прехрамбени  производи
## 4                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Набавка добара - рачунарска опрема 10/2019
## 5                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    Екскурзија ученика трећег, четвртог, шестог, седмог и осмог разреда и настава у природи ученика другог разреда
## 6                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               Добра-набавка  школскoг намештаја (клупе и столице)
## 7                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Набавка електричне енергије за јавну расвету
## 8                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       ЗАКУП АУТОДИЗАЛИЦЕ И АУТОПЛАТФОРМЕ, ПАРТИЈА 1 - ЗАКУП АУТОДИЗАЛИЦЕ M2019-18
## 9                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         Ауто гуме
## 10                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             Ангажовање стручне куће за безбедност на раду и против пожарне заштите, ЈНМВ 41-2019
##                                                               NazivNarucioca
## 1                Град Београд - Градска управа - Секретаријат за инвестиције
## 2  МИНИСТАРСТВО ОДБРАНЕ, СЕКТОР ЗА МАТЕРИЈАЛНЕ РЕСУРСЕ, УПРАВА ЗА СНАБДЕВАЊЕ
## 3                                    Установа Геронтолошки центар Младеновац
## 4                       Факултет инжењерских наука Универзитета у Крагујевцу
## 5                                                     ОШ "Доситеј Обрадовић"
## 6                                                 Основна школа "Свети Сава"
## 7                                                           Општинска управа
## 8                                            ЈКП Зеленило и гробља Смедерево
## 9                                       ЈАВНО КОМУНАЛНО ПРЕДУЗЕЋЕ "СТАНДАРД"
## 10                                                  Здравствени центар Врање
##    MaticniBroj       PIB IdMesto IdOpstina IdVrstaPostupka
## 1     17565800 100065430  791105     70246               4
## 2      7093608 102116082  791091     70220               4
## 3     17413805 101477704  704458     70173               1
## 4      7151314 101576499  718980     70645               1
## 5      7141106 101521949  733083     70947               1
## 6      7130139 100499692  706418     70327               7
## 7      7175221 102156105  713325     70483               1
## 8     20782633 107333843  740527     71099               7
## 9      7208324 100630696  717657     70602               7
## 10     7205805 100548147  711306     70432               7
##                                                                                                                                                                            PredmetNabavke
## 1  архитектонске услуге; инжењерске услуге; услуге урбанистичког планирања и пејзажне архитектуре; услуге техничког тестирања и анализа; услуге енергентског прегледа и енергетске услуге
## 2                                                                                                                                                                            друге услуге
## 3                                                                                                                                                                        храна, намирнице
## 4                                                                                                                                             рачунарска опрема (хардверска и софтверска)
## 5                              услуге копненог саобраћаја (осим услуга железничког саобраћаја ), укључујући и услуге превоза у оклопљеним возилима и курирске услуге (осим превоза поште)
## 6                                                                                                                                                                             друга добра
## 7                                                                                                                                                                             друга добра
## 8                                                                                                   техничка опрема за обављање делатности (уређаји, машине, апарати, механизација и сл.)
## 9                                                                                                                                                                             друга добра
## 10                                                                                                                                                                           друге услуге
##    VrstaPredmeta
## 1         услуге
## 2         услуге
## 3          добра
## 4          добра
## 5         услуге
## 6          добра
## 7          добра
## 8          добра
## 9          добра
## 10        услуге
##                                                                                                                                                                       OpstiRecnikNabavki
## 1                                                                                                       Надзор пројеката и документације (пројектантски надзор),Услуге техничког надзора
## 2                                                                                                                                                                      Одбрамбене услуге
## 3  Свеже живинско месо,Месни производи,Припремљена и конзервисана риба,Животињска или биљна уља и масти,Млеко,Млинарски производи, скроб и скробни производи,Разни прехрамбени производи
## 4                                                                                                                                                          Рачунарска опрема и материјал
## 5                                                                                                                                                           Услуге организације путовања
## 6                                                                                                                                                                       Школски намештај
## 7                                                                                                                                                                    Електрична енергија
## 8                                                                                                                                                    Изнајмљивање дизалица са оператером
## 9                                                                                                                                                            Гуме за тешка и лака возила
## 10                                                                                                                                              Услуге у области здравства и безбедности
##                                   KontaktOsoba                Telefon
## 1                               Ана Крсмановић           011/321-6037
## 2                               Мишо Симоновић 011/2059-168, 2059-019
## 3                              Новаковић Ђорђе             0118230865
## 4  Марија Петровић, службеник за јавне набавке            034/330-196
## 5                           Весна Димитријевић              012223371
## 6                                Мирјана Лазић              030421688
## 7     Дејан Вељовић  начелник Општинске управе            032-713-528
## 8                                  Милица Бера            064-8476886
## 9                                Tasić Emilija            019/731-112
## 10                            Весна Стојановић              017427832
##    DatumPoslednjeIzmene IdDelatnost IdOblikOrg IdOblikSvoj IdKategorija
## 1   2019-10-04 14:21:07        8411         73           5            8
## 2   2019-10-09 15:23:26        8422         71           5            1
## 3   2019-10-01 13:14:13        8730         85           5            6
## 4   2019-10-01 09:03:04        8542         85           5            5
## 5   2019-10-01 11:16:50        8520         85           5            5
## 6   2019-10-09 13:28:30        8520         85           5            5
## 7   2019-10-08 11:20:40        8411         71           5            8
## 8   2019-10-01 12:39:21        9603         17           5            7
## 9   2019-10-01 13:35:25        3600         17           5            7
## 10  2019-10-02 08:33:48        8610         85           5            3
##    PozivZaPodnosenjePonuda PozivZaPodnosenjePrijava
## 1                        1                        0
## 2                        0                        0
## 3                        1                        0
## 4                        1                        0
## 5                        1                        0
## 6                        1                        0
## 7                        1                        0
## 8                        2                        0
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
## 1                               1                             0
## 2                               0                             0
## 3                               0                             0
## 4                               0                             0
## 5                               0                             0
## 6                               1                             0
## 7                               0                             0
## 8                               0                             0
## 9                               1                             0
## 10                              0                             0
##    ObavestenjeOObustaviPostupkaJavneNabavke
## 1                                         1
## 2                                         0
## 3                                         0
## 4                                         2
## 5                                         0
## 6                                         0
## 7                                         0
## 8                                         1
## 9                                         0
## 10                                        0
##    PodaciOIzmeniUgovoraOJavnojNabavci KonkursnaDokumentacija
## 1                                   0                      1
## 2                                   0                      0
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
## 3                           0                     0
## 4                           0                     0
## 5                           1                     0
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
## 1                     2                              0
## 2                     0                              0
## 3                     7                              0
## 4                     0                              0
## 5                     2                              0
## 6                     1                              0
## 7                     1                              0
## 8                     0                              0
## 9                     1                              0
## 10                    1                              0
##    ObavestenjeOPonistenjuPostupka OdlukaOObustaviPostupka
## 1                               0                       1
## 2                               0                       0
## 3                               0                       0
## 4                               0                       1
## 5                               0                       0
## 6                               0                       0
## 7                               0                       0
## 8                               0                       1
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
## 1  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2408810
## 2  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2445282
## 3  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2447521
## 4  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2453300
## 5  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2458195
## 6  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2468141
## 7  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2468533
## 8  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479362
## 9  http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479757
## 10 http://portal.ujn.gov.rs/Dokumenti/JavnaNabavka.aspx?idd=2479911
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
