# Project Title
Building AI cource project

Final project for the Building AI course

## Summary

Data-driven recipe recommendation system using web-scraped recipe data (including but not limited to data like ingredients, health facts, etc.) and user’s historical preference.

Cooking is a hobby for some and a major problem for others, but deciding what to cook and the real challenge. This inspired me to want to create a system that can recommend recipes based on ingredient suggestions.

## Background

Cooking is a hobby for some and a major problem for others, but deciding what to cook and the real challenge. This inspired me to want to create a system that can recommend recipes based on ingredient suggestions.

## How is it used?

Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?


## Data sources and AI methods

All data is stored on a Google Drive at https://tinyurl.com/yajzjchs. We scraped a total of 61,880 recipes, and parsed the set of ingredients to produce a set of unique ingredients. We then passed these unique ingredients through a unit conversion pipeline, resulting in a total of 37,765 ingredient features (each ingredient has a 'mass' feature and a 'volume' feature). Due to the dimensionality issues, we have processed the data several times using feature selection, and we have uploaded the smaller representations.

    recipe_info.csv: the recipe 'name', 'type' (e.g., Breakfast and Brunch), and 'subtype' (e.g., Pancake Recipes). Also contains a column for each GMM-produced cluster labels. For each of the feature-reduced datasets, there are cluster results for 4, 25, and 54 components.
    recipes_normalized_varFS.csv: the set of ingredients, normalized, for all recipes. There are a total of 7,580 features in this processed set after performing Variance Threshold feature selection, using the mean normalized variance for all features.
    recipes_normalized_varFS_incrementalPCA100.csv: set of ingredients transformed to a size of (61880, 100) by using incremental PCA in batches of 100.
    recipes_normalized_varFS_incrementalPCA1000.csv: set of ingredients transformed to a size of (61880, 1000) by using incremental PCA in batches of 1000.
    recipes_normalized_varFS_extraTrees912.csv: set of ingredients chosen by ensemble classifier (classifying subtype) with a size of (61880, 912)
    recipes_normalized_varFS_extraTrees186.csv: set of ingredients chosen again (from previously derived set) by an identical ensemble classifier, with a size of (61880, 186)
    recipes_encoded100.csv: recipe dimensions were reduced from 7000+ to 100 using a stacked autoencoder of hidden layers 1000 and 100. Input Set: recipes_normalized_varFS.csv. Output Size: (61880, 100)
    recipes_encoded1000.csv: recipe dimensions were reduced from 7000+ to 1000 using a one-hidden-layer autoencoder. Input Set: recipes_normalized_varFS.csv. Output Size: (61880, 1000)

Where does your data come from? Do you collect it yourself or do you use data collected by someone else?
If you need to use links, here's an example:
[Twitter API](https://developer.twitter.com/en/docs)

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 


## Acknowledgments

* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
