Это один из способов хранения данных пользователя.
- Simple Storage with [In-Memory Authentication](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/in-memory.html#servlet-authentication-inmemory)
- Relational Databases with [JDBC Authentication](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/jdbc.html#servlet-authentication-jdbc)
- Custom data stores with [UserDetailsService](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/user-details-service.html#servlet-authentication-userdetailsservice)
- LDAP storage with [LDAP Authentication](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/ldap.html#servlet-authentication-ldap)


[InMemoryUserDetailsManager] в Spring Security реализует интерфейс [UserDetailsService] для обеспечения поддержки аутентификации на основе имени пользователя/пароля, которые хранятся в памяти. [InMemoryUserDetailsManager] обеспечивает управление пользовательскими данными путем реализации интерфейса UserDetailsManager. Аутентификация на основе пользовательских данных используется Spring Security, когда она настроена на принятие имени пользователя и пароля для аутентификации.