# Planned risk and an opening gap

A close-to-open gap can move a price past a planned stop before the next available trade. This drill separates the amount used to size a hypothetical position from the loss at a specified simulated fill.

## Exercise

These numbers are invented for practice. Assume an account has a planned dollar-risk budget of $100 for a hypothetical long position. The entry is $50.00 per share and the stop threshold is $48.00. Ignore fees and capital constraints. At the next session, the first available exit fills the entire position at $46.50.

1. How many whole shares fit the planned risk budget?
2. What is the modeled loss at the actual exercise fill?
3. What disclosure would help a reader distinguish the stop threshold from the fill?

## Check your answer

The planned risk is $50.00 − $48.00 = $2.00 per share, so the position contains 50 shares. At the specified fill, the modeled loss is 50 × ($50.00 − $46.50) = $175.00. The gap adds $75.00 to the planned amount.

Keep three fields visible: the stop threshold, the simulated execution price, and the timestamp and data that support the assumed fill. In a daily-bar simulation, the opening price alone does not establish which orders could have filled or how many shares were available. The fill in this exercise is stipulated to isolate the arithmetic.

For an optional practice check, the [eStockes Academy position-sizing lesson](https://estockes.com/education/risk-and-sizing/sizing-from-stop-distance?utm_source=github&utm_medium=community&utm_campaign=overnight_gap_exercise) covers the sizing formula and what changes when a stop is passed. See whether you can find the discussion of gaps before answering question 3.

This exercise is for education.
