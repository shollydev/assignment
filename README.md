# C# Assignment For Senior Level Candidates

Fork the existing repository located here: https://github.com/transactBlackboard/assignment
This document may be followed for how to fork, branch and submit a pull request: https://gist.github.com/Chaser324/ce0505fbed06b947d962 Note: all sections after "Submitting" are the steps Transact staff will perform to test your submission.

Create a branch with a name of your choosing.

Complete the assignment as described in this document

Commit and push your changes to github

Create a pull request from your branch to the master (fork)

Create a Console App that will execute your code.

#Assignments

## Assignment 1

Given a list of 20 random numbers we need to get the first 4 even numbers using LINQ. Print out the result to console.

## Assignment 2

The below existing code base violates the 'O' in the SOLID principle. Please refactor the code to remove the violation. (This can be corrected right in this README.md to save time). The product manager believes the customer will also want to have post that contain mentions of other users in the future but that will be completed on a future sprint.

```
// Adds a tweet to the database, if a tweet has a hash tag then it adds to the database as a tagged post
class Post
{
        void CreatePost(Database db, string postMessage)
            {
                if (postMessage.StartsWith("#"))
                {
                    db.AddAsTag(postMessage);
                }
                else
                {
                    db.Add(postMessage);
                }
            }
}
```

## Assignment 3

Then entire code base was written with the logger instantiated in the individual classes. For example, the below code was written with a custom ErrorLogger. Since Microsoft now has Application Insights we would like to use the ILogger interface. How should the original developer written this so the logger could have been changed out more easily? Please do the refactoring now to support future changes to the logger. (This can be changed in this Readme.MD to save time)

```
class Post
{
    private ErrorLogger errorLogger = new ErrorLogger();

    void CreatePost(Database db, string postMessage)
    {
        try
        {
            db.Add(postMessage);
        }
        catch (Exception ex)
        {
            errorLogger.log(ex.ToString())
        }
    }
}
```

## Assignment 4

You are given a data structure of employee information, which includes the employee's unique id, his importance value and his direct subordinates' id.

For example, employee 1 is the leader of employee 2, and employee 2 is the leader of employee 3. They have importance value 15, 10 and 5, respectively. Then employee 1 has a data structure like [1, 15, [2]], and employee 2 has [2, 10, [3]], and employee 3 has [3, 5, []]. Note that although employee 3 is also a subordinate of employee 1, the relationship is not direct

Example 1:

Input: [[1, 5, [2, 3]], [2, 3, []], [3, 3, []]]
Output: 11
Explanation:
Employee 1 has importance value 5, and he has two direct subordinates: employee 2 and employee 3. They both have importance value 3. So the total importance value of employee 1 is 5 + 3 + 3 = 11.

Note:

One employee has at most one direct leader and may have several subordinates.
The maximum number of employees won't exceed 2000.

Create an Employee object and an ImportanceCalculator and print out the total importance of each employee.
