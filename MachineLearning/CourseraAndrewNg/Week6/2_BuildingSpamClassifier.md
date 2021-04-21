# Building Spam Classifier

## Supervised Learning
- x: features of email
- y: spam(1) or not spam(0)

Features x: choose 100 words indicative of spam/not spam.
e.g. my name, deal, buy, discount, etc.

Then we will have a matrix:
`[0 1 1 1 ...]` for `[not find Qi, find deal, find buy, find deal, ...]`.

x(j): 1 if word j exists in the email; 0 otherwise;

