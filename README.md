# Email-Spam-Classifier Using Flask

# Introduction
Developing an efficient email spam classifier using machine learning to enhance inbox filtering and prioritize user communication.

# Dataset
In my dataset they are two types of mails "Spam mail" and "Ham mail" spam mail is labled as '1' and ham mails as '0'

# Dependencies

- Numpy
- Pandas
- Matplotlib
- Flask
- Scikit-learn
- Seaborn

# Data Preparation

- Load the email data from the "emails.csv" file into a Pandas DataFrame using `pd.read_csv("/content/emails.csv")`.
- Separate the text content (`X`) and the spam label (`y`) from the DataFrame: `X = data['text'].values` and `y = data['spam'].values`.
- Split the data into training and testing sets using `train_test_split`: `X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)`.
- Use CountVectorizer to convert the text data into a numerical format: `cv = CountVectorizer()` and `x_train = cv.fit_transform(X_train)`.
- Train the Naive Bayes classifier (`MultinomialNB`) using the transformed training data: `nb = MultinomialNB()` and `nb.fit(x_train, y_train)`.

# Using Flask

This Flask web application loads a pre-trained Naive Bayes spam classification model from a pickled file ("Naive_model.pkl"). Upon receiving a user input through a form submission on the home page ("/"), it extracts the entered email text, makes predictions using the loaded model, and then displays the predicted output on a separate page ("show.html"). The application utilizes Flask's functionality for rendering templates and handling HTTP requests. The server runs in debug mode when executed as the main module, making it suitable for development purposes. The prediction result is integrated into the rendered template to provide feedback to the user.

- Webpage link http://127.0.0.1:5000




