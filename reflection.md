# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

##### The game opened and showed "Guess a number between 1 and 100" with 7 attempts. The hints were backwards, so guessing a number higher than the secret said "Go higher". It also accepted guesses outside 1 to 100.#####

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input  | Expected Behavior | Actual Behavior | Console Output / Error |
|------------------|-------------------|-----------------|------------------------|
| 1. guessed 55 (secret was 47)| "go lower" hint  | it said "go higher" | no error shown at the first guess though it should have instructed to lower the guess|


| 2. guessed 555 (secret was 47) | "error message" as it is <100| "go higher" | it asked for "go higher 2 more times though I inserted 55555 - higher than instructed >100 and it still kept asking for higher number until I was out of attempts |


| 3. guessed 45 (secret: 64)| "go higher" | "go lower" 3 more times as I guessed 30, 10, 5 as it kept asking for "go lower" |"Out of attempts! The secret was 64. Score: -20" |

| 4. Won the game (peaked the secret), clicked New Game, then guessed | A fresh game starts | Game was still stuck or in the old state | No error shown |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

### Went through the app.py code line-by-line and understood the logic of the hint is reversed and istead of saying "go lower" when the guessed number is too high - it keeps saying "go higher" due to such code: if guess > secret:
##### return "Too High", "📈 Go HIGHER!"

# to make sure my understanding is right, I copy/pasted the app.py code to claude to check and it confired the error I noted above. 
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
