
# Football Analytics with Deep Learning and Computer Vision
> **_Acknowledgment:_** 
> > [!Acknowledgment]
> As a fresh data scientist in the field of computer vision, I would like to thank **Hamza Boulahia** ([@hmzbo](https://www.github.com/hmzbo)) for giving me the first step to move forward.


# Project Overview: 

The aim of this project is to create a web-based application that automates the analysis of football games using deep learning and computer vision techniques. The application provides meaningful insights that can help in decision-making processes.

The web application allows users to upload football game footage, and in turn, detects players, referees, and the ball, predicts the players' teams based on team colors, and maps player and ball movements onto a tactical field.

# Features: 
1. **Player, Referee, and Ball Detection**:
Identify and track all players, referees, and the ball during the match.
2. **Team Prediction**:
Automatically predict teams by analyzing predefined team colors and comparing them to detected players' color palettes.
3. **Tactical Map Representation**:
Visualize player and ball positions on a tactical map, which helps in understanding the game's dynamics.
4. **Ball Movement Tracking**:
Track the ball’s movement throughout the game and calculate meaningful statistics such as ball possession rates.
6. **Object Tracking Statistics**:
Generate statistics such as:
   - Ball possession rate.
   - Players' traveled distances.
   - Average speed of players and the ball.

# Detailed Functionality

## 1. Object Detection
The object detection model detects players, referees, and the ball. You can visualize these detections in real-time as the video plays.

## 2. Team Prediction
To predict teams, color palettes are extracted from each player’s detected image. These color palettes are compared to predefined team colors using LAB color space, as it closely matches human color perception. This helps in accurately assigning players to their respective teams.

## 3. Tactical Map Representation
Keypoints are detected and used to calculate the homography matrix, which maps the video frame's key points to positions on a tactical field. This allows accurate visualization of player and ball movements.

## 4. Ball Tracking
The system tracks the ball's movement throughout the video, and various statistics such as ball possession and ball trajectory are displayed on the tactical map.

# Challenges Faced

### Player Tracking
Ensuring that the system accurately tracks players as they move in and out of the video frame.

### Tactical Map Accuracy
Achieving high accuracy in tactical map representation by using videos with minimal camera movement.

### Class Imbalance
The dataset has an imbalance in the number of ball instances, leading to lower recall for the ball class. This can be improved by collecting more ball-specific data or by using data augmentation techniques.

# Algorithms Used

## Team Prediction
- **Clustering Algorithms**: Initially, K-Means and DBScan were tested for clustering players based on features like CNN-extracted features and color palettes. However, due to poor performance, the team prediction model was simplified to a rule-based system. The system now compares the extracted player color palette to predefined team colors using Euclidean distance in the LAB color space.

## Homography Transformation
The homography matrix is calculated to map detected key points from the video frame onto the tactical map. This transformation is key for aligning video coordinates with the tactical representation.

# Future Improvements

- Improve ball detection and tracking by increasing the size and diversity of the dataset or applying advanced data augmentation techniques.
- Enhance the efficiency of the application, particularly in team prediction and tactical map rendering, to provide real-time feedback.
- Implement more advanced tracking algorithms to better handle occlusions and players exiting/reentering the video frame.

## Application Workflow

1. **Video Input:**  
   Users can upload a football game video as input.

2. **Object Detection:**  
   The system detects football players, referees, and the ball using a pre-trained deep learning model.

3. **Team Prediction:**  
   The color palette of each player is extracted, and team assignment is done by comparing this palette with predefined team colors.

4. **Tactical Map Generation:**  
   The detected positions of players and the ball are projected onto a tactical map using a homography matrix.

5. **Tracking and Statistics:**  
   The ball's movement is tracked, and key statistics like ball possession and player distance are computed.


## Installation & How to use?

Steps:
1. Clone the repository using the command
   ```bash
   git clone https://github.com/Hmzbo/Football-Analytics-with-Deep-Learning-and-Computer-Vision.git 
2. Install the required libraries listed in the file `requirement.txt`
   ```bash
   pip install -r requirements.txt

5. Start the application:
   ```bash
   streamlit run main.py
## Application Architecture


![workflow diagram](https://github.com/khawla12-op/Footbal_Analytics_with_DL_CV/blob/main/workflow%20diagram.png)
