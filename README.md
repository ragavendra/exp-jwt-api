# Express back end api with JWT auth
Cloned from this [repo](https://github.com/hagopj13/node-express-boilerplate) .

### User
By default in [.env.example](.env.example) file the authentication token is valid for about 30 minutes. The refresh token can be used upto 30 days.

Send verification email will send an email with the token which is valid for 10 minutes to verify the email and `isEmailVerified` is set to `true`.

Similarly reset password token is valid upto 10 minutes as well.

### How JWT tokens work/ are generated

#### For login
First when a user registers or logs in, a auth (30 min) and a refresh token(30 days) is generated or sent in the response.

After 30 min, the user has to send the refresh token in body as POST to `/v1/auth/refresh-tokens` to get a response similar to register or login.

#### For verify email or reset password
Similar to login, but refresh token is not sent.

### Create User
A user must be logged in to create an user with the `user` or `admin` roles. During register the user is created with `user` role.

### New endpoints
The logged in user can now get and update his user info.
