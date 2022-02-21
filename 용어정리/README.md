용어를 정리하는 곳이다.
===

## UUID란 무엇인가?

- UUID는 Universally unique identifier의 약자로, 정보 식별을 위하여 사용되는 식별자이다.
- 128-bit 숫자로 이루어져 있다.
- UUID의 장점은 데이터들이 나중에 단일 DB로 통합되거나, 같은 채널에서 전송되더라도 식별자가 중복될 확률이 매우 낮다는 점이 있다.
- Microsoft의 S/W에서는 GUID라고 불린다.

## UUID  Format

- canonical 텍스트 표현에서, UUID는 16octets가 32hex 숫자로 표현되고, hypen(-)으로 구분된  5개의 그룹으로 이루어짐
- 8-4-4-4-12 형식
- 123e4567-e89b-12d3-a456-426655440000
- xxxxxxxx-xxxx-Mxxx-Nxxx-xxxxxxxxxxxx
- M은 4bit로, Version을 의미
    - 위 예제에서는 M=1, version=1
- N은 1-3bit로, Variant를 의미
    - 위 예제에서 N=a(=10xx), variant=1
- 5개의 그룹은 순서대로 아래를 의미함

    UUID record layout

    1. time_low (bytes = 4, hex digits = 8)
        - 시간의 낮은 32bits 정수
    2. time_mid (bytes = 2, hex digits = 4)
        - 시간의 중간 16bits 정수
    3. time_hi_and_version (bytes = 2, hex digits = 4)
        - 최상위 비트의 4비트 버전 , 그 다음 상위 12비트
    4. clock_seq_hi_and_res/clock_seq_low (bytes = 2, hex digits = 4)
        - 최상위 비트에서 1~3비트 "변형"과 13~15 비트 클럭 시퀀스
    5. node (bytes = 6, hex digits = 12)
        - 48비트 노드 ID

## UUID의 이점
- UUID는 128-bit로 이루어진 "실용적인 측면에서 충분히 고유한" universal 식별자이다
- UUID의 고유성은 중앙 등록 기관(예를 들면 DB서버) 등에 의존되지 않고, standard method를 통해 독립적으로 생성 가능하다.
- 별도로 분리되어 있던 데이터들을 통합하거나, 하나의 채널에서 전송하더라도 충돌이 발생하지 않는다.
- UUID는 널리 채택되어 있고 많은 컴퓨팅 플랫폼들에서 UUID 생성, 파싱을 지원하고 있음
    - ex) Exposed의 UUIDTable class