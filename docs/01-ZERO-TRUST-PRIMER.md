# 제로 트러스트 입문 — 데모랩 적용 예시

> [DUMMY-DATA.md](DUMMY-DATA.md)

## 원칙 → Lab 조치 매핑

| 원칙 | 데모랩 Lab 조치 (가상) |
|------|------------------------|
| 명시적 검증 | `jmp-lab-01` → `10.60.0.0/24` SSH만 허용 |
| 최소 권한 | `bff-api` SA는 `orders-db:5432`만 |
| 가정 침해 | 세그먼트 간 east-west 기본 거부 |

## 서비스 ID 기반 정책 (예시)

| 출발 SPIFFE ID | 목적 | 포트 |
|----------------|------|------|
| `spiffe://demolab/lab/bff-api` | `spiffe://demolab/lab/orders-db` | 5432 |

실제 SPIRE/서비스 메시는 범위 밖 — **문서 연습용**입니다.
