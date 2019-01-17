# PollEvBot

PollEvBot is a script that automatically answers polls from PollEverywhere. It continually checks if a specified poll user has opened any polls. Once a poll has been opened, the bot finds and submits the correct response to PollEverywhere, or submits a random one if the poll has no correct response.

Note: This script was specifically designed to access PollEverywhere through MyUW. 

## Dependencies

[Requests](https://github.com/requests/requests), [BeautifulSoup](https://github.com/waylan/beautifulsoup)

## Usage

To use the script as is, you will need a MyUW Net ID and password.

First, install `PollEvBot`:
```
pip install PollEvBot
```

Set your username (UW Net ID), password, and desired poll host:
```python
user = 'MyUW Username (@uw.edu email)'
password = 'MyUW Password'
host = 'My Favorite Teacher'
```

And run the script. If you're importing PollEvBot as a library, you will need to use run(), which takes the following keyword arguments:
 * `delay`: Specifies how long the script will wait between queries to check if a poll is open (seconds).
 * `wait_to_respond`: Specifies how long the script will wait to respond after finding an open poll (seconds).
 * `clear_responses`: If true, clears any previous responses to a poll before responding.
 * `run_forever`: If true, runs the script forever.
 * `ignore_prev_polls`: If true, does not respond to polls that this script has already responded to. For safety, this parameter should remain set to true; continuous failed queries may look suspicious and can result in an ip ban.
    
Pretty simple to use:
```python
from PollEvBot.src import Poll

user = 'MyUW Username (@uw.edu email)'
password = 'MyUW Password'
host = 'My Favorite Teacher'

with Poll(username=user, password=password, poll_host=host) as poll:
    poll.run(delay=5, wait_to_respond=5, run_forever=True)
```
Alternatively, you can input your login credentials into main.py and run it from there.

## Disclaimer

I do not promote or condone the usage of this script for any kind of academic misconduct or dishonesty, including but not limited to cheating on in-class poll quizzes or spoofing attendance polls. I wrote this script for the sole purpose of educating myself on cybersecurity and web protocols, and cannot be held liable for any indirect, incidental, consequential, special, or exemplary damages arising out of or in connection with the usage of this script.