# Intro

In a typical two-factor authentication application, user authentication proceeds as follows: a user will enter username and password into a website or other server, generate a one-time password for the server using TOTP running locally on a smartphone or other device, and type that password into the server as well. The server will then also run TOTP to verify the entered one-time password. For this to work, the clocks of the user's device and the server need to be roughly synchronized (the server will typically accept one-time passwords generated from timestamps that differ by ±1 from the client's timestamp). A single secret key, to be used for all subsequent authentication sessions, must have been shared between the server and the user's device over a secure channel ahead of time. If some more steps are carried out, the user can also authenticate the server using TOTP.

# Reference

 - [Two-factor authentication](https://en.wikipedia.org/wiki/Two-factor_authentication)
 - [totp](https://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm)
 - [Hotp](https://en.wikipedia.org/wiki/HMAC-based_One-time_Password_Algorithm)
 - [one-time-passwords-hotp-and-totp](http://blogs.forgerock.org/petermajor/2014/02/one-time-passwords-hotp-and-totp/)