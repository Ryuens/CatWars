# 데이터 테이블

CatWars 게임 데이터 테이블 구조와 스펙을 설명합니다.

> 원본 파일 위치: `참고자료/원본자료/EXCEL_DATA/`

---

## 데이터 구조

### Enums (열거형)
게임에서 사용하는 상수값 정의

### Models (모델)
게임 로직에 사용되는 실제 데이터

---

## Enums 목록

| 파일 | 항목 수 | 설명 |
|------|---------|------|
| ItemType.xlsx | 10 | 아이템 타입 (골드, 마석, 파랑수정, 특성석, 유물, 스킬 등) |
| BonusType.xlsx | 12 | 보너스 유형 |
| ConditionType.xlsx | 16 | 조건 유형 |
| ProductType.xlsx | 5 | 상품 유형 (한정, 소비성, 광고보상, 구독) |
| ProductCategory.xlsx | 2 | 상품 카테고리 (패키지, 보석) |
| ContentsOpenType.xlsx | 2 | 콘텐츠 해금 조건 (전투 횟수, 스테이지 도달) |
| ContentsOpenPopupType.xlsx | 4 | 해금 팝업 유형 |

---

## Models 목록

### 유닛/종족

| 파일 | 행 수 | 주요 컬럼 |
|------|-------|-----------|
| Tribe.xlsx | 37 | TribeIndex, SetInStage, TribeUnit1~3_Index |
| TribeUnitStat.xlsx | 113 | TribeUnitIndex, 능력치 |
| TribeUnitStatData.xlsx | 1 | 유닛 스탯 기본 데이터 |
| SetTribeByStage.xlsx | 600 | 스테이지별 종족 인덱스 |

### 전투/스테이지

| 파일 | 행 수 | 설명 |
|------|-------|------|
| StageSpawn.xlsx | 6 | 스테이지 웨이브 정보 (Age, Wave) |
| EnemyBaseCampHp.xlsx | 600 | 스테이지별 적 기지 HP |
| EnemyBaseCampGetGold.xlsx | 6 | 적 기지 타격 시 획득 골드 |

### 스킬/특성

| 파일 | 행 수 | 주요 컬럼 |
|------|-------|-----------|
| Skill.xlsx | 160 | Idx, Lv, Value, U1~3_Value |
| SkillCost.xlsx | 20 | 레벨별 필요 재료 |
| Mastery.xlsx | 95 | 특성 정보 |
| MasteryData.xlsx | 4 | 특성 타입 |
| MasteryLevel.xlsx | 760 | 특성 레벨 데이터 |

### 던전

| 파일 | 행 수 | 설명 |
|------|-------|------|
| Dungeon.xlsx | 3 | 던전 기본 정보 |
| DungeonData.xlsx | 3 | 던전 상세 데이터 |
| DrChurDungeon.xlsx | 500 | 슬라임 러쉬 던전 |
| DrChurDungeonUserUnitBase.xlsx | 3 | 슬라임 던전 아군 베이스 |
| DrChurDungeonEnemyUnitBase.xlsx | 3 | 슬라임 던전 적군 베이스 |
| DemonInvasionDungeon.xlsx | 1000 | 마계침공 던전 |
| DemonInvasionDungeonUserUnitBase.xlsx | 3 | 마계침공 아군 베이스 |
| DemonInvasionDungeonEnemyUnitBase.xlsx | 3 | 마계침공 적군 베이스 |

### 아이템/상점

| 파일 | 행 수 | 설명 |
|------|-------|------|
| Item.xlsx | 58 | 아이템 인덱스, 타입 |
| Shop.xlsx | 18 | 상점 상품 (17개 컬럼) |
| ShopItemPackage.xlsx | 25 | 아이템 패키지 |
| ShopPerkItems.xlsx | 2 | 특수 판매 아이템 |
| ItemLowPackage.xlsx | 8 | 저가 패키지 |

### 소환/유물

| 파일 | 행 수 | 설명 |
|------|-------|------|
| ArtifactLevel.xlsx | 3600 | 유물 레벨별 데이터 |
| ArtifactSummonLevel.xlsx | 20 | 유물 소환 레벨 |
| SummonData.xlsx | 4 | 소환 기본 데이터 |
| SummonGemProduce.xlsx | 1000 | 소환석 생산량/가격 |
| UnitSummonGemCost.xlsx | 100 | 유닛 소환 비용 |

### 업그레이드/성장

| 파일 | 행 수 | 설명 |
|------|-------|------|
| BaseCampUpgradeHp.xlsx | 1000 | 기지 레벨별 HP |
| BaseCampUpgradePrice.xlsx | 1000 | 기지 레벨별 가격 |
| PlanetLevel.xlsx | 300 | 행성 레벨별 난이도 |
| UnitOpenCost.xlsx | - | 유닛 해금 비용 |

### 퀘스트/보상

| 파일 | 행 수 | 설명 |
|------|-------|------|
| GuideQuest.xlsx | 3371 | 가이드 퀘스트 |
| DailyQuest.xlsx | 11 | 일일 퀘스트 |
| DailyAttendance.xlsx | 7 | 출석 보상 |
| DailyRoulette.xlsx | 8 | 룰렛 보상 |
| BattlePass.xlsx | 120 | 배틀패스 (Free/VIP 보상) |
| ClearReward.xlsx | 42 | 클리어 보상 |
| ContentsOpen.xlsx | 28 | 콘텐츠 해금 조건 |

### 기타

| 파일 | 행 수 | 설명 |
|------|-------|------|
| CommonData.xlsx | 8 | 공통 설정 데이터 |
| PushMessage.xlsx | 4 | 푸시 메시지 |
| PushMessageText.xlsx | 14 | 푸시 메시지 텍스트 |

---

## 주요 데이터 관계

### 전투 계산

```
최종 능력치 = 베이스 능력치 + 스킬 보너스 + 유물 보너스 + 특성 보너스
```

### 던전 난이도 계산

```
적군 공격력 = 베이스 공격력 × 챕터 난이도 (PlanetLevel)
적군 체력 = 베이스 체력 × 챕터 난이도
```

### 골드 획득 계산

```
HP당 획득 골드 = EnemyBaseCampGetGold / EnemyBaseCampHp
```

---

## 데이터 수정 가이드

1. 원본 Excel 파일 수정
2. 변경 내용 이 문서에 기록
3. 테스트 후 적용

### 주의사항
- 인덱스 변경 시 관련 참조 데이터 확인
- 밸런스 수정 시 PlanetLevel 난이도 고려
- 새 콘텐츠 추가 시 Enums 먼저 정의
