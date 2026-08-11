# EduBot - Education AI Chatbot

EduBot is a JavaFX-based educational chatbot that provides interactive answers to frequently asked education-related questions.

The application uses **rule-based Natural Language Processing (NLP)** techniques to analyze user input, identify important keywords, determine the user's intent, and return a predefined educational response.

The project demonstrates Java, Object-Oriented Programming, JavaFX GUI development, NLP fundamentals, and rule-based artificial intelligence.

> **Note:** This project uses rule-based NLP rather than a trained neural-network or generative AI model. The chatbot responds using a predefined educational FAQ knowledge base.

---

# Repository Name

```text
education-ai-chatbot-javafx
```

---

# Project Structure

```text
education-ai-chatbot-javafx/
│
├── src/
│   ├── ChatbotEngine.java
│   └── EducationChatbotApp.java
│
├── README.md
└── .gitignore
```

---

# Project Objective

The main objective of this project is to create an interactive education chatbot using Java.

The chatbot can:

* Accept questions from users
* Process natural language input
* Identify keywords
* Detect the user's intent
* Match questions with frequently asked questions
* Provide educational responses
* Display conversations in a JavaFX GUI

---

# Features

* JavaFX graphical user interface
* Interactive chat window
* Text-based communication
* Rule-based NLP
* Keyword matching
* Intent detection
* Stop-word removal
* Text normalization
* Educational FAQ knowledge base
* Study-related responses
* Exam preparation responses
* Programming responses
* Java and Python responses
* Algorithm and database responses
* Project and career guidance
* Clear chat functionality

---

# Technologies Used

* Java
* JavaFX
* Object-Oriented Programming
* Collections Framework
* HashMap
* HashSet
* ArrayList
* String Processing
* Regular Expressions
* Rule-Based NLP

---

# NLP Techniques

The chatbot uses several basic NLP techniques.

## 1. Text Normalization

The chatbot converts the user's message to lowercase and removes punctuation.

For example:

```text
How Can I Learn Java?
```

becomes:

```text
how can i learn java
```

This allows the chatbot to compare words consistently.

---

## 2. Tokenization

Tokenization divides a sentence into individual words.

For example:

```text
How can I learn Java?
```

is converted into tokens such as:

```text
how
can
i
learn
java
```

The chatbot then processes these individual tokens.

---

## 3. Stop-Word Removal

Common words that provide little information are removed.

Examples include:

```text
the
is
a
an
to
of
for
i
you
can
what
how
```

For example:

```text
Can you tell me how to learn Java?
```

can be reduced to important words such as:

```text
learn
java
```

This makes keyword matching more effective.

---

## 4. Keyword Matching

The chatbot contains keyword groups for different topics.

For example, the Java intent contains:

```text
java
jdk
jvm
```

The exam intent contains:

```text
exam
exams
test
revision
prepare
```

The programming intent contains:

```text
programming
coding
program
code
```

The user's tokens are compared with these keyword groups.

---

## 5. Intent Detection

Intent detection determines what the user is asking about.

Each keyword match contributes a score to its corresponding intent.

For example:

```text
User:
How can I learn Java programming?
```

Important tokens:

```text
learn
java
programming
```

The system finds:

```text
Java intent       → 1 match
Programming intent → 1 match
```

The chatbot then selects the best matching intent according to its keyword rules.

---

## 6. Rule-Based Response Generation

After detecting the intent, the chatbot retrieves a predefined response.

For example:

```text
User:
What is an algorithm?
```

Detected intent:

```text
algorithm
```

Response:

```text
An algorithm is a step-by-step procedure used
to solve a problem or complete a particular task.
```

The responses are stored in the `ChatbotEngine` class.

---

# FAQ Topics

The chatbot currently covers:

| Topic       | Example Question                           |
| ----------- | ------------------------------------------ |
| Study       | How should I study?                        |
| Exams       | How can I prepare for exams?               |
| Programming | What is programming?                       |
| Java        | What is Java?                              |
| Python      | What is Python?                            |
| Algorithms  | What is an algorithm?                      |
| Database    | What is a database?                        |
| Projects    | How can I create projects?                 |
| Career      | How can I prepare for a technology career? |
| College     | How should I prepare for college?          |
| Assignment  | How should I complete an assignment?       |
| NLP         | What is NLP?                               |

