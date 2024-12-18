<h1 align="center">Diet Recommendation System</h1>
<div align= "center"><img src="Assets/logo_img1.png" />
  <h4>A diet recommendation web application using content-based approach with Scikit-Learn, FastAPI and Streamlit.</h4>
</div>

# Diet-Recommendation-System

## :bookmark_tabs:Table of contents

- [General info](#general-info)
- [Development](#development)
- [Technologies](#technologies)
- [Setup](#setup)

## :scroll: General info

### Motivation
In today’s modern world, people are becoming increasingly concerned about their health and lifestyle. While avoiding junk food and exercising are crucial, they are not sufficient on their own. A balanced diet is essential for maintaining good health. By tailoring meals based on factors like height, weight, and age, individuals can achieve and sustain a healthy lifestyle. A balanced diet, combined with regular physical activity, can help manage weight, reduce the risk of chronic diseases such as heart disease and cancer, and improve overall well-being.

Despite growing awareness, there is a lack of State-of-the-Art (SOTA) projects focusing on food and diet recommendation systems. Recognizing this gap, I conceived the idea of developing a content-based recommendation system powered by machine learning to address this need.

#### Future Vision

In the future, the system will evolve into a monthly subscription-based meal service that delivers nutritious, personalized meals based on user recommendations. This service would especially benefit office workers living far from their families, ensuring they receive well-balanced and nutrient-rich food conveniently.

This project not only promotes healthier eating habits but also bridges the gap between nutritional awareness and practical implementation, making a meaningful impact on the lives of busy professionals.

### What is a food recommendation engine?

A food recommendation engine using a content-based approach is an important tool for promoting healthy eating habits. This type of engine uses information about the nutritional content and ingredients of foods to make personalized recommendations to users. One of the key advantages of a content-based approach is that it takes into account an individual's dietary restrictions and preferences, such as allergies or food preferences. By providing users with tailored recommendations, a content-based food recommendation engine can help them make better choices about what to eat and improve their overall health. Additionally, by recommending a variety of healthy foods, it can also help users to discover new and nutritious options, expand their dietary horizons and overcome food boredom. All these can lead to a better and well-rounded diet, which can have a positive impact on long-term health outcomes.

### What is a content-based recommendation engine?

A content-based recommendation engine is a type of recommendation system that uses the characteristics or content of an item to recommend similar items to users. It works by analyzing the content of items, such as text, images, or audio, and identifying patterns or features that are associated with certain items. These patterns or features are then used to compare items and recommend similar ones to users.

<div align= "center"><img src="Assets/content_based_img.webp" /></div>

### Why content-based approach?

- No data from other users is required to start making recommendations.
- Recommendations are highly relevant to the user.
- Recommendations are transparent to the user.
- You avoid the “cold start” problem.
- Content-based filtering systems are generally easier to create.

### Challenges of content-based approach

- There’s a lack of novelty and diversity.
- Scalability is a challenge.
- Attributes may be incorrect or inconsistent.

## :computer:Development

### Model developement

The recommendation engine is built using Nearest Neighbors alogrithm which is an unsupervised learner for implementing neighbor searches. It acts as a uniform interface to three different nearest neighbors algorithms: BallTree, KDTree, and a brute-force algorithm based on routines in sklearn.metrics.pairwise. For our case, we used the brute-force algorithm using cosine similarity due to its fast computation for small datasets.

$$cos(theta) = (A * B) / (||A|| * ||B||)$$

### Dataset

I used Food.com kaggle dataset Data with over 500,000 recipes and 1,400,000 reviews from Food.com. Visit this [kaggle](https://www.kaggle.com/datasets/irkaal/foodcom-recipes-and-reviews?select=recipes.csv) link for more details.

### Backend Developement

The application is built using the FastAPI framework, which allows for the creation of fast and efficient web APIs. When a user makes a request to the API (user data,nutrition data...) the model is used to generate a list of recommended food similar/suitable to his request (data) which are then returned to the user via the API.

### Frontend Developement

The application's front-end is made with Streamlit. Streamlit is an open source app framework in Python language. It helps to create web apps for data science and machine learning in a short time. It is compatible with major Python libraries such as scikit-learn, Keras, PyTorch, SymPy(latex), NumPy, pandas, Matplotlib etc. For our case the front-end is composed of three web pages. The main page is Hello.py which is a welcoming page used to introduce you to my project. The side bar on the left allows the user to navigate too the automatic diet recommendation page and the custom food recommendation page. In the diet recommendation page the user can fill information about his age,weight,height.. and gets a diet recommendation based on his information. Besides, the custom food recommendation allows the user to specify more his food preferency using nutritional values.

### Deployement using Docker

#### Why Docker?

By using Docker, you can ensure that the environment in which the application is exactly the same as the environment in which it was built, which can help prevent unexpected issues and improve model performance. Additionally, Docker allows for easy scaling and management of the deployment, making it a great choice for larger machine learning projects.

#### Docker-Compose

My project is composed of different services (frontend,API). Therefore, our application should run on multiple containers. With the help of Docker-compose we can share our application using the yaml file that define the services that runs together.

### Project Architecture

<div align= "center"><img src="Assets/Architecture_diagram.png" width="600" height="400"/></div>

## :rocket: Technologies

The project is created with:

- Python: 3.10.8
- fastapi 0.88.0
- uvicorn 0.20.0
- scikit-learn 1.1.3
- Pandas: 1.5.1
- Streamlit: 1.16.0
- streamlit-echarts 1.24.1
- Numpy: 1.21.5
- beautifulsoup4 4.11.1

![](https://img.icons8.com/color/48/null/python--v1.png)![](https://img.icons8.com/color/48/null/numpy.png)![](Assets/streamlit-icon-48x48.png)![](Assets/fastapi.ico)![](Assets/scikit-learn.ico) ![](https://img.icons8.com/color/48/null/pandas.png)

## :whale: Setup

### Run it locally

#### Clone the repo

```
$ git clone https://github.com/Deepak-gautam1/Food-Point
```

### docker-compose

In the project root run:

```
$ docker-compose up -d --build
```

Then open http://localhost:8501 and enjoy :smiley:.

PS: You should have docker and docker-compose already installed

## Demo Video

Click the image below to watch the demo video:

[![Demo Video](Assets/foodpoint.png)](https://drive.google.com/file/d/1Hzd2AQR46gRUaOS3EBm9wPEpS1XMh8A4/view?usp=sharing)

<!-- https://diet-recommendation-system.streamlit.app/ -->
