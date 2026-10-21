# NOTES: Three Layers

Your name: TODO

Fill each TODO. Write plain, short sentences. Do not delete the headings.

## Part 1. Predict, then find [S1]

Write your prediction before you open any code. Then search. In the last column, write each file the search finds and what that file does.

| Action | Search word | My prediction (file) | Files found and what each does |
|---|---|---|---|
| Prints "Not yet. Try again." | `Not yet` | `app.py` | `app.py` prints the retry message in the command-line interface. |
| Decides that the second miss shows the answer | `reveal` | `dataman/logic.py` | `app.py` displays a revealed answer; `dataman/logic.py` decides when to reveal it; `tests/test_logic.py` tests that the second miss reveals it. |
| Saves one attempt | `save_attempt` | `dataman/store.py` | `dataman/logic.py` calls `save_attempt` when an answer is submitted; `dataman/store.py` records attempts in memory or JSON. |
| Refuses the 11th problem | `SetFull` | `dataman/logic.py` | `app.py` catches and displays `SetFull`; `dataman/logic.py` defines it and enforces the 10-problem limit; `exercise/bank.py` is the Segment 2 practice implementation; `exercise/test_bank.py` tests its limit; `tests/test_logic.py` tests the library limit. |

Search command: `grep -rn "SEARCH WORD" --include=*.py .`

## Part 2. What the program remembered [S1]

After the restart, what did the program remember? the program recalled due to the json file the last attempt but would not let you continue past until you completed both attempts adn viewthe report

Which file made that possible? dataman_.json

## Part 3. The interface change [S1]

What did you change in `app.py`? you changed a output the program gives the user 

Why did no test need to change? nohting was changed as to hwo the program acutaly runs its supericial change that is more for user interface to replicate the original product

## Part 4. The rule in the real library [S2]

The same 10-problem rule exists in the real library. Write the file and the function name. TODO

## Part 5. The red test [S2]

With the rule removed from the library, what did the screen show? TODO

With the rule removed, which test failed? TODO

## Part 6. The data swap [S2]

A real database would replace which file? TODO

Which file holds the rules and does not change when the database changes? TODO

## Reflection [S2]

Write 3 to 5 sentences. Pick one layer. Say what you changed in it. Say what stayed the same in the other two layers. TODO

## Beta feedback (optional)

This bonus is a beta test. Which step took longer than its time? What confused you? Write it here. Your answer helps the next class.
