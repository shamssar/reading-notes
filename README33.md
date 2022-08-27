# Login and Auth:
## What is Role-Based Access Control (RBAC)?
Role-based access control (RBAC) restricts network access based on a person's role within an organization and has become one of the main methods for advanced access control. The roles in RBAC refer to the levels of access that employees have to the network.

## Examples of (RBAC)
Some of the designations in an RBAC tool can include:

* Management role scope – it limits what objects the role group is allowed to manage.
* Management role group – you can add and remove members.
* Management role – these are the types of tasks that can be performed by a specific role group.
* Management role assignment – this links a role to a role group.
By adding a user to a role group, the user has access to all the roles in that group. If they are removed, access becomes restricted. Users may also be assigned to multiple groups in the event they need temporary access to certain data or programs and then removed once the project is complete.

Other options for user access may include:

- Primary – the primary contact for a specific account or role.
- Billing – access for one end-user to the billing account.
- Technical – assigned to users that perform technical tasks.
- Administrative – access for users that perform administrative tasks.
## Benefits of (RBAC)
Reducing administrative work and IT support.
Maximizing operational efficiency.
Improving compliance.
## Best Practices for Implementing (RBAC)
Here are a few things to map out first:

Current Status.
Current Roles.
Write a Policy.
Make Changes.
Continually Adapt.

# react-cookie:
```
npm install react-cookie
```
### useCookies([dependencies])
Access and modify cookies using React hooks.
```
const [cookies, setCookie, removeCookie] = useCookies(['cookie-name']);
```

### Cookies Methods :
```
get(name, [options])
```

Get a cookie value

* name (string): cookie name
* options (object): doNotParse (boolean): do not convert the cookie into an object no matter what
```
getAll([options])
```
Get all cookies

* options (object):
 - doNotParse (boolean): do not convert the cookie into an object no matter what
 ```
set(name, value, [options])
```
Set a cookie value

* name (string): cookie name
* value (string	object): save the value and stringify the object if needed
* options (object): Support all the cookie options from RFC 6265
- path (string): cookie path, use / as the path if you want your cookie to be accessible on all pages
- expires (Date): absolute expiration date for the cookie
- maxAge (number): relative max age of the cookie from when the client receives it in seconds
- domain (string): domain for the cookie (sub.domain.com or .allsubdomains.com)
- secure (boolean): Is only accessible through HTTPS?
- httpOnly (boolean): Can only the server access the cookie? Note: You cannot get or set httpOnly cookies from the browser, only the server.
- sameSite (boolean	none	lax	strict): Strict or Lax enforcement
```
remove(name, [options])
```
Remove a cookie

* name (string): cookie name
* options (object): Support all the cookie options from RFC 6265
path (string): cookie path, use / as the path if you want your cookie to be accessible on all pages
expires (Date): absolute expiration date for the cookie
maxAge (number): relative max age of the cookie from when the client receives it in seconds
domain (string): domain for the cookie (sub.domain.com or .allsubdomains.com)
secure (boolean): Is only accessible through HTTPS?
httpOnly (boolean): Can only the server access the cookie? Note: You cannot get or set httpOnly cookies from the browser, only the server.
sameSite (boolean	none	lax	strict): Strict or Lax enforcement