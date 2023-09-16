The [SecurityContext] is obtained from the [SecurityContextHolder]. The `SecurityContext` contains an [Authentication] object.

The [`Authentication`](https://docs.spring.io/spring-security/site/docs/6.1.2/api/org/springframework/security/core/Authentication.html) interface serves two main purposes within Spring Security:
- An input to [`AuthenticationManager`](https://docs.spring.io/spring-security/reference/servlet/authentication/architecture.html#servlet-authentication-authenticationmanager) to provide the credentials a user has provided to authenticate. When used in this scenario, `isAuthenticated()` returns `false`.
- Represent the currently authenticated user. You can obtain the current `Authentication` from the [SecurityContext](https://docs.spring.io/spring-security/reference/servlet/authentication/architecture.html#servlet-authentication-securitycontext).

The `Authentication` contains:
- `principal`: Identifies the user. When authenticating with a username/password this is often an instance of [`UserDetails`](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/user-details.html#servlet-authentication-userdetails).
- `credentials`: Often a password. In many cases, this is cleared after the user is authenticated, to ensure that it is not leaked.
- `authorities`: The [`GrantedAuthority`](https://docs.spring.io/spring-security/reference/servlet/authentication/architecture.html#servlet-authentication-granted-authority) instances are high-level permissions the user is granted. Two examples are roles and scopes.