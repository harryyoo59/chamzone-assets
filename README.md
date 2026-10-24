# Chamzone Interactive

회사 홈페이지 · 배포 주소 목표: **https://chamzoneinteractive.vercel.app**

이 저장소는 Chamzone Interactive(참존 인터랙티브) 회사 사이트와 앱 아이콘·로고 자산을 함께 둡니다.

| 경로 | 용도 |
|---|---|
| `index.html` | 회사 홈(랜딩) |
| `warehouse.html` | 아이콘·로고 작업용 창고(예전 미리보기) |
| `preview.html` | 창고 미리보기(하위 호환) |
| `company/` | 회사 공통 아이콘·로고 |
| `apps/` | 앱별 아이콘 |
| `emoji/` | 이모지 |
| `originals/` | 큰 원본 |
| `vercel.json` | Vercel 정적 배포 설정 |

## 로컬 미리보기

```bash
npx --yes serve -l 4173 .
# 또는: python3 -m http.server 4173
```

브라우저에서 `http://localhost:4173` → 회사 홈, `/warehouse` → 아이콘 창고.

## Vercel 배포 · 도메인

정적 사이트입니다. 빌드 명령 없음 · Output Directory는 저장소 루트(`.`)입니다.

### 이미 `chamzone-assets` 프로젝트가 있는 경우

1. [Vercel Dashboard](https://vercel.com/dashboard)에서 이 GitHub 저장소(`harryyoo59/chamzone-assets`)에 연결된 프로젝트를 엽니다.
2. **Settings → Domains**에서 `chamzoneinteractive.vercel.app` 를 추가합니다.
   - Vercel 프로젝트 이름을 `chamzoneinteractive`로 바꾸면 `*.vercel.app` 기본 주소도 같이 바뀝니다.
   - 기존 `chamzone-assets.vercel.app` 는 Domains에 남겨 두면 창고·자산 URL로 계속 쓸 수 있습니다.
3. 프로덕션 브랜치(`main`)에 머지하면 자동 배포됩니다.

### 새 Vercel 프로젝트로 회사 사이트만 분리할 경우

1. Vercel → Add New Project → `harryyoo59/chamzone-assets` 연결.
2. Framework Preset: **Other**, Build Command 비움, Output Directory: `.`
3. 프로젝트 이름을 `chamzoneinteractive`로 두면 기본 URL이 `https://chamzoneinteractive.vercel.app` 이 됩니다.
4. 커스텀 도메인(예: `chamzoneinteractive.com`)을 쓸 때는 Domains에 추가한 뒤 DNS에 Vercel이 안내하는 `A`/`CNAME` 레코드를 넣습니다.

### DNS (커스텀 도메인일 때만)

| 레코드 | 이름 | 값 |
|---|---|---|
| A | `@` | `76.76.21.21` (Vercel 안내 값 확인) |
| CNAME | `www` | `cname.vercel-dns.com` |

`*.vercel.app` 주소만 쓸 때는 DNS 작업이 필요 없습니다.

## 파일 이름 규칙

영어 **소문자**와 `-`(하이픈)만 씁니다.  
예: `favicon-32.png`, `apple-touch-icon.png`
