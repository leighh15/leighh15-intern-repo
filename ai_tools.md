I have installed GitHub Copilot on VS Code and have utilised ChatGPT before for coding help and debugging. For this task, I tried ChatGPT to enhance its coding support. 

Generate code snippet:

My prompt for ChatGPT was:
"Can you create a python code snippet to determine if a user input has numerical characters in it?"
ChatGPT created the following snippet:
# Prompt user for input
user_input = input("Enter something: ")

# Check if any character is a digit
if any(char.isdigit() for char in user_input):
    print("Your input contains numerical characters.")
else:
    print("Your input does not contain any numerical characters.")

The code snippet provided the necessary code I required from my prompt. 

Debugging using AI:

My prompt for ChatGPT was:
"I have the following code, is it correct? I want to find the average without including 1:
numbers = [1, 2, 3, 4, 5]
print(sum(numbers)/len(numbers)-1)"

ChatGPT pointed out that my code will run without errors but the output will be incorrect. It provided me a fixed code:
numbers = [1, 2, 3, 4, 5]
filtered = [n for n in numbers if n != 1]
print(sum(filtered) / len(filtered))  # Output: 3.5

Learning new concept through AI:

My prompt for ChatGPT was:
"Can you give me a brief explanation of what SQL and how it works?"

ChatGPT gave me the following explanation:
<img width="655" height="859" alt="Screenshot 2025-08-15 at 10 22 43 am" src="https://github.com/user-attachments/assets/20044798-8ba1-470e-835c-fc8f658a8490" />

What worked well? What didn't?
I think ChatGPT was able to provide code snippets and debugging quite well. Though the examples were simple, I think given the right amount practice, it can further support in more complex coding. Personally, I find the explanations to be quite lacking for the new concept I asked ChatGPT to explain. It doesn't tell me where all the commands take place, and what it will look like when working with SQL. 

When do you think AI is most useful for coding?
Like my example for debugging, I think AI could be most useful when my code doesn't necessarily produce errors but will have incorrect output due to illogical code. Codes such as those are most dangerous because it can slip through many reviews without careful checking and testing, and AI can support in spotting these mistakes in the code. 
