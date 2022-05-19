# Spring Boot - JWT

### Intro
Spring Boot, Spring Security를 활용한 JWT 인증과 인가 처리 구현

### Codes

#### TokenProvider
토큰의 생성, 토큰의 유효성 검증등을 담당

- createToken: 토큰 생성
- getAuthentication: 토큰 정보를 이용해 Authentication 객체 리턴
- validateToken: 토큰 검증

#### JwtFilter
JWT를 위한 커스텀 필터

- doFilter: 토큰의 인증정보를 SecurityContext에 저장하는 역할 수행
- resolveToken: Request Header에서 토큰 정보를 꺼내오기 위한 메서드

#### JwtSecurityConfig
JWT를 적용할 Security Config, Security 로직에 필터를 등록

#### JwtAuthenticationEntryPoint
유효한 자격증명을 제공하지 않고 접근할 시 401 Unauthorized 에러 리턴

#### JwtAccessDeniedHandler
필요한 권한이 존재하지 않는 경우 403 Forbidden 에러 리턴
