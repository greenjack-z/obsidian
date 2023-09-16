Фреймворк для обеспечения [[Аутентификация|аутентификации]] и [[Авторизация|авторизации]] в спринг приложениях. Кроме этого обеспечивает [[Protection Against Exploits|защиту]] от популярных атак.

Spring Security обеспечивает интеграцию с многочисленными фреймворками и API. Ниже указаны общие интеграции, которые не являются специфичными для сервлетов или реактивных сред.
- [Cryptography](https://docs.spring.io/spring-security/reference/features/integrations/cryptography.html)
- [Spring Data](https://docs.spring.io/spring-security/reference/features/integrations/data.html)
- [Java’s Concurrency APIs](https://docs.spring.io/spring-security/reference/features/integrations/concurrency.html)
- [Jackson](https://docs.spring.io/spring-security/reference/features/integrations/jackson.html)
- [Localization](https://docs.spring.io/spring-security/reference/features/integrations/localization.html)

Spring Security интегрируется с контейнером сервлетов с помощью стандартного фильтра сервлетов. Это означает, что он работает с любым приложением, которое запускается в контейнере сервлетов. Более конкретно, вам не нужно использовать Spring в вашем приложении на основе сервлетов, чтобы воспользоваться преимуществами Spring Security.
- [Getting Started](https://docs.spring.io/spring-security/reference/servlet/getting-started.html)
- [Architecture](https://docs.spring.io/spring-security/reference/servlet/architecture.html)
- [Authentication](https://docs.spring.io/spring-security/reference/servlet/authentication/index.html)
- [Authorization](https://docs.spring.io/spring-security/reference/servlet/authorization/index.html)
- [OAuth2](https://docs.spring.io/spring-security/reference/servlet/oauth2/index.html)
- [SAML2](https://docs.spring.io/spring-security/reference/servlet/saml2/index.html)
- [Protection Against Exploits](https://docs.spring.io/spring-security/reference/servlet/exploits/index.html)
- [Integrations](https://docs.spring.io/spring-security/reference/servlet/integrations/index.html)
- Configuration
- [Testing](https://docs.spring.io/spring-security/reference/servlet/test/index.html)
- [Appendix](https://docs.spring.io/spring-security/reference/servlet/appendix/index.html)