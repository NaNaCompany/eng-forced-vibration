# 강제진동 정상 진폭 계산기

질량·스프링·점성 감쇠로 이루어진 1자유도계에 조화력이 작용할 때 정상 변위 진폭을 계산합니다.

- ID: E130
- App: https://nanalab.kr/eng-forced-vibration/
- Repository: https://github.com/NaNaCompany/eng-forced-vibration
- Formula: X = F₀ / √[(k − mω²)² + (cω)²]

## Model and data

선형 스프링과 점성 감쇠, 질량에 직접 작용하는 F₀ cos(ωt)를 가정합니다. 초기조건에 따른 과도응답은 제외합니다. c=0이면 표시값은 조화 특수해의 진폭이며 자유진동은 실제로 소멸하지 않습니다. c=0, ω=√(k/m), F₀>0이면 유한한 정상 진폭이 없으므로 오류를 표시합니다. ω=0은 정적 변위 F₀/k입니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
