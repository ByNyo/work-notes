### Authentication
You need to know for example on a website the login data.

### Authorization
Checks if you have permission (are authorized) to for example log in.

### Basic
You just need the username and password when making a request.

### Token based
You need to have a unique token to access for example your account or making requests.

### JWT (***J***SON ***W***eb ***T***oken)
![[JWTImage.jpg]]
In JWT there is a secret encrypted key in the header that changes when the other data (for example login data) was changed so you can no longer login. That prevents you or unauthorized people from logging into the account of a different person.

## Video about Web Authentication
https://www.youtube.com/watch?v=LB_lBMWH4-s