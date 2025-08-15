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
