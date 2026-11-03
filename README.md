# ujam-marketplace

UJAM 공유 Claude Code 플러그인 마켓플레이스입니다.

## 설치 방법

### 1. 마켓플레이스 추가

Claude Code에서 다음 명령을 실행합니다.

```
/plugin marketplace add jaemin-Yoo/ujam-marketplace
```

### 2. 플러그인 설치

```
/plugin install commit@ujam-marketplace
```

또는 `/plugin` 명령으로 메뉴를 열어 `ujam-marketplace`에서 원하는 플러그인을 골라 설치할 수 있습니다.

### 업데이트

마켓플레이스에 새 버전이 올라오면 다음 명령으로 목록을 갱신합니다.

```
/plugin marketplace update ujam-marketplace
```

### 제거

```
/plugin uninstall commit@ujam-marketplace
/plugin marketplace remove ujam-marketplace
```

## 팀 프로젝트에 자동 등록하기 (선택)

프로젝트의 `.claude/settings.json`에 다음 내용을 추가하면, 팀원이 해당 프로젝트 폴더를 신뢰(trust)할 때 마켓플레이스 추가와 플러그인 설치를 안내받습니다.

```json
{
  "extraKnownMarketplaces": {
    "ujam-marketplace": {
      "source": {
        "source": "github",
        "repo": "jaemin-Yoo/ujam-marketplace"
      }
    }
  },
  "enabledPlugins": {
    "commit@ujam-marketplace": true
  }
}
```

## 플러그인 목록

| 플러그인 | 설명 | 사용법 |
|----------|------|--------|
| `commit` | 현재 Claude 대화에서 수행한 작업을 Conventional Commit 형식으로 커밋합니다. 변경 사항이 여러 관심사에 걸쳐 있으면 논리적 단위로 분리하여 커밋합니다. | `/commit:commit` |

### commit

- `main` 브랜치에서 커밋할 때:
  - 로컬 브랜치가 `main` 하나뿐이면 확인 없이 바로 커밋합니다.
  - 다른 로컬 브랜치가 있으면 커밋 전에 사용자에게 확인을 받습니다.
- `master` 브랜치에서는 항상 커밋 전에 사용자에게 확인을 받습니다.
- 파일을 하나씩 지정해서 스테이징하며, `git add -A`는 쓰지 않습니다.
