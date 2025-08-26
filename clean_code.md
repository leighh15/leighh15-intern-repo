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

## Common Refactoring Techniques

Refactoring code is simply changing the code so that it is easier to understand without altering behaviour. The following refactoring techniques are commonly utilised:
- Extract method: take small functions out of long ones to isolate intentions
- Renaming variables: changing the names of variable of function or method to better reflect its purpose or content
- Remove duplication: consolidating repeat logic in one place only
- Replace magic number with constants

## Complicated vs Refactored Code

The image below shows an overly complicated code. We can detect immediately that the function is trying to do everything at once. This created deep nesting with many branches that made it difficult to understand. There also multiple instances of code duplication, which is risky when we need to update or make changes. 

<img width="767" height="910" alt="Screenshot 2025-08-22 at 11 51 39" src="https://github.com/user-attachments/assets/701302b4-d80a-45a3-a6d0-92e5379172cb" />

The image belows shows a refactored version. The intentions are clearly separated, and the code is easier to understand and follow through. Dictionaries are also utilised if we need to add new instances. This eliminated the code duplication from the complicated code. The flow of the code is now more logical and intentional. 

<img width="1246" height="910" alt="Screenshot 2025-08-22 at 11 56 21" src="https://github.com/user-attachments/assets/380ad366-f046-402b-9210-33fd77c257fd" />
<img width="1135" height="215" alt="Screenshot 2025-08-22 at 11 57 04" src="https://github.com/user-attachments/assets/56c8a1e7-1431-4160-b793-ec1335157e01" />

# Commenting and Documentation

## Best Practices for Comments and Documentation

Writing effective code comments and documentation is crucial for collaboration and maintainability. Comments explain why a chunk of code exists, especially when it is not immediately clear from the code itself. Good comments should be:
- Concise and straight to the point
- Comments add value and not merely restating the code
- Write comments along with the code, not as an afterthought
Documentations provide comprehensive information about the codebase, typically aimed at users of the code. Good documentation should be:
- Up-to-date and reflects current state of codebase
- Make documents easily accessible
- Include examples of code usage

## When to add and when to not add comments

Poorly commented
<img width="634" height="262" alt="Screenshot 2025-08-22 at 12 24 12" src="https://github.com/user-attachments/assets/966c3658-49f7-4847-ae0e-fe5a6b1d5173" />

Well commented
<img width="634" height="593" alt="Screenshot 2025-08-22 at 12 23 52" src="https://github.com/user-attachments/assets/41ccd87f-915b-480a-839a-dc0e35405519" />

Add comments when you need to clarify complex logic and algorithms, and provide context for specific values or configurations. It is also helpful to explain some design decisions and trade-offs.

Comments that merely restate the code (such as in the first image) are unecessary. If you feel that a comment is required to explain the name of a variable or function, it is better to change the name entirely. If you feel that a comment has to explain the function step-by-step, consider refactoring and restructuring the code so that it makes sense. 

# Handling Errors and Edge Cases

## Best Practices for Handling Errors and Edge Cases

Error Handling (what to do when something goes wrong, or could go wrong)
- Check inputs early: validate input as soon as it enters the function
- Guard clauses: quick check at the start, if something is wrong, raise an error immediately
- Clear error messages: error messages should explain exactly what failed

Edge Cases (plan ahead for special and unusual situations)
- Empty values
- Extreme values
- Wrong type of input
- Duplicates

## Good vs Bad Code

The code below has no error handling and edge cases at all. This code assumes nothing will go wrong. However, we know that if nums is None, the code crashes, if nums is empty, it divides by zero (undefined), if nums contains a string, it crashes. We don't want this to happen, that is why we have to account for all possible scenarios.

<img width="634" height="70" alt="Screenshot 2025-08-22 at 13 10 42" src="https://github.com/user-attachments/assets/dd2fc76f-8342-4f6c-8121-9da74df2e199" />