---

# Algorithm

```text
START
  |
  v
Launch JavaFX Application
  |
  v
Create ChatbotEngine
  |
  v
Load FAQ responses
  |
  v
Load keywords and stop words
  |
  v
Display JavaFX Chat Interface
  |
  v
User enters a question
  |
  v
Normalize the text
  |
  v
Tokenize the sentence
  |
  v
Remove stop words
  |
  v
Compare tokens with keyword groups
  |
  v
Calculate intent scores
  |
  v
Select the best matching intent
  |
  +-------- No match --------+
  |                          |
  v                          v
Find FAQ response       Default response
  |                          |
  +------------+-------------+
               |
               v
       Display response
               |
               v
        Wait for next input
               |
               v
              END
```

---

# Detailed Algorithm

1. Start the JavaFX application.
2. Create an instance of `ChatbotEngine`.
3. Load the stop-word list.
4. Load the educational FAQ responses.
5. Load keywords for each intent.
6. Display the chatbot GUI.
7. Wait for the user to enter a message.
8. Read the user's message.
9. Convert the message to lowercase.
10. Remove punctuation and unnecessary characters.
11. Split the sentence into individual words.
12. Remove common stop words.
13. Compare the remaining tokens with predefined keywords.
14. Calculate a score for each possible intent.
15. Select the intent with the highest score.
16. Retrieve the response associated with that intent.
17. If no matching intent exists, display a default response.
18. Display the user's message and chatbot response in the GUI.
19. Clear the input field.
20. Wait for another question.
21. Continue until the application is closed.

---

# Code Explanation

## ChatbotEngine.java

`ChatbotEngine` is responsible for the chatbot's intelligence.

It contains:

```java
Map<String, String> responses;
```

This stores the chatbot's responses.

Example:

```text
java → Java is an object-oriented programming language...
```

It also contains:

```java
Map<String, List<String>> keywords;
```

This maps each intent to its keywords.

Example:

```text
java → java, jdk, jvm
```

---

## `normalize()`

This method converts the user's input into a consistent format.

```java
private String normalize(String text)
```

It:

* Converts text to lowercase
* Removes punctuation
* Removes extra spaces

---

## `tokenize()`

This method splits the normalized sentence into words.

It also removes stop words.

---

## `detectIntent()`

This is the main rule-based NLP method.

It compares the user's tokens with predefined keywords and calculates a score.

The intent with the highest score becomes the detected intent.

---

## `getResponse()`

This method combines the NLP processing steps.

It:

1. Receives the user's message.
2. Tokenizes it.
3. Detects the intent.
4. Finds the appropriate response.
5. Returns the response to the GUI.

---

# EducationChatbotApp.java

This class creates the JavaFX graphical interface.

The GUI contains:

* Application title
* Chat history area
* Text input field
* Send button
* Clear button

The `sendMessage()` method connects the GUI with the chatbot engine.

The process is:

```text
User Input
    ↓
sendMessage()
    ↓
ChatbotEngine
    ↓
NLP Processing
    ↓
Intent Detection
    ↓
Response
    ↓
Chat Area
```

---

# Object-Oriented Programming

This project demonstrates several OOP concepts.

## Encapsulation

The chatbot data is managed inside the `ChatbotEngine` class.

## Abstraction

The GUI does not need to know how NLP processing works.

It simply calls:

```java
chatbot.getResponse(userMessage);
```

## Classes and Objects

The project contains two main classes:

```text
ChatbotEngine
EducationChatbotApp
```

Each class has a specific responsibility.

---

# Sample Output

When the application starts:

```text
+------------------------------------------------+
|                    EduBot                     |
|             Education Help Assistant           |
+------------------------------------------------+

EduBot:
Hello! Welcome to EduBot.

I can help you with:
• Study methods
• Exam preparation
• Programming
• Java and Python
• Algorithms
• Databases
• Projects
• College and careers
```

