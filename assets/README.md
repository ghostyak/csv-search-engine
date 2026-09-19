# 애플리케이션 아이콘

네이비 타일, 민트색 표, 흰색 돋보기로 데이터 검색을 표현한다.

- `app-icon-source.png`: 내장 image_gen으로 생성한 투명 배경 원본.
- `app-icon.png`: 창/작업 표시줄용 256px RGBA PNG.
- `app-icon.ico`: Windows 실행 파일/설치 파일용 16, 20, 24, 32, 40, 48, 64, 128, 256px 아이콘.

원본에서 배포용 파일을 다시 만들려면 Windows에서 다음을 실행한다.
일반 빌드에서는 이미 저장된 아이콘을 사용하므로 이미지 도구를 설치할 필요가 없다.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/generate-icon.ps1
```

`build.rs`는 [winresource](https://github.com/BenjaminRi/winresource)를 통해 실행 파일에
아이콘과 Cargo 패키지 버전 정보를 포함한다. `src/main.rs`는 같은 디자인의 PNG를 창 아이콘으로 사용하고,
Inno Setup은 ICO를 설치 파일 아이콘으로 사용한다.

## 생성 프롬프트

Built-in image_gen 사용. 아래 프롬프트로 생성한 뒤 크기/파일 형식만 변환했다.

> Use case: logo-brand. Create one polished Windows desktop application icon for CSV Search Engine, a professional local CSV and Excel table search tool. Square 1024x1024 PNG with genuinely transparent background outside the icon. Single centered dark midnight navy rounded-square tile occupying 90% of image, with a subtle restrained navy-to-deep-teal gradient, crisp edges. Within tile a beautifully balanced minimalist table grid in soft mint/teal, using only two columns and three rows, partially overlaid at lower right by a bold ivory white magnifying glass with thick clean circular lens and short diagonal handle. Grid and magnifier must read instantly at 32px. Flat vector-like precision, modern premium developer-tool identity, elegant proportions, generous negative space, high contrast. No text, no letters, no numbers, no spreadsheet brand logos, no tiny details, no glossy 3D effects, no busy decoration, no drop shadow outside tile, no presentation sheet, no mockup, only the final isolated app icon.
