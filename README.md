# nyx-ml

A few definitions before we start:

**Individuation**: process to achieve a sense of individuality that separates the individual from others.<br/>
**EI (encoded individuation)**: on-chain agnostic protocol we've developed to allow for individuation in virtual worlds.<br/>
**Soul**: As users completed their E.I, they received an NFT ERC-721 token called “Soul”, with their personality traits represented on the token art.
<br/><br/>

## Intro

NYX was born in 2018 as an exploration of possible ways to create Encoded Individuation (E.I), a psychometrics construct that is fast, precise and unique in decoding the Self. Its core foundations are Jungian theory (including AION), Psychometrics, and machine learning as the underlying tech.

For more information about the research behind this project: [nyxxp medium](https://nyxxp.medium.com/this-is-a-research-on-possible-ways-to-digitize-the-human-soul-using-jungian-theory-psychometrics-ead7f7ad4632)

This repository contains the code and summary for the ML section. Other repositories for this project:
Generative Art: 
node.js: https://github.com/tennydesign/nyx
<br/><br/>


Jupyter notebooks in this repository:
EDA: XXXX
ML model: XXX


## Architecture



## Machine Learning Model


The dataset used in the model came from the individuation data. To mitigate the cold start problem, a survey was sent to 200 people in 5 countries, with individuation questions about them and about a close friend. This early data allowed EDA (exploratory data analysis) in preparation for the model.

Jupyter notebook was used for data wrangling and EDA.

**EDA summary**:

The following chart indicates under each archetype the number of people with the same archetype as their friend (orange) and people with different archetype than their friend (blue). The larger orange bars show that “similars attract” and led us to further exploration of similarity algorithms.


Chart 1: Archetype similarity among friends





Chart 2: Similarity matrix with all participants and friends data





This similarity matrix was created to test if cosine similarity would be a good initial measure of “friendship match”. This chart shows, with the yellow diagonal line, that people that are friends have in general a higher cosine similarity.


Chart 3: histogram of cosine similarity between friends



For the first model iteration the ML algorithm chosen for the model was NearestNeighbors. It was based on the EDA results, on the fact that the survey brought positive labels but there was no efficient way to collect negative labels and also based on the training data size we had available to start.


The research and EDA have shown that not all traits have the same importance for a first acquaintance match. Several experiments were done with different weights and a set of weights was chosen based on the experiments results.

**Beta Test**

Later, another survey was done with web3 users as part of a beta test group. In this survey there was no question about a friend. The goal was to get feedback on the data collection process. Below some stats based on their response.


Personality drivers: Intellect is the main driver for the beta test group



Personality archetype: Visionary is the main archetype in the beta test group, followed by Mentor and Idealist. 



Personality traits: Adventurer is the main trait for the beta test group, followed by Agnostic and Ally.





