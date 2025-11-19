# 데이터 테이블

CatWars 게임 데이터 테이블 구조와 스펙을 설명합니다.

> 원본 파일 위치: `0_참고자료/원본자료/EXCEL_DATA/`

---

## 데이터 구조

### Enums (열거형)
게임에서 사용하는 상수값 정의 (7개 파일)

### Models (모델)
게임 로직에 사용되는 실제 데이터 (44개 파일)

---

## 테이블 목록

### 유닛/전투
- [유닛/종족](유닛_종족.md) - Tribe, TribeUnitStat, SetTribeByStage
- [전투/스테이지](전투_스테이지.md) - StageSpawn, EnemyBaseCamp

### 스킬/성장
- [스킬/특성](스킬_특성.md) - Skill, SkillCost, Mastery
- [소환/유물](소환_유물.md) - Artifact, Summon
- [업그레이드/성장](업그레이드_성장.md) - BaseCampUpgrade, PlanetLevel

### 콘텐츠
- [던전](던전.md) - DrChurDungeon, DemonInvasionDungeon

### 상점/보상
- [아이템/상점](아이템_상점.md) - Item, Shop, Package
- [퀘스트/보상](퀘스트_보상.md) - Quest, BattlePass, Attendance

### 기타
- [기타](기타.md) - CommonData, PushMessage, Enums

---

## 데이터 통계

| 카테고리 | 파일 수 | 총 데이터 행 |
|----------|---------|--------------|
| Enums | 7 | 51 |
| 유닛/종족 | 4 | 751 |
| 전투/스테이지 | 3 | 612 |
| 스킬/특성 | 5 | 1,035 |
| 던전 | 8 | 1,512 |
| 아이템/상점 | 5 | 111 |
| 소환/유물 | 5 | 4,724 |
| 업그레이드 | 4 | 2,300+ |
| 퀘스트/보상 | 7 | 3,587 |
| 기타 | 3 | 26 |

---

## 관련 시스템
- [시스템 기획](../2_시스템기획/README.md)
