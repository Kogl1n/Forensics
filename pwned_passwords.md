# pwnedpasswords
returns the number of passwords that are in the pwnedpasswords database  
based on hashing to preserve anonymity, e.g. no plaintext passwords are transmitted.  

## principle
The Pwned Passwords API utilizes the concept of k-anonymity.
Formally, a data set can be said to hold the property of k-anonymity, if for every record in a released table, 
there are k−1 other records identical to it.
This allows us to only provide the first 5 characters of the SHA-1 hash of the password in question. 



Likewise, if a password looks like a SHA-1 hash (i.e., ) but is actually a user-provided 
password, set plain_text to True, so that the library knows to hash it before sending it to the API.


## apply
pwnedpasswords.check("testing 123")  
# Returns 1  
pwnedpasswords.check("mypassword")  
# Returns 34729  

Already hashed passwords that match the regular expression [0-9a-fA-F]{40} like "b8dfb080bc33fb564249e34252bf143d88fc018f"  
are automatically detected. This can be disabled with plain_text=True argument.

## install
pip install pwnedpasswords  



