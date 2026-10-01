# 샘플 영상 출처

이 표는 `scripts/build_imagery_samples.py`가 `manifest.toml`과 만들어진 파일에서 다시 쓴다. 손으로
고치지 않는다. 라이선스별 조건은 [LICENSE.md](LICENSE.md)에 있다.

- 모든 원본은 로그인 없이 받는 공개 버킷에 있다. SPOT 5만 CNES 계정으로 받은 제품에서 만들었다.
- 가공: 원본에서 표의 범위만 잘라 Web Mercator 타일로 다시 만들었다. `늘림`은 그 범위의 밝기를
  적은 백분위 구간으로 8비트에 맞춘 것이고, 밴드마다 따로 맞춘다.
- SAR는 레이더 반사 세기라 사진과 다르게 보인다.

| 파일 | 지역 | 센서·해상도 | 범위·줌·크기 | 촬영 (UTC) | 가공 | 라이선스 | 출처 표기 | 만든 날 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `maxar-wajima` | 와지마 (일본) · Maxar | 광학 0.5 m | 4.1 × 4.1 km · 줌 12–19 · 83 MB | 2024-01-02 01:57 | 자르기만 | CC BY-NC 4.0 | Maxar Open Data Program | 2026-10-01 |
| `maxar-lahaina` | 라하이나 (하와이) · Maxar | 광학 0.5 m | 3.6 × 2.6 km · 줌 13–19 · 37 MB | 2023-08-12 21:12 | 자르기만 | CC BY-NC 4.0 | Maxar Open Data Program | 2026-10-01 |
| `spacenet-paris-eiffel` | 파리 에펠탑 · WorldView-3 | 광학 0.3 m | 1.6 × 2.4 km · 줌 13–19 · 31 MB | 2016-02-29 11:19 | 늘림 1–99% | CC BY-SA 4.0 | SpaceNet on AWS (Maxar WorldView-3) | 2026-10-01 |
| `spacenet-las-vegas` | 라스베이거스 · WorldView-3 | 광학 0.3 m | 2.0 × 2.4 km · 줌 13–19 · 22 MB | 2015-10-22 18:36 | 늘림 1–99% | CC BY-SA 4.0 | SpaceNet on AWS (Maxar WorldView-3) | 2026-10-01 |
| `satellogic-busan-new-port` | 부산신항 · Satellogic | 광학 1 m | 5.8 × 8.1 km · 줌 11–17 · 11 MB | 2022-10-28 01:52 | 늘림 1–99.5%, 조각 이어 붙임 | CC BY 4.0 | Satellogic EarthView | 2026-10-01 |
| `spot5-incheon` | 인천 · SPOT 5 | 광학 5 m | 73.2 × 72.6 km · 줌 8–15 · 66 MB | 2006-05-07 02:22 | 장면 전체, 위치 모델로 폄 | Open Licence 2.0 (Etalab) | SPOT images acquired by CNES's Spot World Heritage Programme | 2026-10-01 |
| `umbra-incheon-airport` | 인천공항 · Umbra | SAR 0.9 m | 5.3 × 5.3 km · 줌 12–18 · 25 MB | 2023-06-17 01:31 | 늘림 1–99% | CC BY 4.0 | Umbra Open Data Program | 2026-10-01 |
| `umbra-seoul` | 서울 도심 · Umbra | SAR 0.2 m | 4.3 × 4.3 km · 줌 12–19 · 78 MB | 2024-04-13 12:43 | 늘림 1–99% | CC BY 4.0 | Umbra Open Data Program | 2026-10-01 |
| `umbra-busan-port` | 부산항 · Umbra | SAR 0.35 m | 3.9 × 3.9 km · 줌 13–19 · 72 MB | 2025-10-23 13:34 | 늘림 1–99% | CC BY 4.0 | Umbra Open Data Program | 2026-10-01 |
| `umbra-sydney-harbour` | 시드니 항 · Umbra | SAR 0.5 m | 3.9 × 3.9 km · 줌 13–19 · 60 MB | 2025-05-08 12:51 | 늘림 1–99% | CC BY 4.0 | Umbra Open Data Program | 2026-10-01 |
| `capella-seongnam` | 성남 · Capella | SAR 0.6 m | 3.1 × 3.1 km · 줌 13–19 · 87 MB | 2024-01-04 01:54 | 늘림 1–99% | CC BY 4.0 | Capella Space Open Data | 2026-10-01 |
| `capella-giza` | 기자 피라미드 · Capella | SAR 0.5 m | 3.0 × 3.1 km · 줌 13–19 · 73 MB | 2024-10-04 00:19 | 늘림 1–99%, 픽셀 0.3 m로 줄임 | CC BY 4.0 | Capella Space Open Data | 2026-10-01 |