---

## Example 1

### User

```text
What is Java?
```

### EduBot

```text
Java is an object-oriented programming language
used for desktop applications, web applications,
enterprise software, and many other types of
applications.
```

---

## Example 2

### User

```text
How should I prepare for exams?
```

### EduBot

```text
For exam preparation, create a study timetable,
revise important topics, practice previous questions,
and take regular short breaks.
```

---

## Example 3

### User

```text
What is an algorithm?
```

### EduBot

```text
An algorithm is a step-by-step procedure used
to solve a problem or complete a particular task.
```

---

## Example 4

### User

```text
How can I create programming projects?
```

### EduBot

```text
Projects are a great way to demonstrate your
programming skills. Start with a small project
and gradually add features such as databases,
APIs, or graphical interfaces.
```

---

## Unknown Question

### User

```text
Tell me about space travel.
```

### EduBot

```text
I'm not sure I understand that question.
Try asking about studying, exams, programming,
Java, Python, databases, algorithms, projects,
college, or careers.
```

---

# How to Run

## Requirements

Install:

* Java JDK 17 or later
* JavaFX SDK
* Git
* An IDE such as IntelliJ IDEA, Eclipse, or VS Code

Check Java:

```bash
java -version
```

Check the compiler:

```bash
javac -version
```

---

# Running with an IDE

For IntelliJ IDEA:

1. Create/open the project.
2. Add the JavaFX SDK libraries.
3. Set the JavaFX `lib` directory as a module path.
4. Add:

```text
--module-path "PATH_TO_FX/lib" --add-modules javafx.controls
```

to the VM options.

5. Run:

```text
EducationChatbotApp
```

---

# Running from Command Line

Assuming JavaFX is installed and `PATH_TO_FX` points to the JavaFX SDK:

### Compile

```bash
javac --module-path "PATH_TO_FX/lib" --add-modules javafx.controls -d out src/*.java
```

### Run

```bash
java --module-path "PATH_TO_FX/lib" --add-modules javafx.controls -cp out EducationChatbotApp
```

Replace `PATH_TO_FX` with the location of your JavaFX SDK.

---

# .gitignore

Create a `.gitignore` file:

```text
out/
*.class
.idea/
.vscode/
*.iml
.DS_Store
```

---

# GitHub Upload

Create a GitHub repository named:

```text
education-ai-chatbot-javafx
```

Then run:

```bash
git init
git add .
git commit -m "Initial commit - Education AI Chatbot"
git branch -M main
git remote add origin https://github.com/yourusername/education-ai-chatbot-javafx.git
git push -u origin main
```

Replace `yourusername` with your GitHub username.

---

# Limitations

This project uses a **rule-based NLP approach**, so it is not a fully trained machine-learning chatbot.

Limitations include:

* It understands predefined topics.
* It relies on keyword matching.
* It cannot understand every possible sentence.
* It does not automatically learn from conversations.
* Its answers come from a predefined FAQ knowledge base.

For example, new topics must be added manually to `ChatbotEngine.java`.

---

# Future Improvements

The project can be upgraded with:

* Machine-learning-based intent classification
* Stemming
* Lemmatization
* Sentiment analysis
* TF-IDF text classification
* Database-based FAQ storage
* Conversation history
* User accounts
* Voice input
* Text-to-speech
* More educational subjects
* Admin panel for adding FAQs
* Generative AI/LLM integration
* Spring Boot backend
* MySQL database
* Cloud deployment

---

# Learning Outcomes

This project demonstrates:

* Java programming
* JavaFX GUI development
* Object-Oriented Programming
* Collections
* HashMap and HashSet
* String processing
* Regular expressions
* NLP fundamentals
* Tokenization
* Stop-word removal
* Keyword matching
* Intent detection
* Rule-based AI
* Event handling
* Git and GitHub

---

# Disclaimer

This project is created for educational purposes. The chatbot provides predefined educational information.

---

# Author
K. Anu Ananda
