# EEL Finance - Provision of under/un-collateralized loans based on reputation based on WorldID.

## What is it?
This project develops reputation-based lending, where the reputation is tied to every person's Worldcoin passport, which is unique to every person. This eliminates the need for collateral, as the user's reputation acts as collateral for the loan. This allows us to substitute traditional bank loans that are dependent on credit scores, and are not usually available for most individuals, for on-chain identity based loans.

It intends to function akin to a standard lending protocol, but substitutes the need for collateral in-full, thus permitting users to take out under/uncollateralised loans, with a reputation-dependent system. Reputation is based on the user’s ability to repay the loan + interest on time, and dictates the amount that the user can borrow, and the interest rate of their loan.  

### Challenge to overcome
The main problem with this design is the abuse of the lending system. Anyone with an iris-verified WorldID would be able to borrow money - basically for free - which could lead to treasury drainage. The abuse would be hard to repeatedly execute, since always getting new Worldcoin IDs is unfeasible for a single person to do. The initial lent sum would not be a lot, so a person with malicious intentions wouldn’t have many incentives to take the money in the first place. However, a user that actually wants to borrow a proper loan, could ‘farm’ their reputation by borrowing and repaying their loans back on time. There is still a chance that they will run with the money once they ‘farmed’ enough reputation but it will be covered by borrowers with good intentions who pay their interest rates back.

The system will try to prevent non-returns as much as possible but, we do understand that it will be hard to implement in the blockchain world since we cannot take any legal action against the malicious actors, in this case, we admit that this problem exists and the solution we came up with is to trim our algorithms to account for those losses in interest rate (more) and initial borrowable amount (less) calculations.

If past payment history is non existent, we would give the borrower a low borrowable amount with, high interest rate to prevent abuse. These parameters need to be algorithmically calculated such that the amount is not too low, and the interest rate is not too high, and people would not abuse it too much (ratio based). If user’s payment history proves to be good - we decrease user’s interest rate and increase allowable borrowing amount.

Another option for mitigating non-repaid loans, is implementing collateral inversely proportional to the borrower’s reputation, where it becomes an increasingly lower percentage of their requested sum with increasing reputation.
