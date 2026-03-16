# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
      Game Purpose
The purpose of the game is to let users guess a randomly generated secret number based on a selected difficulty level. The game provides feedback after each guess (too high, too low, or correct) and is meant to be an interactive way to practice logic and state management using Streamlit.
- [ ] Detail which bugs you found.
      Bugs Found

Incorrect hint feedback
The hint messages were reversed. When my guess was lower than the secret number, the game incorrectly told me to “Go Lower,” and when my guess was higher, it told me to “Go Higher.”

“New Game” button not functioning
The “New Game” button did not properly reset the game state. The number of allowed attempts was not reset, and there was no way to start a new round after finishing a game.

Difficulty setting not working correctly
The difficulty selection had no effect on gameplay, as the secret number range remained 1–100 regardless of the chosen difficulty. Additionally, the difficulty ranges were misarranged: Normal mode had a larger range than Hard mode, making Normal unintentionally more difficult than Hard.
- [ ] Explain what fixes you applied.
      Fixes Applied
I fixed the difficulty bug by increasing the number range for Hard mode so that it was more challenging than Normal. I also stored the secret number in Streamlit’s session state and ensured it was only generated once per game, which gave the game consistent behavior across user interactions.
      

## 📸 Demo

- [ ] [Insert a screenshot of your fixed, winning game here]
      

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
