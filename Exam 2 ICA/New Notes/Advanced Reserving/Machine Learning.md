## Goal

- Look at the individual claims (not on aggregate like we are used to)

## Advantages

- aggregate methods neglect individual claims behavior
- features can be dynamic in the model (stochastic features)

## How it works

- Machine learning—specifically **regression trees (CART)**—is used to estimate the **transition probabilities** governing whether a claim will:
	- remain open or close next period
	- generate a payment next period
- These probabilities are then iterated forward to obtain the **expected total number of future payments**, i.e., the **ultimate claim count**.
- RBNS = Reported but not settled
- For IBNR claims, we used Chain Ladder to determine the future reported claims count
	- this means that for these claims we cannot provide individual claim specific predictions because we do not have feature information.
	- We simulate the feature needed for the ML process, so then we can predict how claims will evolve (This is implied by the use of a homogeneous marked Poisson process.)
