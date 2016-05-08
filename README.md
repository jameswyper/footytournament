# footytournament

A website for updating and publishing football (soccer) tournament scores.  The local team my kids play in have asked if I can have a go at producing one.  It will be developed in Ruby/Rails.

# Installation

To follow

# Features (planned)

Creation of an event (e.g. local tournament 2016)  
Creation of competitions within that event (U8 Boys cup, U9 Girls plate etc)  
Setup of fixtures that will create the competition  
* Group and knockout stages (knockouts will be a cheap hack)
* Ability to link across competitions e.g. group stage where 1st/2nd place go into a cup competition, 3rd/4th go into plate
* 1-leg or 2-leg round robins and knockouts
* Optionally apply various rules to determine standings e.g. Goal difference, Goals For, Head to Head, Away Goals
Entry of full time scores as the competition progresses  
Publicly viewable pages to show results and standings across all competitions  

# Design

No security on the public pages  
Simple authentication on the admin page (1 user only) PLUS a configurable URL to provide an extra layer of security

# Data model

One or more Events  
Each event has one or more Competitions  
Each competition has one or more Stage Groups  
Each Stage Group has one or more Stages  
A Stage is a set of Fixtures  
A Fixture is between two Teams (Home and Away)  
A Stage also has Progression rules associated with it (e.g. for each position in the stage what's the next competition / stage / fixture the team will play in)  

Note that to keep things simpler most of the logic will be based around "round robin" style stages, for a knockout stage we'll need to set up (e.g. for a quarter final) a Stage Group (U9 Boys Cup QF) with 4 stages each containing a single fixture (or two for a 2-legged knockout), the team finishing top (out of two) is of course the winner
