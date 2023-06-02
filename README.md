# Automated Exam Creator and Simulator

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction
This Python-based project provides a dynamic way of creating and simulating exams using the OpenAI GPT-4 for question generation. With the main target audience being teachers and educators, this project simplifies the process of exam creation and grading. 

## Project Structure
The project includes the following Python scripts:

- `test_creator.py`: Houses the `TestGenerator` class which leverages the OpenAI API to generate multiple-choice questions based on the input topic.
- `teacher.py`: Contains the `Teacher` class responsible for interacting with the user to setup tests and processing the generated tests to segregate into teacher and student views.
- `exam_simulator.py`: Hosts the `Exam` class that takes the student view of the test and correct answers, simulates an exam-taking environment, stores the test and grades the answers.

The main function is included in `main.py` which showcases how to utilize these classes.

## Installation
To setup this project, follow the below steps:

1. Clone the repository to your local machine using `git clone`.
2. Install the required Python packages. This project primarily uses the `openai` package which can be installed via pip: `pip install openai`.
3. Get your OpenAI API key. The `TestGenerator` class fetches this key using `os.environ["OPENAI_API_KEY"]`.
4. Set the OpenAI API key as an environment variable.

For Unix/Linux:
```bash
export OPENAI_API_KEY='your-api-key-here'
```
For Windows:
```bash
$env:OPENAI_API_KEY='your-api-key-here'
```

## Quick Start
After following the installation instructions, run the main.py script from the command line:

```bash
python main.py
```

The `Teacher` class will prompt you for input on the topic, number of possible answers for each question and number of questions for your test.

## Usage 

Here is a detailed breakdown of how to use this project:

### Create a Test

Run `main.py`. You will be prompted to enter the topic of the test, the number of possible answers per question, and the total number of questions. The `Teacher` class uses these inputs to leverage the `TestGenerator` class for generating the respective questions.

```bash
python main.py
```

### Simulate an Exam

After the test creation, the `Exam` class initiates a simulation of the exam. You will be prompted to provide your answers for the questions.

```bash
#Input Prompt
Enter your answer: 
```

### Exam Grading

Once the exam is over, the `Exam` class grades your answers. The grading output will be displayed on the screen:
```bash
# Example output
{1: 'A', 2: 'B', 3: 'D'}
3 out of 3 correct! You achieved: 100.0 % : Passed!
```

### Storing a Test
You can also choose to store the test in a text file for future use. This can be done by passing `store_test=True` while creating an instance of the `Exam` class.


# Contributing
Contributions are welcomed! Here's how you can help:

1. Fork the repository.
2. Create a new branch with your feature: `git checkout -b my-feature`.
3. Commit your changes: `git commit -am 'Added some feature'`.
4. Push to the branch: `git push origin my-feature`.
5. Submit a pull request.


# LICENSE
This project is licensed under the MIT License. See the LICENSE file for details.
