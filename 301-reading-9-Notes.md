# **Reading Assignment 9 - Functional Programming and Refactoring**

1. ## Functional Programming Overview
  + ### Definition
    + **Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.**
    + The first fundamental concept we learn when we want to understand functional programming is pure functions.
      + So how do we know if a function is pure or not? Here is a very strict definition of purity:
        + It returns the same result if given the same arguments (it is also referred as deterministic)
        + It does not cause any observable side effects
        + No External Objects
    + **It does not cause any observable side effects**
      + Examples of observable side effects include modifying a global object or a parameter passed by reference.
      + Now we want to implement a function to receive an integer value and return the value increased by 1.
        + `let counter = 1;`
        + `function increaseCounter(value) {`
        + `counter = value + 1;}`
        + `increaseCounter(counter);`
        + `console.log(counter); // 2`
      + We have the counter value. Our impure function receives that value and re-assigns the counter with the value increased by 1.
      + **Observation: mutability is discouraged in functional programming.**
        + We are modifying the global object. But how would we make it pure? Just return the value increased by 1. Simple as that.
          + `let counter = 1;`
          + `const increaseCounter = (value) => value + 1;`
          + `increaseCounter(counter); // 2`
          + `console.log(counter); // 1`
      
2. ## Functions as first-class entities
  + 1. **The idea of functions as first-class entities is that functions are also treated as values and used as data.**
    + Functions as first-class entities can:
      + - refer to it from constants and variables
      + - pass it as a parameter to other functions
      + - return it as result from other functions
    + `const sum = (a, b) => a + b;`
    + `const subtraction = (a, b) => a - b;`
    + `const doubleOperator = (f, a, b) => f(a, b) * 2;`
    + `doubleOperator(sum, 3, 1); // 8`
    + `doubleOperator(subtraction, 3, 1); // 4`
    + When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. It is harder to procrastinate or get off track when someone else is relying on you to complete the work. Popping open your Facebook timeline is just that less enticing when someone else is looking at your screen.
    + Another important aspect of learning to program is knowing when to ask for help. We advise our students to spend no more than fifteen minutes stuck on a problem before asking a teaching assistant or instructor for help. When developers pair program, they rely more on each other and can often find a solution together without needing to ask for additional help. Ultimately, this boosts overall confidence.
  + 3. Learning from fellow students
    + Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.
    + Often times, the developers in a pairing have different skill sets. If one programmer is more experienced in a certain skill, they can teach a student who is less familiar with that area. The less experienced developer benefits from the experienced developer’s knowledge and guidance, and the latter benefits from explaining the topic in their own words, further solidifying their own understanding.
  + **4. Social skills**
    + Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills. When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself.
    + This has long-term career impacts. As much as employers want strong programmers, they know it’s essential to hire people who can work well with others.
  + **5. Job interview readiness**
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.
    + For most roles, the ability to work with and learn from others and stellar communication skills are as (or more!) important to a company than specific technical skills. Pair programming strengthens all of those skills.
  + **6. Work environment readiness**
    + Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.
