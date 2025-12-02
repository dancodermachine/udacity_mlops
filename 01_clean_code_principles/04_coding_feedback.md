# Giving Code Feedback
When thinking of giving feedback, think of the following:

* Is the code clean and modular?
    * Can I understand the code easily?
    * Does it use meaningful names and whitespace?
    * Is there duplicated code?
    * Can I provide another layer of abstraction?
    * Is each function and module necessary?
    * Is each function or module too long?
* Is the code efficient?
    * Are there loops or other steps I can vectorize?
    * Can I use better data structures to optimize any steps?
    * Can I shorten the number of calculations needed for any steps?
    * Can I use generators or multiprocessing to optimize any steps?
* Is the documentation effective?
    * Are inline comments concise and meaningful?
    * Is there complex code that's missing documentation?
    * Do functions use effective docstrings?
    * Is the necessary project documentation provided?
* Is the code well tested?
    * Does the code have high test coverage?
    * Do tests check for interesting cases?
    * Are the tests readable?
    * Can the tests be made more efficient?
* Is the logging effective?
    * Are log messages clear, concise, and professional?
    * Do they include all relevant and useful information?
    * Do they use the appropriate logging level?
---
When doing code review, you are dealing with people, no computers. So it's important to be thoughtful on their ideas and efforts. You are in a team and there will be differences in preferences. The goal of code review isn't to make all code follow your personal preferences, but to ensure it meets a standard of equality for the whole team.
1. **Explain issues and make suggestions**

    Rather than commanding people to change their code a specific way because it's better, it will go a long way to explain to them the consequences of the current code and <u>suggest</u> changes to improve it. They will be much more receptive to your feedback if they understand your thought process and are accepting recommendations, rather than following commands. They also have done it a certain way intentionally, and framing it as a suggestion promotes a constructive discussion, rather than opposition.
    ```
    🔴 BAD: Make model evaluation code its own module – too repetitive.

    🟡 BETTER: Make the model evaluation code its own module. This will simplify models.py to be less repetitive and focus primarily on building models.

    🟢 GOOD: How about we consider making the model evaluation code its own module? This would simplify models.py to only include code for building models. Organizing these evaluation methods into separate functions would also allow us to reuse them with different models without repeating code.
    ```
2. **Keep your comments objective**
    
    Try to avoid using the words "I" and "you" in your comments. You want to avoid comments that sound personal to bring the attention of the review to the code and not to themselves.
    ```
    🔴 BAD: I wouldn't groupby genre twice like you did here... Just compute it once and use that for your aggregations.

    🔴 BAD: You create this groupby dataframe twice here. Just compute it once, save it as groupby_genre, and then use that to get your average prices and views.

    🟢 GOOD: Can we group by genre at the beginning of the function and then save that as a groupby object? We could then reference that object to get the average prices and views without computing groupby twice.
    ```
3. **Provide examples**
    
    When providing a code review, you can save the author time and make it easy for them to act on your feedback by writing out your code suggestions. This shows you are willing to spend some extra time reviewing their code and helping them out. It can also just be much quicker for you to demonstrate concepts through code rather than explanations.
    ```
    🔴 BAD: You can do this all in one step by using the pandas str.split method.

    🟢 GOOD: We can actually simplify this step to the line below using the pandas str.split method. Found this on this Stack Overflow post: https://stackoverflow.com/questions/14745022/how-to-split-a-column-into-two-columns
    ```
### Further Reading
* [Reading 1]( https://github.com/lyst/MakingLyst/tree/master/code-reviews)
* [Reading 2](https://www.kevinlondon.com/2015/05/05/code-review-best-practices/)