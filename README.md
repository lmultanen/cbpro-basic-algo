This repo is intended to be practice for setting up a basic trading algo to be used with Coinbase PRO, following various tutorials I found online.

Some things I learned so far getting the basics set up:
- the cbpro module is not compatible with python 3.11 (or even 3.10), so I had to install and use pyenv to change my global python version on my machine to 3.9

Have been able to set up the check buy/sell trigger methods and make buy/sale methods from the client.ipynb notebook that I tested in the PublicWebsocketClient class into my (private) live_client.py file, where I am now using a new class derived from the cbpro.AuthenticatedClient class.
- Currently have just been using sandbox data still, but after everything else in place will generate some live keys and fund account with some money to see how it performs.
- Before that, need to implement some sort of tick function still, likely just will check bid/ask spread every few seconds for a minute tops when called.
- Reason for having such a limited scope for ticking is that I would like to try to set up a lambda function on AWS and use event bridge to invoke this tick function maybe every 30 mins or so (depends on what costs might be). Ideally, will not want to incur any charges while still testing, so will try to keep usage minimal initially.