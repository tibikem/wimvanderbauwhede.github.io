---
layout: article
title: "Képzeljük el, ha jobbak lennének az időjárás-előrejelzéseink"
date: 2018-03-04
modified: 2018-03-04
tags: [ időjárás, gyorsítók, szuperszámítás ]
excerpt: "Jelenlegi időjárás-előrejelzéseink egyidőben nagyon fejlettek és mégsem elég jók. Korábbi és pontosabb figyelmeztetések korlátozhatják hasonló események kárát."
current: "Képzeljük el, ha jobbak lennének az időjárás-előrejelzéseink"
current_image: better-forecasts_1600x600.jpg
comments: false
toc: false
categories: articles
image:
  feature: better-forecasts_1600x600.jpg
  teaser: better-forecasts_400x150.jpg
  thumb: better-forecasts_400x150.jpg
---

Az elmúlt napok megmutatták, hogy a jelenlegi időjárás-előrejelzéseink egyidőben nagyon fejlettek és mégsem elég jók. Kevés fihgyelmeztetés volt a nagy mennyiségű hóesésről amely megbénította az infrastruktúránkat. Korábbi és pontosabb figyelmeztetések korlátozhatják hasonló események kárát(£470m-ra értékelték fel a napi kárt csak az utazásí zavarok miatt). Ezenkívül az ilyen események jövőbeli valószínűségére vonatkozó jobb hosszú távú előrejelzések elősegíthetik a beruházásokat és az infrastruktúra és szolgáltatások tervezését: fektesenek-e be a Tanácsoknak több hókoptróba; kell-e a vasúttársaságoknak befektetniük a hálózat ellenállóbbá tételére az extrém hideg időjárással szemben; hogyan lehetne folyamatosan működtetni a sürgősségi szolgálatokat ilyen szélsőséges körülmények között stb.?

## Tehát miért nem jobbak az előrejelzéseink??

### Felbontás

Az egyik fő ok az, hogy az időjárás-előrejelző számítógépes modellek felbontása jelenleg még elég durva. Például a MetOffice előrejelzési modell, amelyet a világ legjobbjai között tartanak számon, 1,5 km-es négyzetekre osztja az Egyesült Királyságot a legnagyobb felbontásában, azaz a szimuláció egyetlen átlagolt értéket hoz létre bárhol ezen az 1,5 km x 1,5 km-es területen. A legrövidebb távú előrejelzés időbeli felbontása 50 másodperc.

Ezzel szemben a helyi időjárás pontos szimulációjához száz méteres felbontás és körülbelül másodperces idő lépték szükségesek. Ehhez egy ezerszer erősebb szuperszámítógépre lenne szükség, mint a jelenlegi amit a MetOffice használ.

### Sebesség és teljesítmény

<!--
A számítógépek természetesen folyamatosan gyorsulnak, de körülbelül tíz évvel ezelőtt alapvető változás történt abban, _ahogyan_ gyorsabbak lettek. Ez nagyon jól el van magyarázva a híres cikkben ["The Free Lunch Is Over"](http://www.gotw.ca/publications/concurrency-ddj.htm) Herb Sutter által, de az eredmény az lett, hogy a számítógépeket nehezebb lett programozni, és a régebbi programok valójában _lassabban_ fognak futni az újabb számítógépeken.
-->

 A fő probléma a szuperszámítógépekkel az, hogy _nagyon sok_ energiát fogyasztanak. A jelenlegi MetOffice szuperszámítógép 2.7 MW energiát fogyaszt. Egy ezerszer gyorsabb szuperszámítógép 2.7GW-ot igényelne, amely kétszer több energia mint amit az Egyesült Királyság legnagyobb atomeróműje állít elő, Hinkley Point B.

Az energiafogyasztás csökkentése érdekében az új szuperszámítógépek speciális hardvert kezdenek használni névileg [_gyorsítók_](https://www.techradar.com/news/world-of-tech/future-tech/accelerating-supercomputing-power-1223031). Már a világ [leggyorsabb](https://www.top500.org/lists/2017/11/) és [energiahatékonyabb](https://www.top500.org/green500/lists/2017/11/) szuperszámítógépei is ezt a technológiát használják.

### Programozási kihívások

Sajnos nagyon bonyolult programokat írni egy ilyen gyorsító alapú szuperszámítógéphez. A meglévő programok pedig nagyobb változások nélkül nem élvezhetik a gyorsítókat. Az időjárás-előrejelzési modellek nagyon nagyok és összetettek, mintegy millió kódsorral. Egy ilyen program átírása rendkívül nehéz és időigényes.

## Tehát mi akadályozza a haladást?

A szent grálnak olyan szoftvertechnológiát kell kifejlesztenie, amely automatikusan megváltoztathatja a régi programokat, hogy alkalmassá váljanak az új, gyorsító alapú szuperszámítógépekre. Számos kutatócsoport, [köztük sajátjaim](https://www.nextplatform.com/2015/05/18/fpgas-held-back-in-hpc-but-hope-on-the-horizon/) is dolgoznak ilyen megközelítéseken.

Óriási különbség van azonban a kutatás igazolása és a használatra kész termék között, és ennek a hiányosságnak a megszüntetéséhez jelentős beruházásokra van szükség.Sajnos ezen a területen finanszírozási hiány van: egyrészt terméket létrehozni kuitatás koncepciójának igazolásából nem számít alapkutatásnak, ezért nem finanszírozható sem a Kutatási Tanácsok, sem pedig az európai uniós kutatási finanszírozás révén. Másrészt, mivel egy ilyen termékben nincs érzékelt kereskedelmi érték (mivel a megjelölt potenciál nagyon kicsi), a kereskedelmi finanszírozás sem egy opció.

## Képzeljék

Tehát képzelje el, hogy az Egyesült Királyság a kutatás elfogadásának felgyorsítása érdekében a befektetésekkel összevontabb álláspontot képvisel. Az időjárás-előrejelzés esetében ez segítene minimalizálni az olyan súlyos időjárási események emberre és a gazdaságra gyakorolt ​​hatását, mint ahogyan azt a közelmúltban tapasztaltuk. Ez a beruházás ezerszeres megtérülése lenne.

<!--
megjegyzés: Még finomabb részletekű helyi szimulációkhoz, amelyek például figyelembe veszik a városban lévő épületek hatását, néhány méteres felbontásra és néhány száz másodperces időbeli léptékre van szükség. Ehhez a modellnek milliószor több adatpontot kellene kiszámítania, mint a száz méteres modell esetében, és így milliárdszor több számítást igényelne, mint a jelenlegi modell.
-->
