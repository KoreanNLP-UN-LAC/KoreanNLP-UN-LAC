# Prefix-Tuning 기법과 KoGPT-2 모델 기반 한국어 시 생성 모델 제안

## Team UN-LAC(언락)

**Uncovering Korean Language Archive Content**

가천 x 세종 연합 학술제 프로젝트

## About-Us

| Profile                                                                               | Name                                          | Major                         |
| ------------------------------------------------------------------------------------- | --------------------------------------------- | ----------------------------- |
| <img src="https://github.com/sejong-mingi.png" width="80" style="border-radius:50%;"> | [**이민기**](https://github.com/sejong-mingi) | 세종대학교 데이터사이언스학과 |
| <img src="https://github.com/NamKyeongMin.png" width="80" style="border-radius:50%;"> | [**남경민**](https://github.com/NamKyeongMin) | 가천대학교 인공지능학과       |

---

## Table of Contents

- [Abstract](#Abstract)
- [KoGPT-2 Architecture](#KoGPT-2-Architecture)
- [Conclusion](#Conclusion)
- [Skill Stack](#Skill-Stack)
- [Progress](#Progress)

---

## Abstract

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7674a4fa-af38-4401-92e5-b355249ac129" />

본 연구는 스트리밍의 확산으로 가사 접근성이 높아지고 가사가 독자적 텍스트로 조명되는 변화, 그리고 대화형 인공지능의 부상을 배경으로, 노래 가사와 시의 경계를 가로지르는 한국어 시 생성의 가능성을 탐색한다. 한국어 사전학습 언어모델 KoGPT-2를 기반으로 Prefix-Tuning 기법을 적용해 시 데이터와 장르별 가사 데이터를 학습시켜 3개의 모델을 구축하여 장르적 특성이 시 생성에 반영되는지 검증하는 것을 목표로 한다.

Perplexity와 Train/Eval loss를 측정하여 모델의 안정적인 수렴과 학습 성능을 확인하였으며, 생성된 시는 sBERT 기반 문장 임베딩을 활용한 유사도 비교와 정성적 분석을 통해 평가하였다. 각 모델은 동일한 데이터셋에 대하여 서로 다른 유사도 Top1 시를 선택하였으며, 이를 통해 장르적 표현 양식, 정서적 경향이 시 생성 과정에 뚜렷하게 반영됨을 확인하였다. 나아가 문학적 평가에서는 장르별 정서적 어휘와 운율적 특성이 시적 맥락 속에 자연스럽게 드러나, 장르에 따라 구별되는 창작 양상을 보여주었다.

이러한 시도는 시와 가사의 장르적 경계를 허물고, 운율적 언어의 새로운 표현 양식을 탐색하는 동시에, 인공지능 기반 문학 창작의 새로운 방향성을 제시한다.

---

## KoGPT-2-Architecture

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1fec80fd-1673-403e-a596-473704fcfa37" />

본 연구에서는 문학의 한 장르인 시에 노래 가사가 어떻게 접목될 수 있는지를 탐색하기 위해, 한국어 시와 장르별 가사 데이터를 함께 학습시킨 모델의 시 생성 결과를 비교한다.사전 학습 언어모델 KoGPT-2를 기반으로 Prefix-Tuning 기법을 적용하여 발라드·힙합·인디음악 가사 데이터를 각각 학습시킨 세 개의 모델을 구축하였다.

학습한 모델의 출력 결과에 대해 sBERT를 통한 원본 시 데이터와의 유사도 비교를 진행하여 모델의 성능을 평가하였다. 또한 모델별 출력 결과에 대한 문학적 평가를 진행하여 장르별 특성이 시 생성 결과에 반영되는 양상을 분석하였다.

---

## Conclusion

각각의 모델이 학습한 가사 데이터 기반의 입력 프롬프트뿐만 아니라, 동일한 입력 프롬프트에서도 학습한 장르 데이터의 특성이 뚜렷이 반영된 결과를 산출하였다. 힙합 모델은 직설적이고 리듬감 있는 표현을, 발라드 모델은 서정적이고 감정에 몰입된 흐름을, 인디음악 모델은 소박하고 개성적인 감수성을 중점적으로 시 생성 결과를 산출한다. 이는 곧 장르별 데이터 학습이 생성 모델의 시적 산출물에 직접적인 영향을 미친다는 사실을 내포한다. 따라서 본 실험은 장르별 데이터셋 학습이 생성 모델의 문체적 편향을 유도하며, 특정 장르적 감수성을 창작물에 반영하는 중요한 요소임을 시사한다.

본 연구의 의의는 크게 세 가지로 살펴볼 수 있다. 첫째, 한국어를 대상으로 한 시 생성 연구라는 점에서 기존 영어 중심 연구와 차별성을 가진다. 둘째, 시와 가사의 경계를 가로지르는 새로운 시도로서, 장르별 가사 데이터가 시 창작의 양식을 어떻게 변주하는지를 실험적으로 검증하였다. 셋째, sBERT 기반 유사도 비교를 통한 정량적 평가와 정성적 문학 분석을 결합하여, 인공지능 창작물을 다각적으로 해석할 수 있는 분석 틀을 제시하였다.

---

## Skill-Stack

- 언어: Python
- 환경: google colab, Jupyter notebook
- 데이터 수집: Web Scraping(BeautifulSoup)
- 전처리: numpy, pandas, scikit-learn, re
- 모델/토크나이저: HuggingFace Transformers
- DL 프레임워크: PyTorch
- 튜닝: PEFT(Prefix-Tuning)
- 시 생성 모델: KoGPT-2 (SKT)
- 유사도 평가 모델: SentenceBERT (Cosin Similarity 기반 STS)

---

## Progress

- [x] 연구 주제 선정
- [x] 연구 리서치 및 모델 구조 결정
- [x] 데이터 수집 (웹 스크랩핑)
- [x] 데이터 전처리 (KoGPT2 Tokenizer)
- [x] 모델 프롬프트 튜닝 (Prefix-Tuning)
- [x] KoGPT-2 훈련 및 저장
- [x] 시 데이터 생성
- [x] 모델 성능 평가 (sBERT STS/코사인 유사도)
