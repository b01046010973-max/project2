# Linux C-Build
Linux 환경 C언어 개발 및 환경 구축

1. 프로젝트 개요
Windows 환경에서 Linux 서버(Ubuntu)에 접속하여, CLI 환경 전용 도구들을 이용해 C언어 프로그램을 작성하고 빌드하는 전 과정을 실습했습니다.

<br>

2. 주요 작업
- 에디터 활용: `vi` 에디터를 사용하여 소스 코드(`taskk.c`) 작성 및 수정.
- 컴파일러 사용: `gcc`를 이용해 chmod없이 소스 코드를 실행 파일(`result_f`)로 빌드.
- 권한 관리: `sudo` 명령어를 통한 시스템 디렉터리 접근 권한 제어.

<br>

3. 트러블슈팅
  - 문제: `vi`가 수정 시(`:wq!`) 결과가 저장되지 않는 것과 에러 경고를 보고 스왑 파일 존재 여부에 가능성을 두어 .swp 삭제를 위한 `rm` 명령어를 사용했으나, "Is a directory" 에러가 발생하며 파일 삭제 실패.
<img width="400" height="100" alt="pro2_원인" src="https://github.com/user-attachments/assets/9a9485fd-95d0-442b-98f0-40eeccf80107" />

  - 원인: 현재 위치가 이미 `/var/www/html`임에도 불구하고, 삭제 명령에 다시 절대 경로(`/var/www/html/`)를 포함하여 입력. 
  - 이 과정에서 명령어 끝에 파일명만 정확히 붙지 않고 경로 자체가 인자로 전달되면서, 시스템은 파일이 아닌 '디렉터리'를 삭제하려는 시도로 간주.
  - 최종 해결: 중복된 경로 입력을 배제하고, 해당 위치에서 파일명만 정확히 지정하여 환경을 정리한 후, 실습을 완수함.

<img width="400" height="150" alt="pro2_완성본" src="https://github.com/user-attachments/assets/f6d1f5a8-bc4c-40c2-8a34-b2d0d19df504" />


  
