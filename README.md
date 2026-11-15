# 리튬금속 음극 보호용 불화물계 소재 스크리닝

인공지능재료설계 수업 발표 프로젝트입니다. Materials Project 데이터베이스에서 리튬(Li)과 불소(F)를 포함하는 물질을 단계별 필터로 걸러, 리튬금속 음극 보호층 후보를 찾습니다.

## 스크리닝 단계

| 단계 | 기준 | 남은 후보 |
| --- | --- | --- |
| 출발 | Li·F 포함 물질 (Materials Project) | 2,582 |
| ① 안정성 | Ehull ≤ 0.05 eV/atom | 851 |
| ② 원소 제외 | 독성·고가 원소 제외 | 691 |
| ③ 전자 절연 | 밴드갭 ≥ 4.0 eV | 95 |
| ④ Li 반응성 | Li 반응 에너지 ≥ -0.1 eV/atom | 3 |

## 결과

| Materials Project 번호 | 화학식 | Ehull (eV/atom) | 밴드갭 (eV) | Li 반응 에너지 (eV/atom) |
| --- | --- | --- | --- | --- |
| mp-1138 | LiF | 0.000 | 8.72 | 0.000 |
| mp-1185301 | LiF | 0.024 | 8.76 | 0.000 |
| mp-10250 | BaLiF3 | 0.022 | 6.57 | -0.049 |

- 알려진 LiF가 필터를 통과해 방법의 타당성을 확인했습니다.
- BaLiF3가 새 후보로 남았으며, Li+ 전도도와 기계적 물성은 평가하지 않았습니다.

## 사용한 도구

- Materials Project API (mp-api)
- pymatgen (PhaseDiagram, InterfacialReactivity)
- pandas, matplotlib

## 실행 방법

1. [Materials Project](https://next-gen.materialsproject.org/)에서 무료 API 키를 발급받습니다.
2. `lithium_fluoride_screening.ipynb`를 Google Colab에서 엽니다.
3. `런타임 > 모두 실행`을 누르고, 안내가 나오면 API 키를 입력합니다. 키는 저장되지 않습니다.

## 한계

- 결정질·0 K 계산 기준이며, 기준값(Ehull, 밴드갭, 반응 에너지)은 직접 정한 값입니다.
- Li+ 이동 장벽과 기계적 물성은 다루지 않았습니다.

## 참고

코드 작성과 문서 초안에 AI 도구의 도움을 받았고, 실행과 결과 해석은 직접 수행했습니다.
