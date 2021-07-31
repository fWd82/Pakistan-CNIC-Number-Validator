# Pakistan CNIC Number Validator
RegEx for validating CNIC numbers of Pakistan

`CNIC` stands for `Computerized National Identiry Card`. There are two ways we can actually write CNIC numbers: 
1. `12345-1234567-1`
2. `1234512345671`

One with dashes and one with dashes but not mixed with other.

# Only Allow Dashes

    ^([0-9]{5})-?([0-9]{7})-?([0-9]{1})$
Example: `12345-1234567-1`

# Don't Allow Dashes and Spaces

    ^([0-9]{5})([0-9]{7})([0-9]{1})$
Example: `1234512345671`    

# FINAL - Allow Dashes or Spaces but not both

    ^(([\d]{5})-([\d]{7})-([\d]{1}))|(([\d]{5})([\d]{7})([\d]{1}))|(([\d]{5}) ([\d]{7}) ([\d]{1}))$

This is a mixture of three different regex.  
Test it online on [RegExr](https://regexr.com/62tbn) or [regex101](https://regex101.com/r/Y6NSdd/1)
    
### Allow these: 
    1234512345671
    12345-1234567-1

### Don't Allow
    12345 1234567-1
    12345-1234567 1
    12345123456718
    12345-1234567-71
    12345-12345678-1


### Tip
The last digit says gender of citizen. You can extract gender entity only by checking for last value. If it is `Even Number` its female, while `Odd Number` is used for `Male`, You can do it only if your users alowed this, you can only know someone gender if only they want you to know.

