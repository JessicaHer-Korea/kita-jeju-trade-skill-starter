# 무역 AI Agent Skill Starter

**한국무역협회 제주지부 · 2026 제주 수출기업 AI 에이전트 구축 실증사업**
제주 수출기업이 매주 반복하는 무역 실무 5개 영역을 Claude Skill 5종으로 담았다. Kick-off(2026-09-22) M3 실습 "기존 Skill 설치·수정·활용"과 이후 1:1 컨설팅의 출발점이다.

## 구성
```
skills/                 Skill Starter 5종 (각 폴더 = Skill 1개, SKILL.md + references/)
  buyer-discovery/      바이어 발굴: 목표시장 우선순위 · 후보 리서치 · 적합도 스코어링 · 초도 오퍼 · 접촉 이력
  trade-documents/      무역서류: 상업송장 · 포장명세서 · PI · 수출단가 산정 로직 · 서류 발송 메일 · 서류 간 교차검증
  market-pricing/       시장·가격: 도매시세 동향 · 환율 반영 견적 · 가격 포지셔닝 · 소비자가 역산 · 출장 조사
  customs-compliance/   통관·규제: HS코드 후보 · 수입국 규제 요건 · 원산지 증빙 점검
  marketing-inquiry/    마케팅·응대: 제품 소개자료 · 영문 상세페이지 · 바이어 문의 응대 · FAQ
agents/
  trade-agent.md        Claude Code 서브에이전트 파일 (5종 Skill 라우팅, 공통 규칙)
  project-instructions.md  claude.ai 프로젝트 "지침" 복사용
companies/              참여기업 6개사 에이전트 설계 카드 + 희망 기능 → Skill 매핑표
tests/                  시험 3회 규칙(양호본·불량본·애매본) 샘플과 기록표
dist/                   claude.ai 업로드용 Skill ZIP 5개
```

## 설치

### claude.ai (유료 플랜)
1. `dist/`의 ZIP 5개를 내려받는다(또는 `skills/<이름>` 폴더를 각각 ZIP으로 압축).
2. claude.ai › 설정 › 기능(Capabilities) › Skills › 업로드 → ZIP 선택. 5개를 각각 올린다.
3. 프로젝트를 하나 만들고 `agents/project-instructions.md` 내용을 "지침"에 붙여넣은 뒤 `[ ]`를 회사 정보로 채운다.
4. 회사 양식·단가표·과거 메일(비식별)을 프로젝트 "지식"에 올린다.
5. 대화에서 "buyer-discovery Skill로 태국 바이어 후보 정리해줘"처럼 Skill 이름을 부르거나, 그냥 업무를 말하면 Claude가 description을 보고 골라 쓴다.

### Claude Code
```bash
# 프로젝트 폴더에서
mkdir -p .claude/skills .claude/agents
cp -R skills/* .claude/skills/
cp agents/trade-agent.md .claude/agents/
```
- `claude` 실행 후 "jeju-trade-agent로 인보이스 초안 만들어줘" 또는 업무 요청.
- 회사 자료는 프로젝트 폴더에 두고 `company-profile.md`를 첫 대화에서 만들어 둔다.

### ChatGPT · Gemini 사용 기업
SKILL.md 본문(절차·금지사항·출력 형식)을 GPTs "Instructions" 또는 Gem "지침"에 그대로 붙여넣으면 같은 방식으로 동작한다. references/ 파일은 "지식(Knowledge)"에 올린다. 단, 파일 자동 참조·Skill 자동 선택은 Claude에서만 된다.

## Skill 파일 구조 (M3·M4 실습에서 고치는 곳)
```
skills/buyer-discovery/
  SKILL.md              ← 두 부분: frontmatter(name, description = 언제 쓰는가) + 본문(절차·금지·출력 = 어떻게 일하는가)
  references/           ← 필요할 때만 읽는 기준표·템플릿·출처 목록
```
- **우리 회사용으로 바꾸는 순서**: ① description에 우리 품목·국가 넣기 → ② "시작 전 확인"에 우리 표준 조건 적기 → ③ 절차의 표 컬럼을 우리 양식 순서로 → ④ 금지사항에 우리 회사 금지 표현 추가 → ⑤ 시험 3회.
- SKILL.md 규칙: `name`은 폴더명과 같은 소문자·하이픈, `description`은 1,024자 이내, 본문은 500줄 이내.

## 시험 3회 규칙
Skill을 올리거나 고칠 때마다 `tests/`의 양호본·불량본·애매본을 돌리고 `tests/시험기록표.md`에 기록한다. 통과 기준은 "형식대로 나오는가 / 창작하지 않는가 / 애매하면 보류하는가".

## 보안 원칙
- 비식별 샘플로 시작한다. 개인정보·영업비밀·원가 단가표·계약서 원문은 외부 AI에 넣지 않는다.
- 계정의 "학습에 데이터 사용" 설정을 끈다. 어디까지 입력할지는 기업이 결정한다.
- Skill이 만든 바이어명·연락처·세율·HS코드는 후보다. 발송·신고 전 담당자·관세사가 확인한다.

## 기업별 적용
`companies/00_수요매핑표.md`에 6개사 신청서 선택 항목과 Skill 매핑, 권장 우선 과제 3개가 있다. 각 기업 카드(01~06)는 1:1 컨설팅 1회차의 출발점이며, 면담 후 확정 과제로 갱신한다.

## 강사 소개
[INSTRUCTOR.md](INSTRUCTOR.md) — 허윤영 원장 (한국디지털제주교육원) 프로필과 연락처.

## 참고 (공식 문서)
- Anthropic Agent Skills 문서: SKILL.md 구조와 작성 규칙
- Anthropic 공식 Skills 저장소(GitHub): 같은 구조의 공개 Skill 모음
- Claude Code Sub-agents 문서: agents/trade-agent.md 형식

---
작성: 허윤영 원장 (한국디지털제주교육원) · 2026-09-20 · 문의 ai_jessica@naver.com · [강사 소개](INSTRUCTOR.md)
