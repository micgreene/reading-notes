# **Reading Assignment 6 - Game of Greed 1**
[Home](https://micgreene.github.io/reading-notes/)<br />
 ## How to use the Random Module in Python
   ### Randint   
    + If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.
    + `import random`<br />`print(random.randint(0, 5))`
   ### Random   
     + If you want a larger number, you can multiply it. For example, a random number between 0 and 100:
     + `import random`<br />`print(random.random() * 100)`
   ### Choice   
     + Generate a random value from the sequence sequence.<br />
       `random.choice( ['red', 'black', 'green'] )`<br />
     + The choice function can often be used for choosing a random element from a list.
     + `import random`<br />`print(random.random() * 100)`
   ### Shuffle   
     + The shuffle function, shuffles the elements in list in place, so they are in a random order.
     + `from random import shuffle`<br />`x = [[i] for i in range(10)]`<br />`shuffle(x)`<br />**Output:**<br />
     `# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]`
   ### Randrange   
     + Generate a randomly selected element from range(start, stop, step)
     + `import random`<br />`for i in range(3):`<br />
       `print random.randrange(0, 101, 5)`
   
  
 ## What is Risk Analysis in Software Testing and how to perform it?<br />
   The probability of any unwanted incident is defined as Risk. In Software Testing, *risk analysis* is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.<br />
   ### Why use Risk Analysis?
     + In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.
       + Use of new hardware
       + Use of new technology
       + Use of new automation tool
       + The sequence of code
       + Availability of test resources for the application
     + Certain risks are unavoidable:
       + The time that you allocated for testing
       + A defect leakage due to the complexity or size of the application
       + Urgency from the clients to deliver the project
       + Incomplete requirements
     + In such cases, you have to tackle the situation with care. Following points can be taken care of:
       + Conduct Risk Assessment review meeting
       + Use maximum resources to work on high-risk areas
       + Create a Risk Assessment database for future use
       + Identify and notice the risk magnitude indicators: high, medium, low.
       
     + Now, what are these risk magnitude indicators? Well, here is an explanation.
       + **High:** means the effect of the risk would be very high and non-tolerable. The company might face loss.
       + **Medium:** it is tolerable but not desirable. The company may suffer financially but there is a limited risk.
       + **Low:** it is tolerable. There lies little or no external exposure or no financial loss.

   ### Risk Identification
     + **Business Risks:** This risk is the most common risk associated with our topic. It is the risk that may come from your company or your customer, not from your project.
     + **Testing Risks:** You should be well acquainted with the platform you are working on, along with the software testing tools being used.
     + **Premature Release Risk:** a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required
     + **Software Risks:** You should be well versed with the risks associated with the software development process.

   ### Risk Assessment
     + In the risk analysis process, these steps prove to be the most important one. It is said that this step is way too complex and should be tackled with the utmost care. After risk identification, assessment has to be dealt programmatically.
      ![image](https://user-images.githubusercontent.com/66289456/146984956-704f9ff3-be63-48ab-94b6-1e903449f91e.png)
    
   ### The perspective of Risk Assessment
     + **Effect** – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.
     + **Cause** – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.
     + **Likelihood** – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.
   
   ### How to perform Risk Analysis?
     + There are three steps:
       + **Searching the risk**
       + **Analyzing the impact of each individual risk**
       + **Measures for the risk identified**
