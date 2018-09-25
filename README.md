# indiko
the amnesic pwd manager

# why
can't remember my passwords, nor want a pwd manager account

# how
enter your master pwd, then your account [reminder] and press the current year button

# security
* No dependencies on external libraries
* Just a single HTML file with some easily auditable javascript
* Uses PBKDF2 from your browser crypto API (remember, no external dependencies) with 100.000 iterations
* It derives a 192 bits pwd (32 chars in Base64) from your master password with your account [reminder] + year as salt

# but
* Can my master pwd be smaller than 16 chars? *No*
* Do I need to remember the year for my password? *Yes. Or change your passwords on new year's day*
* My password expires in 90 days! *Use the quarter 'Q1-Q4' buttons*
* I need the password from five years ago! *Press the previous year four times*
* My service doesn't allow 32 char passwords! *Use another service*
* It doesn't work with {browser}? *Try Chrome*
* But I want to use {browser}? *It needs support for crypto [and copy] APIs. Try the latest version of your preferred browser*
* I don't trust your website! *Download the HTML file and open it in an [isolated computer](https://en.wikipedia.org/wiki/Air_gap_(networking))*
* There are better [PBKDF2 alternatives!](https://en.wikipedia.org/wiki/PBKDF2#Alternatives_to_PBKDF2) *Not in the browsers crypto API to my knowledge and I don't want to rely on external dependencies*
* The fulfilPWDRequirements function reduces the bit length of the pwd! *Yes, it ALWAYS changes the first four chars to "lower+upper+digit+simbol", and it reduces from (64^32) to (64^28)x(26^2)x10x32 different passwords, 80934920751979755332050202371375703759864659890321489920 in total*
* The fulfilPWDRequirements can be improved! *Yes, but it's simpler like this. If you are really [worried about the bit reduction](https://xkcd.com/538/) it's MUCH easier to change the 192 bits to 256*
* There is a flaw in your implementation! *Please, open a merge request*
* Why this name? [*Indiko*](https://en.wiktionary.org/wiki/indiko)
