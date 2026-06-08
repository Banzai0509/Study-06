# 🛒 쇼핑 리스트 앱

Supabase를 백엔드로 사용하는 바닐라 JavaScript 쇼핑 리스트 웹 앱입니다.

## 기능

- 아이템 추가 / 삭제
- 체크박스로 완료 처리
- 전체 / 미완료 / 완료 필터링
- 완료 항목 일괄 삭제
- 새로고침 후에도 데이터 유지 (Supabase 연동)

## 기술 스택

- **Frontend**: HTML, CSS, Vanilla JavaScript (ES Modules)
- **Backend**: [Supabase](https://supabase.com) (PostgreSQL + REST API)

## 실행 방법

별도 빌드 없이 `index.html`을 브라우저에서 열면 됩니다.

```bash
# Live Server (VS Code 확장) 또는 아래 명령어로 실행
npx serve .
```

> `file://` 프로토콜로 직접 열면 ES Module import가 차단될 수 있으니 로컬 서버를 사용하세요.

## Supabase 설정

1. [Supabase](https://supabase.com)에서 프로젝트 생성
2. 아래 SQL로 테이블 생성:

```sql
create table shopping_items (
  id bigint primary key,
  text text not null,
  done boolean not null default false,
  created_at timestamptz default now()
);
```

3. `index.html` 내 다음 값을 본인 프로젝트 정보로 교체:

```js
const SUPABASE_URL = 'your-project-url';
const SUPABASE_ANON_KEY = 'your-anon-key';
```
