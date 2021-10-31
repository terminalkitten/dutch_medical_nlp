# Dutch medical NLP
This repository contains a collection of Dutch medical texts which were used for [domain-adaptive pretraining](http://dx.doi.org/10.18653/v1/2020.acl-main.740) to pretrain Dutch medical language models (see [here](https://huggingface.co/basarends/dutch_medical_robbert/) and [here](https://huggingface.co/basarends/dutch_medical_mbert/)).

## Data sources
For creation of this dataset, we used medical texts from the Dutch College of General Practitioners' [guidelines](https://richtlijnen.nhg.org) and [monthly magazine](https://henw.org), and from [richtlijnendatabase.nl](https://richtlijnendatabase.nl), a collection of medical guidelines from hospital specialties.

## Pre-processing
Because the texts were mainly professional guidelines, they are scientifically oriented and therefore contain English passages and references to scientific articles. To make the model more suited to clinical applications, we used the [FastText language identification model](https://arxiv.org/abs/1607.01759) to detect and remove English sentences. We used pattern matching to remove article citations. Furthermore, preprocessing included removing whitespace and organizing the texts in a structure of one sentence per line.

## Text statistics
Source                 | Number of words | Size
---------------------- | --------------- | ------
NHG standaarden        | 17.7M           | 127 MB
Richtlijnendatabase    | 43.6M           | 323 MB
Huisarts en wetenschap | 23.7M           | 161 MB

## Acknowledgement
This research was performed by Bas Arends as a student researcher at the [Amsterdam University Medical Centers, location AMC](https://www.amsterdamumc.org/en/research.htm), supervised by Miguel Rios Gaona.