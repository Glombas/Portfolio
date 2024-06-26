This is the workflow for the analysis of Fast Food Nutrition Menu data publicly available on Kaggle. This data was uploaded by Joakim Arvidsson [link](https://www.kaggle.com/datasets/joebeachcapital/fast-food?resource=download)

# About Dataset

Nutritional values, including Calories and Micro-nutrients from six of the largest and most popular fast food restaurants:

McDonald's
Burger King
Wendy's
Kentucky Fried Chicken (KFC)
Taco Bell
Pizza Hut

Attributes include: Calories, Calories from Fat, Total Fat, Saturated Fat, Trans Fat, Cholesterol, Sodium, Carbs, Fiber, Sugars, Protein, and Weight Watchers Points (where available).

## I decided to ask myself and answer the following questions:

### 1. How many options does each restaurant offer in total?
### 2. What is the average amount of calories per meal in each restaurant and in all restaurants altogether?
### 3. Upon establishing the average calories, which restaurant contains the highest amount of meals with calories amount > average across restaurants? 
### 4. When selecting 5 top meals with the highest calories, do the top 5 come from the same restaurant?

These questions will all be answered using _Excel/Google Sheets_ and visualised in a _Tableau_ dashboard. [link](url)


First glance at the data in Google Sheets show duplicate rows for several meals and extra whitespace characters.
![image](https://github.com/Glombas/Portfolio/assets/42178209/bdc154fa-b1e0-4660-9181-32b03861090f)


I removed these based on the suggestions as they would affect the results.

I then filtered out any meals that contained the word "Limited" or "limited" in the name as they are not a part of the regular menu. This removed 5 KFC meals.

I also removed anything with 0 or 'blank cell' calories as that would bias the statistics. This removed 98 cells (almost evenly from all restaurants).

With that, I can answer my first question...

### 1. How many options does each restaurant offer in total?

1. McDonald's (314)
2. KFC (184)
3. Taco Bell (162)
4. Burger King (159)
5. Wendy's (145)
6. Pizza Hut (74)


To answer the second question, I need to create a pivot table and calculate averages of calories per meals in each restaurant.

Setting **company** as rows and **calories** as values, I can answer the second question...

### 2. What is the average amount of calories per meal in each restaurant and in all restaurants altogether?

1. Burger King (396) +/- 265
2. Wendy's (343) +/- 194
3. Taco Bell (325) +/- 209
4. McDonald's (297) +/- 215
5. Pizza Hut (253) +/- 85
6. KFC (248) +/- 201

All restaurants average = **311**.

If we look at the **standard deviation** we see very high values, that might be, because our data also contains stuff such as **sauces, drinks, etc.** which are not a real meal, but merely an addition to one.

It would be wise to filter these out, however the range of calories in offered items is so high, that its better to keep them in as they do complete a final meal and it can spike up the amount of calories a person consumes during one sitting.

**Coffee 10-300 cal**
**Sauce 30-200 cal**


### 3. Upon establishing the average calories, which restaurant contains the highest amount of meals with calories amount > average across restaurants? 

This can be achieved with a pivot table where we filter items by condition "calories > 311".

![image](https://github.com/Glombas/Portfolio/assets/42178209/3c1e0515-a133-4dd7-8c86-0f03d351cd28)


The table then gives us the amount of options in each restaurant which has calories above average of all of them.

1. McDonald's 111
2. Burger King 86
3. Taco Bell 77
4. Wendy's 76
5. KFC 47
6. Pizza Hut 18

### 4. When selecting 5 top meals with the highest calories, do the top 5 come from the same restaurant?

This was kind of a blind check as there is no support for this hypothesis. I just wondered what the top 5 highest calorie meals/options are:

| Company | Meal    | Calories    |
| :---:   | :---: | :---: |
| Burger King | Triple Whopper® Sandwich with Cheese   | 1220   |
| KFC | Potato Salad (Family)   | 1200   |
| Burger King | Cheddar Bacon King Sandwich   | 1190   |
| McDonald’s | Chocolate Triple Thick® Shake (32 fl oz cup)   | 1160   |
| McDonald’s | Big Breakfast with Hotcakes (Large Size Biscuit)   | 1150   |
