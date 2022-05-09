## CI/CD
### CI/CD ?
1. CI(Continuous Intergration)
>Build, Test를 실시하는 프로세스를 말하며 이러한 통합 프로세스를 상시로<br> 실시해주는 것을 CI라고 한다. 즉, 통합을 지속적으로 수행하는 것이다.

    - CI에 필요한 것들
        - 형상관리: Git, SVN 등
        - Build Tool: Grade, ant, make 등
        - CI Tool: Jenkins, Travis CI, Bitrise 등

2. CD(Continuous Delivery or Continuous Deploy)
> 짧은 주기로 개발중인 소프트웨어를 배포하고 그 과정을 자동화 하는것
### CI/CD 가 필요한 이유
전에는 한 페이지를 개발할때마다 테스트 -> 커밋 -> 머지 과정을 개발자가 수동적으로 진행했다. 이러한 부분을 자동화 하기 위해 사용하는것 같다.<br>
많은 부분을 수정하고 한 번에 테스트 하지 말고, 자주 여러번 수정/배포 하면서 개발의 효율성과 릴리즈 기간을 단축시킬수 있다.<br>