## 원본

- `maxar-wajima`: <https://maxar-opendata.s3.amazonaws.com/events/Japan-Earthquake-Jan-2024/ard/53/120022100023/2024-01-02/10300100F316CD00-visual.tif>
- `maxar-lahaina`: <https://maxar-opendata.s3.amazonaws.com/events/Maui-Hawaii-fires-Aug-23/ard/04/122000330002/2023-08-12/10300100EB15FF00-visual.tif>
- `spacenet-paris-eiffel`: <https://spacenet-dataset.s3.us-east-1.amazonaws.com/AOIs/AOI_3_Paris/PS-RGB/16FEB29111912-S2AS_R10C09-056155973010_01_P001.TIF>
- `spacenet-las-vegas`: <https://spacenet-dataset.s3.us-east-1.amazonaws.com/AOIs/AOI_2_Vegas/PS-RGB/15OCT22183656-S2AS_R6C7-056155973040_01_P001.TIF>
- `satellogic-busan-new-port`: chips/satellogic-busan-new-port.txt
- `spot5-incheon`: CNES 계정으로 받은 SPOT 5 제품
- `umbra-incheon-airport`: <https://umbra-open-data-catalog.s3.us-west-2.amazonaws.com/sar-data/tasks/ad%20hoc/Incheon%20International%20Airport%2C%20South%20Korea/53dd67b6-a1ce-4ffc-9ff6-f57bbd8cac8d/2023-06-17-01-31-23_UMBRA-06/2023-06-17-01-31-23_UMBRA-06_GEC.tif>
- `umbra-seoul`: <https://umbra-open-data-catalog.s3.us-west-2.amazonaws.com/sar-data/tasks/ad%20hoc/SpaceSymposium2024/fd407bc4-44fb-409f-91af-73e07535164d/2024-04-13-12-43-27_UMBRA-05/2024-04-13-12-43-27_UMBRA-05_GEC.tif>
- `umbra-busan-port`: <https://umbra-open-data-catalog.s3.us-west-2.amazonaws.com/sar-data/tasks/Port%20of%20Busan%2C%20South%20Korea/cac7324e-0bc1-4881-a6e9-0cc89f08c23c/2025-10-23-13-34-27_UMBRA-08/2025-10-23-13-34-27_UMBRA-08_GEC.tif>
- `umbra-sydney-harbour`: <https://umbra-open-data-catalog.s3.us-west-2.amazonaws.com/sar-data/tasks/ad%20hoc/Sydney-Harbor_Australia/d0c6a8ef-5ec2-4438-bc9d-efaa432428d5/2025-05-08-12-51-40_UMBRA-09/2025-05-08-12-51-40_UMBRA-09_GEC.tif>
- `capella-seongnam`: <https://capella-open-data.s3.us-west-2.amazonaws.com/data/2024/1/4/CAPELLA_C06_SP_GEO_HH_20240104015400_20240104015423/CAPELLA_C06_SP_GEO_HH_20240104015400_20240104015423_preview.tif>
- `capella-giza`: <https://capella-open-data.s3.us-west-2.amazonaws.com/data/2024/10/4/CAPELLA_C13_SP_GEO_HH_20241004001939_20241004002012/CAPELLA_C13_SP_GEO_HH_20241004001939_20241004002012_preview.tif>
