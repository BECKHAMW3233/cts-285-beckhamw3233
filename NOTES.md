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

After the restart, what did the program remember? It remembered my first wrong answer, 55, so practice resumed at Try 2.

Which file made that possible? `dataman_store.json`.

## Part 3. The interface change [S1]

What did you change in `app.py`? I changed the retry message shown after a wrong first answer.

Why did no test need to change? The business rules and data behavior stayed the same; only interface text changed.

## Part 4. The rule in the real library [S2]

The rule is in `dataman/logic.py`, in `MemoryBank.add_problem`.

## Part 5. The red test [S2]

Before removing the rule, my guess is that `test_eleventh_problem_is_refused` will fail.

With the rule removed from the library, the screen showed `Added. Set holds 11.`

With the rule removed, `tests/test_logic.py::test_eleventh_problem_is_refused` failed. My guess was correct.

## Part 6. The data swap [S2]

A real database would replace `dataman/store.py`.

`dataman/logic.py` holds the rules and does not need to change when the database changes.

## Reflection [S2]

I changed the interface layer in `app.py` by updating the retry message and making JSON storage the default. The business rules in `dataman/logic.py` stayed the same in the final version. The data layer in `dataman/store.py` also stayed the same and still provides both memory and JSON stores. Changing the default did not change how attempts are saved or when answers are revealed.

## Beta feedback (optional)

This bonus is a beta test. Which step took longer than its time? What confused you? Write it here. Your answer helps the next class.
