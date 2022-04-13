---
title: "NFL Play Call Prediction with Recurrent Neural Networks"
author: "Joseph Williams Director"
date: "Spring 2022"
---

## Abstract

The prevelance of data analytics in professional sports has significantly increased over the last 20 years. First popularized in the book (later turned movie) *Moneyball: The Art of Winning an Unfair Game (2003)*, the use of advanced analytics is now mainstream in the four major U.S. sports and abroad. In the National Football League (NFL), millions of dollars are invested into analytics departments and data is being used to drive decision making at every level of a team's operation. American Football, in particular, presents a case where leveraging statistical methods to learn and predict the opposition's tendencies provides a substantial competitive advantage. Specifically, the defensive team can improve its strategy by accurately predicting the offensive team's play call (whether the play is a "run" or a "pass"). To this end, many prior works have implemented popular machine learning algorithms. However, none of the works encountered have treated the data as sequential. In Football, the offensive team's current play call is dependent upon the sequence of plays called before; thus, there is a time series component to the data. In this work, we explore the ability of sequential deep learning models to predict NFL play calls. Namely, we compare the performance of Recurrent Neural Networks (RNNs) and Long Short Term Memory (LSTM) networks to baseline models (Logistic Regression and Gradient Boosted Decision Trees). Using classification accuracy and area under the receiver operating characteristic curve (ROC_AUC) as metrics, we found that sequential models out-perform baseline models. 

## 1. Introduction 

### 1.1 Background

Football is a "dead ball" sport; meaning the gameplay is divided into a sequence of instances called plays. In between plays, the two teams on either side of the ball are allowed to position themselves and prepare. Given this nature, there is an immense amount of pre-snap ("snap" indicates the start of a play) strategy determining which players are on the field, where each player should position themself, and what each player should do once the play begins. Akin to moving pieces on a chessboard, the coaching staff decides their team's best course of action based on the moves they anticipate their opponent to make. In this work we assume the perspective of the defensive team's coaching staff for any given play. For regular plays (i.e. not a kick-off, punt, or field goal attempt), there is a binary option for the type of play the offensive team can do; either a pass or a run. We gain a strategical advantage by accurately predicting this outcome. As a simplistic example, if we know the play is a pass we can put more of our defensive players into pass coverage and if we know the play is a run we can have more players attack the line of scrimmage. 

There are a number of indicators that can inform play call prediction. Certain personnel packages (groups of players from various positions) and formations of the offensive team are more associated with either passes or runs. Unfortunately, the NFL does not publicly release data containing specific personnel or formations. However, there exists a general binary indicator for the formation; whether the play was from the "shotgun" (the Quarterback lines up a few yards back from the center) or "under-center" (the Quarterback lines up directly behind the center). Beyond this, there is the in-game context of the current play. This includes the down (how many plays can be used to gain the required distance), the distance (the amount of yards needed to gain in order to keep the ball), the score differential, the amount of time remaining, etc. The conditions of these factors all incentivize the offensive team to use either a run or a pass play. For example, if an offensive team is losing by a lot of points with little time remaining in the game, they are incentivized to run passing plays because they can gain more yards using less time. Lastly, tendencies of the offensive team can be studied. This is done by accumulating the relative frequency of passes to runs for the offensive team (pass to run ratio) as well as how successful they are at either passing or running (average yards gained per run or pass play).

A defensive coach in the NFL uses experience and intuition to convert the above information into an educated guess for the offensive teams play call. In this work, we replace this with labeled data points from the entirety of a single NFL season (2019-2020) and feed this information into a supervised machine learning algorithm. A supervised machine learning task involves teaching a computer to learn the underlying patterns relating the response variable to the predictors. If the model can discern information about the predictors and response well enough, its predictions should generalize well to unseen instances. Among the most popularly used algorithms in this domain is the field of deep learning. Deep learning uses artificial neural networks (ANNs) that loosely resemble a biological brain. They contain networks of individual neurons or nodes, each with its own activation signal, that is each capable of sending and receiving signals to other nodes through weights. Types of deep learning algorithms vary in complexity and structure. In this work, we examine recurrent neural networks (RNNs) and their variant, long short term memory (LSTM) networks. These kinds of networks were originally designed for speech and text recognition because of their ability to learn sequential patterns. They were selected for study in this work due to the sequential nature of NFL play calls.  

### 1.2 Problem Statement






































