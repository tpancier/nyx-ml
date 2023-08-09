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

<br/>

## Architecture

<img width="638" alt="NYX architecture" src="https://github.com/community/community/assets/19897750/f3144d68-703f-45b0-ac10-726bd3098dd7">

<br/>

## Machine Learning Model


The dataset used in the model came from the individuation data. To mitigate the cold start problem, a survey was sent to 200 people in 5 countries, with individuation questions about them and about a close friend. This early data allowed EDA (exploratory data analysis) in preparation for the model.

Jupyter notebook was used for data wrangling and EDA.

**EDA summary**:

The following chart indicates under each archetype the number of people with the same archetype as their friend (orange) and people with different archetype than their friend (blue). The larger orange bars show that “similars attract” and led us to further exploration of similarity algorithms.
<br/><br/>

Chart 1: Archetype similarity among friends

<img width="844" alt="Archetypes similarity" src="https://github.com/community/community/assets/19897750/be7ba1d3-ff9f-4fcb-b425-73198f6dc399">

<br/><br/>


Chart 2: Similarity matrix with all participants and friends data

<img width="481" alt="Similarity matrix" src="https://github.com/community/community/assets/19897750/1b22a055-7bb8-4a2a-bfd9-3243bfcec88c">

<br/><br/>

This similarity matrix was created to test if cosine similarity would be a good initial measure of “friendship match”. This chart shows, with the yellow diagonal line, that people that are friends have in general a higher cosine similarity.

<br/><br/>

Chart 3: histogram of cosine similarity between friends

<img width="734" alt="Histogram similarity" src="https://github.com/community/community/assets/19897750/6839b26a-102b-4f38-be58-120204f777fb">

<br/><br/>

For the first model iteration the ML algorithm chosen for the model was NearestNeighbors. It was based on the EDA results, on the fact that the survey brought positive labels but there was no efficient way to collect negative labels and also based on the training data size we had available to start.


The research and EDA have shown that not all traits have the same importance for a first acquaintance match. Several experiments were done with different weights and a set of weights was chosen based on the experiments results.

<br/><br/>

**Beta Test**

Later, another survey was done with web3 users as part of a beta test group. In this survey there was no question about a friend. The goal was to get feedback on the data collection process. Below some stats based on their response.

<br/>

Personality drivers: Intellect is the main driver for the beta test group

<img width="225" alt="Drivers" src="https://github.com/community/community/assets/19897750/7db6f921-995d-4ae1-b201-bc817b027e7d">

<br/>

Personality archetype: Visionary is the main archetype in the beta test group, followed by Mentor and Idealist. 

<img width="294" alt="Archetype" src="https://github.com/community/community/assets/19897750/ec7e8a85-68a1-4733-8c00-b0eb2c75dd95">

<br/>

Personality traits: Adventurer is the main trait for the beta test group, followed by Agnostic and Ally.

<img width="358" alt="Traits" src="https://github.com/community/community/assets/19897750/780a68d6-6498-44a3-9197-fed2b3bbc5d5">




