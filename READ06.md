# Authentication

#### in the context of web applications is commonly performed by submitting a username or ID and one or more items of private information that only a given user should know.

#### Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible. Hashing is the greatest way for protecting passwords and considered to be pretty safe for ensuring the integrity of data or password.

### PROBLEMS WITH CRYPTOGRAPHIC HASH ALGORITHM:
- Brute Force attack
 an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value
 - Hash Collision attack
 Hash functions have infinite input length and a predefined output length 
 MD5, SHA1, SHA2 are vulnerable to Hash Collision Attack 


 ### Basic Access Authentication
 Basic access authentication is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.

 ### Install via NPM
 npm install bcrypt
 ### Usage
 async (recommended)
const bcrypt = require('bcrypt');
const saltRounds = 10;
const myPlaintextPassword = 's0/\/\P4$$w0rD';
const someOtherPlaintextPassword = 'not_bacon';

### To hash a password:
* Technique 1 (generate a salt and hash on separate function calls):

bcrypt.genSalt(saltRounds, function(err, salt) {
    bcrypt.hash(myPlaintextPassword, salt, function(err, hash) {
        // Store hash in your password DB.
    });
});

* Technique 2 (auto-gen a salt and hash):

bcrypt.hash(myPlaintextPassword, saltRounds, function(err, hash) {
    // Store hash in your password DB.
});

### To check a password:
// Load hash from your password DB.
bcrypt.compare(myPlaintextPassword, hash, function(err, result) {
    // result == true
});
bcrypt.compare(someOtherPlaintextPassword, hash, function(err, result) {
    // result == false
});




##### References 
- [Securing Passwords with Bcrypt Hashing Function](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)
- [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
- [node.bcrypt.js](https://www.npmjs.com/package/bcrypt)

---------------------------------------------------

[HomePage](README.md)