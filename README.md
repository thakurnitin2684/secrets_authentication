# secrets_authentication
##  Demo project to implement authentication from scratch

### Below is the explanation of each commit. You can checkout code for each level.

### Level 1 : MongooDB
- It is simply using mongoose and mongodb for storing user details and retrieving them.

### Level 2: mongoose-encyption
- It uses moongoose encyption npm package.
- Then uses the plugin on userSchema using a secret.
- Secret is kept in env file which requires dotenv plugin.

### Level 3 : Hashing 
- So previously we needed an encryption key so to avoid that we will use
	hashing so we don't require any encryption key.
- So we will use MD5 npm package.
- we will simply hash our password like this : const password = md5(req.body.password);

### Level 4:  Salting using bcrypt
- Hashing is still hackable because you can generate 20 Billion MD5 hashes per second
	(that we previously used).so it won't take much time for hacker to crack your password.
		
- So we add a random set of chars to it, it is called **salting**.
- We will use bcrypt npm package.
- For comparision you can generate 17000 bcrypt hashes per second , so if your password is strong enough 
	with current computational capabilities, it may take years for hacker to crack your password.
- we use 10 rounds of salting here.

### Level 5:  Cookies and sessions.
- **cookies**: are like a datastore in the browser itself, for eg if you put something in basket in amazon
		 it will create a cookie and next time you open amanzon, the server will see the cookie and get the
		 information about what you were seeing last time and show it to you.
	
- **Session**: is like a time period until your cookie is alive. for eg in login you enter your credentials,
 		so a cookie will be created and the server will not ask for login again and again for that time period until 
		you log out because a cookie is still there and it will be destroyed once you log out.

- so we will use npm packages passport.js, express-session to implement cookies and session.
		
### Level 6: Third party auth
- All of this can be provided by third party auth services like google facebook.
- See level 6 code to see the implementation of passport-google-oauth20.