The code below handles errors and edge cases. The code checks if the input is actually there and is not empty. It rejects bad inputs such as those of the wrong type, empty lists, infinity numbers. Handling errors improve reliability because the system transitions from undefined behaviour to well-defined and observable outcomes. Guard clauses make failures immediately explainable. As a result, the function becomes easier to reason, test, and safer to change reducing runtime incidents and risks. 

<img width="634" height="532" alt="Screenshot 2025-08-22 at 13 13 51" src="https://github.com/user-attachments/assets/b3c6311d-bad9-44e4-8498-3fc0f8a948a6" />

# Identifying and Fixing Code Smells

A code smell is a characteristic in the source code that indicates a deeer problem or potential issue with the design rather than an error or bug. 

## Examples of Code Smells

Magic Numbers and Strings: Using hardcoded values instead of constants.
<img width="634" height="236" alt="Screenshot 2025-08-22 at 13 48 58" src="https://github.com/user-attachments/assets/c31182d2-0517-4ccf-99c2-f60680c40ad6" />

Long Functions: Functions that do too much and should be broken into smaller parts.
<img width="634" height="642" alt="Screenshot 2025-08-22 at 13 50 12" src="https://github.com/user-attachments/assets/e7b1f7cc-bc73-47c7-9be4-1dfe35ecbbec" />

Duplicate Code: Copy-pasting logic instead of reusing functions.
<img width="634" height="184" alt="Screenshot 2025-08-22 at 13 51 30" src="https://github.com/user-attachments/assets/c79124f1-02cd-4e8e-a82a-01bfe625b575" />

Large Classes (God Objects): Classes that handle too many responsibilities.
<img width="634" height="248" alt="Screenshot 2025-08-22 at 13 53 00" src="https://github.com/user-attachments/assets/014f0981-d3af-4de7-8315-138fe98cbf60" />

Deeply Nested Conditionals: Complex if/else trees that make code harder to follow.
<img width="634" height="314" alt="Screenshot 2025-08-22 at 13 56 38" src="https://github.com/user-attachments/assets/41246f4e-d81e-4e78-9d00-19672bb9b88f" />

Commented-Out Code: Unused code that clutters the codebase.
<img width="634" height="105" alt="Screenshot 2025-08-22 at 13 57 29" src="https://github.com/user-attachments/assets/71e20541-1805-40ea-9223-f0bd4524db35" />

Inconsistent Naming: Variable names that don't clearly describe their purpose.
<img width="634" height="118" alt="Screenshot 2025-08-22 at 14 07 24" src="https://github.com/user-attachments/assets/21dd59a2-74e8-4c6c-be5a-09b5f6b4901a" />

Breaking long functions into small helpers made the intent of each step clear at a glance. Extracting constants gave names to important values and put them in one place, so changing a rate or fee is safe and quick. Removing duplicates reduced the number of places to update when rules change. Splitting the large class by responsibility made each class easier to test and reason about, and I can swap implementations without touching unrelated parts. Guard clauses flattened complex branches, so edge cases stand out. Deleting commented‑out code removed noise, which makes real logic easier to find. Consistent names lowered the mental load because patterns repeat across the codebase.

Cleaner code makes it easier to find the cause when something breaks, which is why it is important to avoid code smells. When breaking down a long function into smaller ones, we can detect easily which function broke down and fix only that section. When we use constants instead of hard-coded numbers, we minimise changes when something goes wrong. Simple conditionals also help to make it obvious which branch ran. Fewer moving parts means fewer side effects and clearer traces.

# Static Analysis Checks in CI/CD

# Code Formatting and Style Guides

## Why is Code Formatting Important?

Code formatting is important because it keeps the codebase consistent, making it easier for different developers to read and understand each other's code. It also reduces confusion and makes errors easier to spot.

## What issues did the linter detect?

Running eslint, it detected unusable variables, missing semicolons, some inconsistent spacing in my code. Although they are small mistakes and may not cause errors, they can cause bugs and make the code more difficult to read and follow if not fixed.

## Did formatting the code make it easier to read?

The code is much easier to read after formatting the code. The indentation and spacing are consistent which made the structure more clear. The code also looks more professional and readable.

# Writing Unit Tests for Clean Code
