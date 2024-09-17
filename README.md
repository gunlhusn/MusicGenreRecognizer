<h2>Problem formulation</h2>
The aim of the current project is to build music genre classifier that would be able to differentiate between five following genres: classical, dance, pop, rap, rock based on different track characteristics (acousticness, danceability, duration, energy, instrumentalness, key, liveness, mode, speechiness, tempo, valence). 

<h2>EDA and data preprocessing</h2>
For the current project we decided to generate a database with the help of Spotipy (Python library for the Spotify Web API). For all mentioned genres we chose several dedicated playlists from Spotify and extracted audio features for all tracks labeling each with relevant genre. As a result, we had around 3200 datapoints with more than 600 per genre. After initial generation we drop all repeating rows, make sure values are numeric and there are no missing/null values in the database. We do five-number summary to make sure values are within reasonable range. Furthermore, we analyze feature correlation with genres and other features, allowing us to determine high correlation between “loudness”/ “energy” and high negative correlation between “loudness”/”acousticness” attributes and drop redundant “loudness”. After all mentioned preprocessing we finalize this part by performing MinMax scaling.
  
<h2>Training</h2>
We chose three ensemble models (Random Forest, Gradient Boosting, XGBOOST) for the current project, performing excessive hyperparameter tuning with the help of GridSearchCV allowing us to reach around 80% accuracy on each of them. In order to get more insight about how well models performed, we calculated such crucial estimators as precision, recall, f1-score and confusion matrix. 

<h2>Testing</h2>
There is a script for manual check of arbitrary track. In order to see what prediction our models make for any song one should run the last code block and then login into Spotify account with the given credentials (login: aiproject4296@gmail.com, password: AiProjectTeam8User) in the automatically popped out window. Then, a unique song identifier(URI) should be inputted into the console.

Example URI for JID – Sistanem track: spotify:track:6QwJurtbHqyeVda0fhWV2B


