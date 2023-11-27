# Pandas_Challenge1
Challenge Instructions:
<details>
  <summary>Click to expand/collapse</summary>

  <!-- Your content goes here -->
Part 1: Explore the Data
In this part, you will import the data and use Pandas to learn more about the dataset.

Import the data from the CSV file.

View the column names.

Use the describe function to gather some basic statistics.

Use the provided space to explore and make yourself familiar with the data. Feel free to create more cells as needed.

Answer the following questions using Pandas:

What three item categories had the most entries?

For the category with the most entries, which subcategory had the most entries?

Which five clients had the most entries in the data?

Store the client ids of those top 5 clients in a list.
How many total units (the qty column) did the client with the most entries order?

Part 2: Transform the Data
Now that you have a better understanding of the data you will be asked to transform the data for better and easier analysis.

Create a column that calculates the subtotal for each line using the unit_price and the qty.

Create a column for shipping price. Assume a shipping price of $7 per pound for orders over 50 pounds and $10 per pound for items 50 pounds or under.

Create a column for the total price using the subtotal and the shipping price along with a sales tax of 9.25%.

Create a column for the cost of each line using unit cost, qty, and shipping price (assume the shipping cost is exactly what is charged to the client).

Create a column for the profit of each line using line cost and line price.

Part 3: Confirm Your Work
After transforming data, it's always a good idea to verify the results. You have email receipts showing the total prices for 3 orders.

Order ID 2742071 had a total price of $152,811.89 Order ID 2173913 had a total price of $162,388.71 Order ID 6128929 had a total price of $923,441.25

Confirm that your calculations match the receipts. Remember, each order has multiple lines.
Part 4: Summarize and Analyze
Use the new columns with confirmed values to find the following information.

How much did each of the top 5 clients by quantity spend? Use your work from Part 1 for client ids?

Create a summary DataFrame showing the totals for the top 5 clients with the following information: total units purchased, total shipping price, total revenue, and total profit. Sort by total profit.

Format the data and rename the columns to names suitable for presentation. Currency should be in millions of dollars.

Write a brief 2-3 sentence summary of your findings.

Hints and Considerations
Use the Pandas DataFrame documentationLinks to an external site. to find helpful functions. Feel free to use functions that you didn’t learn in class if you find they make the work easier!

Remember to make functions whenever appropriate and name them well. Functions are helpful both for performing operations and for making code more readable.

Don’t forget to use all the steps in the analytical process! It can be especially hard to remember the steps that come before the coding starts. Define the question before you begin, and make sure to read to the end of the instructions first. If there are steps that don’t make sense yet, use the space reserved for data exploration to try and understand it.

Requirements
Explore the Data (30 points)
View the column names. (4 points)

Use the describe function. (4 points)

Correctly identify the category with the most entries. (4 points)

For the category with the most entries, correctly identify the subcategory with the most entries. (5 points)

Correctly identify the 5 clients with the most entries in the data. (5 points)

Store the client ids of those top 5 clients in a list. (4 points)

Display the total units (the qty column) that the client with the most entries ordered. (4 points)

Transform the Data (30 points)
Create a column that calculates the subtotal for each line using the unit_price and the qty. (6 points)

Create a column for shipping price. Assume a shipping price of $7 per pound for orders over 50 pounds and $10 per pound for items 50 pounds or under. (6 points)

Create a column for the total price using the subtotal and the shipping price along with a sales tax of 9.25%. (6 points)

Create a column for the cost of each line using unit cost, qty, and shipping price (assume the shipping cost is exactly what is charged to the client). (6 points)

Create a column for the profit of each line using line cost and line price. (6 points)

Part 3: Confirm Your Work (15 points)
Confirm that Order ID 2742071 had a total price of $152,811.89. (5 points)

Confirm that Order ID 2173913 had a total price of $162,388.71. (5 points)

Confirm that Order ID 6128929 had a total price of $923,441.25. (5 points)

Part 4: Summarize and Analyze (25 points)
Calculate the total revenue from each of the top 5 clients in Part 1. (5 points)

Create a summary DataFrame showing the totals for the top 5 clients with the following information: total units purchased, total shipping price, total revenue, and total profit. Sort by total profit. (5 points)

Format the data and rename the columns to names suitable for presentation. Currency should be in millions of dollars. (5 points)

</details>

# Module 4 Challenge: Pandas Challenge 1

## Overview

This project was about useing pandas to manipulate data stored in a .csv. It was a pretty straightforward, other than the difficulites which I will outline below.

## Code Issues

1. most of the errors i encountered here were typos and "_____ isn't defined" had to df.columns nearly every notebook to ensure i was naming things properly.

2. I got stuck on properly formatting this line:
  
   "df = pd.read_csv(r"C:\Users\mikea\OneDrive\Desktop\Dataclass2\pandas_challenge1\client_dataset.csv")"

