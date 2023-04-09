# FIFA 22 Predictions: Predicting Salary Based on Player Metrics

Central Question: What are the most valuabe skills a football player can have? What positions do clubs value the most? What is the best route a young player can take in order to maximize earnings as a professional football player?

![image](https://user-images.githubusercontent.com/97577565/230793644-37f6ba10-db06-4f91-810e-c975534b922f.png)

# Data Source
The data source was downloaded from kaggle, using the URL below. Out of the zip file provided, I used the FIFA 22 excel file for my data.
https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset

# Data Description
The data source has 25 columns and 19232 rows originally. After cleaning, the data has 23 columns and 17,041 rows. 

The features are:
Overall - The overall rating (between 0-100) that a player has attributed to him. 

Potential - This is the rating of potential talent that a player has based on metrics age. This takes into account the amount of playing time a player has in actual games.

Value_Eur - This is the amount of money in euros a player makes on their current contract.

Age - Age of player in 2022

Height - Height in centimeters

Weight - Weight in kilograms

Club Team Id - Identifies which club in Europe the player plays for.

League Level - Identifies which level league (1-5), the player plays in. 

Club Position - What position each player plays.

![image](https://user-images.githubusercontent.com/97577565/230793602-3df05e23-9fff-4c7c-a868-ebad594e7c76.png)

Note - I decided to keep Club and League information, because predicting what league / club a player could play for is an interesting data point.

Work rate - This measures stamina and consistency of play.

Body Type - Labels a player based on body demension (height, weight), and categorizes them between "stocky" and "lean".

Pace - Average a player runs divided by speed.

Shooting - Measures number of quality shots versus shots taken.

Passing - Percentage of successful passes a player makes versus unsuccessful passes (that are intercepted / go out of bounds)

Dribbling = Percentage of possession a player can maintain while he has the ball.

Defending - Measures defensive abilities.

Attacking Finishing - Number of shots divided by goals scores.

Skill Dribbling - A skill number assigned to a player based on dribbling ability.

SKill curve - Measures player's ability to curve shots and passes successfully.

Movement Acceleration - Measures "burst" while on and off the ball.

Mentality Aggression - Measures incidents in the game when player attacks goal.

Defending Marking Awareness - Measures a player's ability to mark defenders on set pieces and during live action.


# Some Interesting Insights

Age Matters:
![image](https://user-images.githubusercontent.com/97577565/230793498-6661b348-7126-4463-9981-828ba47dfdb5.png)

The players who earn the most money are between 23-30 years old.  After 31, the salaries drop off significantly. Young players with potential see their value rise significantly around 21 years old.

Dribbling and Passing Matter more than Shooting and Defending

![image](https://user-images.githubusercontent.com/97577565/230793703-90a1933f-ce08-4c43-9455-42a3135de18e.png)

There is a strong correlation between a player's dribbling skills, passing skills, and how much they earn. Moreso than other metrics, these are the top skills that clubs are looking for in players.

Position Matters

![image](https://user-images.githubusercontent.com/97577565/230793956-57340c1e-6938-4d2b-b5ff-83624397eeb0.png)

By far, the highest paid position is center forward. Clubs value players who can play midfield and attack as a forward. This requires high levels of dribbling, passing, and a high attacking mindset metric. 

# Model
I tried 4 different regression models to fit onto my data: Linear Regression, Decision Tree, Bagged Tree, and Random Forest. I tuned all of the models except for the Linerar Regression model since the metrics for that model were significantly lower than the other 3.

The best model was the tuned Random Forest Model. The mean average error - which predicts the difference between the actual and predicted values - shows about a $142K euro difference in salary predictions. Considering that average salary of all players in the data set is 2,965,082 euros ($3,259,959 US dollars), a difference of $142K is reasonable enough to predict.

The mean squared error - which just finds the squared difference of the MAE - isn't a valuable metric for this data set, considering that there are a high number of substitutes and reserve players who make significantly less than the positioned (full time) players.

The best metric to determine efficieny of the model is R2 - which determines how much variance can be explained by the data - in this case it is 98%.

![image](https://user-images.githubusercontent.com/97577565/230793810-83b3bac1-8611-4612-ad14-89d08053078a.png)

# Recommendations
If you are an aspiring football player or an organization looking for young talent here is some advice:

1) Focus your training on dribbling and passing. Professional clubs value players with those skills more so than flashy goal scorers. Your defensive skills, while important, can only get you into the lower quartile of salary earners.

2) Position, position, position - Professional clubs value center forwards FAR more than any other position. If you are deciding on what position you want to play, and are interested in pursuing a professional (or even an ameture) career - then tryout for CF positions as much as possible. However, if you are less interested in earning the highest salary, and just want to join a professional team, them the #1 and #2 positions that clubs carry are substitutes and reserve players. These positions are generally given to top players in lower leagues or ameture leagues.
