# Clean Code Principles

## Simplicity - Keep code as simple as possible

According to the rules of simplicity, there is a set of criteria proposed by Kent Beck to judge whether the code is "simple enough". The code contains no duplication, verified by automated tests and expresses each idea separately. Above all, the code should be composed of only the minimum number of components necessary.

## Readability - Code should be easy to understand

In order for the code to be "readable", there should be a consistent structure, names are clear and logical, short comments explaining "why" are included when necessary, and generally having shorter lines that have only one purpose. Generally, the code is readable if it is easy for someone else to determine what your code is trying to achieve. 

## Maintainability - Future developers should be able to work with the code easily

When seeing if our code is maintainable, we should ask ourselves if we would be satisfied taking over this project from another person. A few ways to ensure maintainability for our code include: clear and updated documentation, code can be broken down to modules that are easy to understand. Maintainable code should also have low coupling, that is, there should be minimal dependency between different parts of the code.

## Consistency - Follow style guides and project conventions

Having a consistent code involves following conventional styles and patterns that are widely accepted. If joining a new organisation, try to understand their specific coding conventions as well. Generally, code should look like it's been created by only 1 person. 

## Efficiency - Write performant, optimised code without premature over-engineering.

Efficient code means if it meets the budget in terms of latency, memory and workload. It is about optimising the performance without sacrificing code quality. This means avoiding unnecessary computations, redundant code and unfavourable data structures. 

# Messy Code vs Clean Code

## Messy Code

I asked ChatGPT to create an intentionally messy code for me to fix. The image below shows the messy code.

<img width="491" height="239" alt="Screenshot 2025-08-15 at 1 23 56 pm" src="https://github.com/user-attachments/assets/f8e53dd3-30d6-434c-9b15-d70790e57d72" />

Why is it difficult to read?
- calculations taking place everywhere, no separation of responsibility
- what is s? what is x?
- the pass threshold is hard-coded (pass threshold is 70 but the code logic is avg>69, not consistent)
- unecessarily recalculates each time

## Clean Code

The code below shows an edited, cleaner version of the messy code.

<img width="491" height="384" alt="Screenshot 2025-08-15 at 1 24 08 pm" src="https://github.com/user-attachments/assets/58b71f05-d69e-4ab7-8375-ad060450fa75" />

Why is it cleaner?
- pass threshold clearly outlined, easy to find and easy to change if required
- created new functions that have its own dedicated responsibility, called to the main code when needed
- names are clear and understandable ("for student in students" clearly means "for each student in the student list" as opposed to "for s in students")

# Code Formatting and Style Guides

# Naming Variables and Functions

## Good Variable and Function Names

Ideally, names should follow these conventions:
- clear and concise
- ideally variables would be nouns, variables verbs
- consistent style (variablename, VariableName, variable-name, variable_name)
- avoid abbreviating
A good name should enable the reviewer of the code or another developer to quickly understand what the code does. 

Poorly named variables will make it difficult for others and even myself to understand the code. Ambiguity could also cause issues when we need to make changes but we are not sure what the variables or functions represent (temp could mean temperature variables, or temporary buffer, etc). In a shared environment, people may create variables or functions that are the same with different names because they didn't realise it already existed. Importantly, it slows down progress because of the frequent miscommunications or reviews. 

## Fixing Names

cnt -> unreead_message_count
idx -> current_user_index
update() -> update_user_profile()
calc_total() -> calculate_invoice_total()

Refactoring makes code easier to read and maintain, less-error prone and developers can understand it more quickly with minimal misunderstanding and documentation. 

# Writing Small, Focused Functions

## Functions Best Practice

Functions should represent a single purpose. Ideally, functions should have less than 20 lines and have no side effects. Smaller functions reduce cognitive load and improve usability (some developers may need only a few functions). It also helps to make the intent of each part of the code explicit. 

## Big, Multitasking Function to Small, Focused Function

<img width="697" height="679" alt="Screenshot 2025-08-20 at 14 06 16" src="https://github.com/user-attachments/assets/47e8269d-ab65-4862-acf0-1eb53f694b60" />

As seen on the image above, by breaking down the large function into smaller ones, each function has its own responsibility and is more readable when used in the main code. 

# Avoiding Code Duplication

Don't Repeat Yourself (DRY) principle is a software development principle aimed at reducing redundancy and duplication of information, discouraging repetition of code, data, and logic. Issues with having duplicate code within a system incude:
- harder to maintain
- higher risk of bugs
- making changes in the code can take an unnecessarily long time

Below shows the difference between a section of code with duplication vs no duplication.

<img width="697" height="679" alt="Screenshot 2025-08-20 at 15 15 41" src="https://github.com/user-attachments/assets/5a381af1-95f5-4a34-9df8-36bbb592cdc6" />

Refactoring the functions to remove duplication allows for centralised logic. This means when there needs be a change or fix, there will only be 1 place to fix it. Functions will also be easier to read because they are smaller and clearer, streamlining collaboration. 

# Refactoring Code for Simplicity

# Commenting and Documentation

# Handling Errors and Edge Cases

# Writing Unit Tests for Clean Code

# Identifying and Fixing Code Smells

# Static Analysis Checks in CI/CD

