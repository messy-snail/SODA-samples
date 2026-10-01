# SODA 샘플 영상

[SODA](https://github.com/messy-snail/SODA)의 지구본에 올려 보는 고해상도 위성 영상 샘플이다. SODA 저장소의 `samples` 서브모듈로 쓴다.

- 광학과 SAR(합성개구레이더) 영상을 한 변 몇 km로 잘라 지도 타일(MBTiles)로 만든 것이다.
- 모두 로그인 없이 받을 수 있고 재배포가 허용된 공개 영상에서 만들었다. 항목별 출처와 라이선스는 [SOURCES.md](SOURCES.md), 조건 요약은 [LICENSE.md](LICENSE.md)에 있다.

## 쓰는 법

SODA 저장소 폴더에서 받는다.

```
git submodule update --init samples
```

서버를 다시 시작하면 `보기 → 영상` 탭 목록에 `샘플`로 나온다. 과녁 버튼을 누르면 그 위치로 이동하고, 확대하면 영상이 나타난다. 샘플은 SODA에서 수정하거나 지울 수 없다. 빼려면 SODA의 `settings.local.toml`에 `imagery_samples = false`를 넣는다.

## 구성

| 경로 | 내용 |
| --- | --- |
| `imagery/<슬러그>.mbtiles` | 타일. Web Mercator, JPEG(가장자리는 WebP) |
| `imagery/<슬러그>.json` | SODA 사이드카: 이름, 범위, 줌, 센서 종류, 라이선스, 출처 표기, 촬영 시각 |
| `manifest.toml` | 샘플을 만드는 입력: 원본 주소, 자를 중심과 크기, 라벨 |
| `chips/*.txt` | 여러 조각을 이어 붙이는 샘플의 조각 주소 목록 |

## 다시 만들기

파일을 손으로 고치지 않는다. `manifest.toml`을 고친 뒤 SODA 저장소에서 실행한다.

```
uv run python scripts/build_imagery_samples.py            # 전부
uv run python scripts/build_imagery_samples.py --only umbra-seoul
```

- 원본은 SODA의 `.cache/imagery-samples/`에 받아 두고 다시 쓴다(전부 합쳐 몇 GB).
- 일반 git 저장소라 파일 하나가 100 MiB를 넘으면 GitHub가 받지 않는다. 스크립트는 95 MiB를 넘으면 해상도를 낮추지 않고 자르는 범위를 줄여 다시 만든다.
- SPOT 5 샘플만 예외로 원본을 자동으로 받지 않는다. CNES 계정으로 직접 받은 제품 zip이 SODA의 `.cache/spot-swh/`에 있어야 한다.
- 샘플을 바꾸면 `SOURCES.md` 표를 같은 커밋에서 고친다.
