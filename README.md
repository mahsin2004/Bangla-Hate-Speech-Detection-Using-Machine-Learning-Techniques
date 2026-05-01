# Bengali Hate Speech Dataset

**Project Update:** The latest version of this project and related machine learning techniques can be found at: [Bangla-Hate-Speech-Detection-Using-Machine-Learning-Techniques](https://github.com/mahsin2004/Bangla-Hate-Speech-Detection-Using-Machine-Learning-Techniques)

## Warning!
The data and lexicons contain contents that are racist, sexist, homophobic, and offensive in many different ways. Datasets are collected and subsequently annotated only for research related purposes. Besides, authors don't take any liability if some statements contain very offensive and hatred statements that are either directed towards a specific person or entity, or generalized towards a group. Therefore, please use it with your risk. 

## Bengali Hate Speech Dataset
The bengali_hate_dataset is used in our paper "DeepHateExplainer: Explainable Hate Speech Detection in Under-resourced Bengali Language". 

### Collection of raw dataset
Bengali articles were collected from numerous sources from Bangladesh including a Bengali Wikipedia dump, Bengali news articles (Daily Prothom Alo, Daily Jugontor, Daily Nayadiganta, BBC bangla), books, blogs, sports portal, and social media (Twitter, Facebook pages and groups, LinkedIn). Facebook pages (e.g., celebrities, athletes, sports, and politicians) and newspaper sources were scrutinized because composedly, they have about 50 million followers, and many opinions, hate speech and review texts come or spread out from there. Altogether, our raw text corpus consists of 250 million articles.  

### Hate speech data annotation
The Bengali Hate Speech Dataset categorized into political, personal, geopolitical, religious, and gender abusive hates. However, our empirical study and linguist analysis observe that distinguishing personal from gender abusive hate is often not straightforward, as they often semantically overlap. To justify this, our study observes that distinguishing personal hates from gender abusive hates was very challenging. Often statements that express hatred statements towards a person commonly used Bengali words that are directed mostly towards women. Therefore, we treated the gender abusive hate statements as personal hate, followed by categorizing the samples into political, personal, geopolitical, and religious hate.

During the data collection, we follow the bootstrap approach for the data collection, where specific types of texts containing common slurs and terms, either directed towards a specific person or entity or generalized towards a group, are only considered. Texts were collected from Facebook, YouTube comments, and newspapers. Three annotators - a linguist, a native Bengali speaker, and an NLP researcher participated in the annotation process. To reduce possible bias, unbiased contents are supplied to the annotators and each label is assigned based on a majority voting on the annotator's independent opinions. To evaluate the quality of the annotations and to ensure the decision based on the criteria of the objective, we measure inter-annotator agreement w.r.t Cohen's Kappa statistic.

### Statistics and frequent words
Following figure shows the most frequently used terms that express different types of hates in Bengali: 

<p align="center"><img src="final_words_cloud_hate.png?" width="400" height="350"></p>

The dataset has 5,698 samples, which has the following distribution: 

| Personal hate | Political hate | Religious hate | Geopolitical hate |
| ------------- | ------------- | ------------- | ------------- |
| 2189           |     814      |     957       |     1738      |

Following columns describe different types of hate (i.e., label and target columns in the [CSV file](https://github.com/mahsin2004/Bangla-Hate-Speech-Detection-Using-Machine-Learning-Techniques/blob/main/final_bengali_hate_speach_dataset.csv)):
| Label | Target | Description |
| --------------------------| ------ | --------------------------|
| Personal Hate | 0 | Hatred comment towards or directed towards a specific person |
| Political Hate | 1 | Hatred comment towards or directed towards a political group or person |
| Religious Hate | 2 | Hatred comment towards or directed towards a specific religion |
| Geopolitical Hate | 3 | Hatred comment towards or directed towards a specific country, continent, or regions |

### Machine Learning Results
We have evaluated the dataset using standard Machine Learning techniques (Linear SVM and Logistic Regression) with TF-IDF vectorization and SMOTE for class balancing. The results are as follows:

- **Linear SVM:** ~78% Accuracy
- **Logistic Regression:** ~75% Accuracy

For more details, please refer to the `demo.ipynb` notebook.

Following are a few examples of Bengali hate speech, either directed or generalized towards a specific person, entity, or a group: 
<p align="left"><img src="final_hate.png?" width="850" height="400"></p>

  






