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

Unfortunately writing programs for such an accelerator-based supercomputer is very complicated. And existing programs can't benefit from accelerators without major changes. Weather forecasting models are very large and complex, with around a million lines of code. Rewriting such a program is extremely difficult and time consuming.

## So what's hindering progress?

The holy grail is to develop a software technology that can automatically change legacy programs to make them suitable to the new, accelerator-based supercomputers. Many research groups, [including my own](https://www.nextplatform.com/2015/05/18/fpgas-held-back-in-hpc-but-hope-on-the-horizon/), are working on such approaches.

There is however a huge gap between a research proof-of-concept and a ready-for-use product and it takes considerable investment to bridge this gap. Unfortunately, a funding gap exists in this area: on the one hand, creating a product from a research proof-of-concept is not core research and can therefore not be funded by the Research Councils or through EU research funding. On the other hand, as there is no perceived commercial value in such a product (because the potential marked is very small), commercial funding is not an option.

## Imagine

So imagine that the UK took a more joined-up view with investment to speed up the adoption of research. In the case of weather forecasting, this would help to minimize the impact on people and the economy of severe weather events like we experienced recently. It would be a thousandfold return on the investment.

<!--
note: For even finer-grained local simulations, which would for example take into account the effect of the buildings in a city, resolutions of a few meters and time steps of a few hundredths of a second are necessary. This would require the model to compute a million times more data points than for the hundred-metres model and thus would require a billion times more computations than for the current model.
-->
