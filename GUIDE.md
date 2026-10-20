# 소설 서가 관리 안내

사이트 공개 주소는 GitHub Pages 설정 후 https://hasutxt.github.io/hasutxt/ 입니다.

## 처음 한 번: 공개하기

저장소의 **Settings → Pages → Build and deployment → Deploy from a branch → main → /(root) → Save**를 선택합니다. 이후 이 저장소의 main 브랜치를 수정하면 사이트가 자동으로 갱신됩니다.

## 번역 고치기

- `data/album-tree.json`의 `pages`에서 해당 `number`(쪽수)를 찾습니다.
- `originalParagraphs`: 일본어 원문, `paragraphs`: 한국어 번역문입니다. 각 문단은 큰따옴표로 감싼 문자열입니다.
- 현재 2–31쪽의 번역문은 검수용 초안입니다. 내용을 수정한 뒤 GitHub의 **Commit changes**를 누르면 사이트에도 반영됩니다.

## 소설 추가하기

1. `data/album-tree.json` 구조를 참고해 `data/새-작품-id.json` 파일을 만듭니다. 맨 위에 `id`, `title`, `subtitle`, `pageCount`, `pages`가 필요합니다.
2. 각 쪽을 `{"number": 1, "originalParagraphs": ["日本語"], "paragraphs": ["한국어"]}` 형식으로 넣습니다.
3. `data/library.json`의 `stories` 배열에 새 항목을 추가합니다. `data` 값은 `"data/새-작품-id.json"`처럼 지정합니다. 목록에는 배열에 적은 순서대로 표시됩니다.

빌드 도구와 서버 비용은 필요하지 않습니다. 저장소의 파일과 공개 사이트는 누구나 볼 수 있습니다.
