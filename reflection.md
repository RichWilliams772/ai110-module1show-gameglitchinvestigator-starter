# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
---
the attempts on the side bar said it was supposed to be 8; however I only recieved 7 attempts 

The range is 1-100; however im allowed to input number in the negative and above 100, Along with the secert number changing and the hints being wrong 
## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used chatgpt to help me through the steps of the project.

I was getting a zsh: command not found: pip error and chatgpt fixed my error because it realized i was on mac and my mac uses the python3 command instead. 
---
the ai sugggestion that was misleading was chatgpt trying to make me put in the bash commands on mac terminal instead of vs code 

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?
I decided a bug was fixed by rerunning the game and checking if the issue no longer appeared. I compared the behavior before and after the change to make sure the game worked as expected.

One test I ran was manually starting a new game and making several guesses to check if the attempts counter and game-over message updated correctly. This helped confirm that the game state was working properly. AI helped me understand which parts of the code controlled the game logic, which made it easier to know what to test.
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---
Based on your code, you can answer it like this:

The secret number kept changing because the app reruns whenever the user interacts with it, and the original version likely generated a new random number each time. That meant every guess could accidentally be checked against a different secret number.

I would explain Streamlit reruns like this: every time you click a button or type something, Streamlit runs the whole script again from top to bottom. Session state is what lets the app remember important values between reruns, like the secret number, score, and attempts.

The change that made the secret number stable was saving it in `st.session_state` with `if "secret" not in st.session_state: st.session_state.secret = random.randint(low, high)`. That way, the number is only created once and stays the same until a new game starts.


## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
One habit I want to reuse in future projects is testing the program step-by-step after making changes instead of assuming the code works. Running the app frequently helped me catch bugs early.

Next time I work with AI on a coding task, I would verify its suggestions more carefully instead of assuming they are correct. I would test the code and read through the logic before applying changes.

This project showed me that AI-generated code can look correct but still contain logical bugs. It made me realize that developers still need to understand and debug the code rather than relying on AI completely.