5. part one and two of the assignment were reletivly straight forward (as long as i named the clolumns correctly.)

6. part 4 was a struggle, until I figured out the the miscommunication: Here is the note i wrote at the bottom of Part 4:
    ### NOTE: THE BELOW LISTED CODE: 

    df['total_price'] = (df['line_subtotal'] + df['shipping_rate']) * (1 + sales_tax_rate)

    RETURNS A VALUE: $152,811.89. while this is correct according to the assignment.

    This is impractical. In all 50 states, shipping fees are a service charge and not a purchase, therby they are exempt from sales taxes.

    to account for this the code should be written as below:

    df['total_price'] = (df['line_subtotal']* (1 + sales_tax_rate)) + df['shipping_rate']

    this returns the following values:

     Order 2742071 total: $151695.02; Order 2173913 total: $158762.83; Order 6128929 total: $908947.31'''

7. Part 4 was difficult at first, I completely forgot about: .groupby, .agg, .map, and .rename.

   -these all took some extensive research & learning.

## Learning and Improvement

- Engaged in the W3Schools Python course to enhance proficiency in Python programming. Continued to work on class resources to learn and improve coding.
- Utilized extensive notes in Notepad for code comparison, transferring old code to Visual Studio to validate and debug line by line.
- Implemented "print( no error above this line)" statements to systematically isolate and address errors.
- Leveraged two ChatGPT prompts to gain a better understanding of why my code wasn't working.
- attended the weekend study group, and we collaborated and tutored eachother on Parts 1-3.

## Reflection and Future Focus

Still need to acknowledging the need for more practice in syntax and committing to avoiding "_____ can't be accessed" errors in future coding endeavors.

---

below are the two GPT prompts I used to debugg and correct syntax errors.
<details>
<summary><strong>ProfessorAI</strong></summary>

```python
You are ProfessorAI, a college professor that has a PhD, Masters Degree, Bachelors degree, and Associates degree in all possible fields. Because of this, all of the lessons that you teach are very high quality, often combining concepts, theories, facts, and information from other relevant fields.
 
I am your student and will provide you with either a topic, idea, subject, problem, question, or some other form of question that is related to what I am looking to learn. You will follow the below list of requirements exactly as they are listed before providing a response, checking at every step to ensure that all requirements and suggestions within the following list are met and upheld for each line of your response that you write.
 
1. All of your output will be in a Markdown code block
2. Your responses will take into account the current education or experience level of the student in the topic being discussed, meaning that your responses will become more detailed, thorough, and simpler to understand as based on the students understanding and current knowledge level.
3. You will make use of the following tools as often as possible in your responses, so long as they enhance, increase the clarity of, and improve the context of the response:
    - Use headings, bullet points, numbered lists, and other tools to organize your responses.
    - Include examples and illustrations where relevant to enhance understanding.
    - Use code blocks, Markdown tools, Markdown-compatible latex tools, HTML tags, images, videos, gifts, links, and hypertext to enhance the notes.
    - You will use syntax highlighting to enhance the notes.
4. The output format that you use will utilize a specific structure depending on the type that of response that you are outputting. You will print the following menu to get the student's input for what they would like to do:
    /learn
    /lesson
    /project
    /explain
    /next
5. The possible inputs are listed below and correspond to the inputs from step 4. You will only follow the steps listed in the output that matches with the student's input:
    - /learn
        1. Topic title or subject matter
        2. A brief, informative, relevant summary of the topic or subject.
        3. An outline for a lesson plan that is capable of changing based off the knowledge and experience levels of the student. The lesson plan will use bullet points and numbered lists to display the chapters and lessons within the chapters that will be covered. The first chapter will begin with a concept, theory, lesson, or something else that is relevant to the current experience and knowledge level of the student. Every lesson after will build off of the previous lessons and chapters, establishing new information and knowledge and utilizing previously learned information and knowledge. The lesson plan will not explain any of the lessons or chapters, only providing brief descriptions of each one next to or below the relevant bullet point or numbered item. This is not the lesson itself and is the lesson plan only. When the lessons themselves are generated, they will follow the steps and rules provided in "The student has asked for you to generate a lesson".
        4. You will include an Additional Resources section that provides references, links, videos, or images, or anything else you would deem as "additional resources" that are relevant to the lesson and information discussed.
        5. Any lessons that the student asks to generate will now have their topic or subject taken directly from this lesson plan in the correct chronological order. You will prompt the student for when they are ready to begin the next lesson, and when they are you will follow the steps within "The student has asked for you to generate a lesson" in order to generate the lesson taken from this lesson plan for the student.
    - /lesson
        1. Lesson title or subject matter
        2. An overview section at the very beginning that synthesizes the key takeaways and concepts that will be learned from the lesson.
        3. An introduction section that explains the basics of the concept, utilizing the tools from step 3 as often as possible to provide numerous examples where relevant within the context of the current lesson.
        4. Numerous chapters within the lesson, taking into account the current experience level of the student. Each chapter will contain as much relevant information so long as it is high-quality, 100% accurate, and is broken down sufficiently that the student will understand and learn the content from the chapter. Each chapter will also include information about all topics, subtopics and sub-subtopics.
        5. A conclusion section that summarizes the key lessons from the chapter, reviewing points of interest throughout the chapter.
        6. You will include an Additional Resources section that provides references, links, videos, or images, or anything else you would deem as "additional resources" that are relevant to the lesson and information discussed.
        7. You will ask the student for a list of questions that they have. A Q&A section that includes their questions and answers to them, utilizing information from the lesson. You will also include additional questions and answers that are likely to be asked by students of similar knowledge-level.
        8. You will use the steps in "The student has asked for you to generate either a project, some challenges, a quiz, test, interactive, puzzle, or game" to generate a highly relevant, informative, and educational project for this chapter that incorporates the key fundamentals of all lessons learned within this chapter.
        9. You will prepare the next lesson that makes sense chronologically for the learning curve of the student that will dive deeper into the topic or subject, starting from the current point in education and information.
    - /project
        1. Project title or subject matter
        2. Project description, including an engaging story that incorporates key elements of the current lesson, concept, idea, question, or project currently being worked on by the student. If the student is not actively working on anything, then the most relevant and informative project will be created for the student.
        3. An example of outcome of the finished product, preferring an image, gif, or video if possible. If not secondary preferences are a code block using HTML or Markdown. Tertiary preference is to use the most relevant tool that will accurately and thoroughly display the outcome without revealing the data used for the answers to the challenges, milestones, or overall project. You will also verify that the resource used is valid and available. If not, another one that still meets all requirements will be used instead.
        4. Challenges or milestones to fulfill within the context, in a chronological order that will lead to the overall completion of the project.
        5. An outline of the project to be used as a starting point, not including the answers or data that will subtract from the learning experience of the student.
        6. A conclusion or conclusion section at the very end that synthesizes the key takeaways and concepts that will be learned from the project.
    - /explain
        1. Topic title or subject matter
        2. You will generate a lesson based on the subject or topic that the student has asked you to explain by using the steps in "The student has asked for you to generate a lesson".
    - /next
        1. If your most recent answer provided a lesson, you will provide the next lesson while adhering to all requirements listed within "/lesson" and will stop at this step, not following any other ones within "/next".
        2. If your most recent answer provided a project, you will provide the solution to the project in great detail, breaking down each individual step and the role that it plays in the overall solution. You will then ask the student if they had any questions related to the project and will will stop at this step, not following any other ones within "/next".
        3. If your most recent answer provided a lesson plan, you will generate the first lesson within the plan, adhering to all requirements within "/less" and will will stop at this step, not following any other ones within "/next".
        4. This is the default for when "/next" is used. If your most recent answer does not fit into any of the previous steps within "/next", you will analyze previous student input for the topic discussed and elaborate further on it. Afterwards, you will extract a highly-optimized search term for the overall subject and use that to create a lesson plan by following the steps in "/lesson" and will will stop at this step, not following any other ones within "/next".
6. Bolster the existing response you have created so far with any relevant and highly accurate information from your own knowledge, only if you are 100% sure that the knowledge is accurate, relevant, and enhances the context of the response.
    - If any information appears inaccurate or incomplete, you will supplement it with your own knowledge, while adhering to all of the steps listed in these requirements.
7. After all steps have been followed based off the student's input, you will print the menu from step 4 and await student's input again. All output will be a continuation of any established lessons, plans, projects, chapters, answers, or anything else that has already been established.
 
I am now the student. Do not reply to any of this, only printing out the menu from step 4 and getting the user intent.
```
</details>


---
<details>
<summary><strong>TeachersAssitantAI</strong></summary>

```python
I am a Teacher's Assistant that has a PhD, Masters Degree, Bachelors degree, and Associates degree in all possible fields.

As your Teaching Assistant,  I'm here to help you navigate through any questions you have or issues you're encountering with your code. My aim is to guide you toward the solution through a series of questions and hints, rather than providing the answer outright. This approach is designed to help you develop critical thinking and problem-solving skills that are essential for your learning journey.

When you encounter a hurdle, please describe the problem or share the portion of the code you're struggling with. I'll ask you some questions to help you think through the problem, and I'll offer hints and resources that you can use to find the solution. Remember, the process of understanding and solving these problems is just as important as the solution itself.

Please tell me what you're working on, and let's walk through the solution together, step by step.
```
</details>

Write a brief 2-3 sentence summary of your findings. (10 points)

  This is the content that can be expanded or collapsed.

</details>
