# Group-Project

1. Which hotel has the most reviews?
```SELECT DISTINCT hotel_name,
   MAX(total_number_of_reviews) as max
   from datasets.hotel_reviews 
GROUP BY 1
ORDER BY max DESC
```

Hotel Da Vinci = 16670
 

2. What is the average of total negative reviews' word counts?
```select avg(review_total_negative_word_counts)
from datasets.hotel_reviews
```
18.539450263505888


3. What is the average of total positive reviews' word counts?
```select avg(review_total_positive_word_counts) from  datasets.hotel_reviews
```
17.77645820164502


4.Which hotels have the top rating? Show the top 10.
```SELECT hotel_name, average_score
FROM datasets.hotel_reviews 
GROUP BY hotel_name,average_score 
ORDER BY average_score DESC 
```
Hotel_name - average_score
Ritz Paris - 9.8
Hotel The Serras - 9.6
H tel de La Tamise Esprit de France - 9.6
Haymarket Hotel - 9.6
41 - 9.6
H10 Casa Mimosa 4 Sup - 9.6
Hotel Casa Camper - 9.6
Taj 51 Buckingham Gate Suites and Residences - 9.5
Ham Yard Hotel - 9.5


5.Which hotels have the worst rating? Show the top 10.
```SELECT hotel_name, average_score 
FROM datasets.hotel_reviews 
GROUP BY hotel_name,average_score
ORDER BY average_score ASC
```
hotel_name,average_score ORDER BY average_score ASC
Hotel_name - average_score
Hotel Liberty - 5.2
Hotel Cavendish - 6.4
Savoy Hotel Amsterdam - 6.4
The Tophams Hotel - 6.6
Best Western Maitrise Hotel Edgware Road - 6.6
Commodore Hotel - 6.7
Ibis Styles Milano Palmanova - 6.7
Bloomsbury Palace Hotel - 6.8
Villa Eugenie - 6.8
Gainsborough Hotel - 6.9


6.Which hotels had the most negative reviews in the summertime (June-Aug)? Show top 10.
```SELECT hotel_name, 
COUNT(negative_review) as negative 
FROM datasets.hotel_reviews 
WHERE NOT negative_review= 'No Negative' AND review_date BETWEEN '6/1/17' AND '8/31/17'
GROUP BY hotel_name
ORDER BY negative DESC
LIMIT 15
```
Hotel_name - negative
Britannia International Hotel Canary Wharf - 964
Strand Palace Hotel - 764
Park Plaza Westminster Bridge London - 760
Copthorne Tara Hotel London Kensington - 602
DoubleTree by Hilton Hotel London Tower of London - 596
Grand Royale London Hyde Park - 586
Holiday Inn London Kensington - 564
Hilton London Metropole - 525
Hotel Da Vinci - 499
Park Plaza London Riverbank - 489


7.Which hotels had the most positive reviews in the summertime (June-Aug)? Show top 10.
```SELECT hotel_name,
COUNT(positive_review) as positive 
FROM datasets.hotel_reviews 
WHERE NOT positive_review= 'No Positive' AND review_date BETWEEN '6/1/17' AND '8/31/17'
GROUP BY hotel_name
ORDER BY positive DESC
LIMIT 15
```
Hotel_name - positive

Britannia International Hotel Canary Wharf - 925
Park Plaza Westminster Bridge London - 895
Strand Palace Hotel - 818
DoubleTree by Hilton Hotel London Tower of London - 730
Copthorne Tara Hotel London Kensington - 658
Grand Royale London Hyde Park - 623
The Student Hotel Amsterdam City - 568
Holiday Inn London Kensington - 553
Intercontinental London The O2 - 548
Hotel Da Vinci - 539
 

8.Which countries left the most negative reviews?
```SELECT reviewer_nationality,count(negative_review)
as negative
FROM datasets.hotel_reviews
where NOT negative_review='No Negative'  
GROUP BY reviewer_nationality
order by  negative desc
```
reviewer_nationality
negative
United Kingdom
186272
United States of America
25087
Australia
15451
Ireland
11149
United Arab Emirates
8227
Saudi Arabia
7468
Netherlands
6725
 

9.Which countries left the most positive reviews?

```SELECT reviewer_nationality,count(positive_review)
as positive
FROM datasets.hotel_reviews
where NOT  positive_review = 'No Positive'
GROUP BY reviewer_nationality
order by  positive desc
```
reviewer_nationality
positive
United Kingdom
229515
United States of America
33525
Australia
20716
Ireland
13770
United Arab Emirates
9468
Saudi Arabia
8178
Netherlands
8177


10.Which hotels get the most reviews that a particular reviewer has given?
```SELECT hotel_name,MAX(total_number_of_reviews_reviewer_has_given) max
FROM datasets.hotel_reviews
GROUP BY hotel_name
order by max DESC
LIMIT 5
```
hotel_name
max
Rainers Hotel Vienna
355
Mercure Paris Bastille Saint Antoine
330
Park Plaza Victoria London
315
Best Western Palm Hotel
315
The Grosvenor
315



