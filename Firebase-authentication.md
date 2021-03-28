As of April 2021, Oppia uses [Firebase](https://firebase.google.com/docs/auth) to handle user authentication. Log-in sessions are tracked using HTTP session cookies. The name of the session cookie is defined by `feconf.FIREBASE_SESSION_COOKIE_NAME = 'session'`.

For developers' convenience, the only thing needed to sign-in is an email address. A password will automatically be generated for the account. The password is the md5 hash of the email address. **This does not happen in production!** Production redirects users to the Google sign-in page instead (hence, _real_ Oppia users require a real Google account).

# Creating an Administrator account

## 1. Sign in with `testadmin@example.com`
![image](https://user-images.githubusercontent.com/5094060/112760738-1abfb500-8fc6-11eb-9e72-64d30a1aa2cb.png)

## 2. Add custom claims to a Firebase account

1. Sign in with any email address.
![image](https://user-images.githubusercontent.com/5094060/112760672-daf8cd80-8fc5-11eb-807e-59257023fa64.png)

2. Go to <a href="http://localhost:4000/auth" target="_blank">http://localhost:4000/auth</a>.

3. Find the corresponding Firebase account, click on the "3 dots" button, then click on **Edit user**.
![image](https://user-images.githubusercontent.com/5094060/111571879-e3f3ce80-877d-11eb-9353-aca9f60dc858.png)

4. Set the Custom Claims value to `{"role":"super_admin"}` then click **Save**.
![image](https://user-images.githubusercontent.com/5094060/111571913-fc63e900-877d-11eb-82ad-930b9b84fef6.png)

5. Sign out and sign back in to refresh your session cookie.

6. **DONE!** You should now have access to the admin page: ![image](https://user-images.githubusercontent.com/5094060/111572389-db4fc800-877e-11eb-8d56-0a5826db4a63.png)