# 수출서류 표준 필드

## Commercial Invoice (상업송장)
| 순서 | 필드 | 비고 |
|---|---|---|
| 1 | Seller / Shipper (상호·주소·연락처) | 사업자 영문 상호 그대로 |
| 2 | Consignee (수하인) | L/C 거래면 L/C 기재대로 |
| 3 | Notify Party (통지처) | 없으면 "Same as Consignee" |
| 4 | Invoice No. / Date | 회사 채번 규칙 |
| 5 | P/O No. 또는 L/C No. / Date | 계약 근거 |
| 6 | Port of Loading / Port of Discharge | 예: Busan, Korea / Laem Chabang, Thailand |
| 7 | Vessel / Flight, ETD | 포워더 확정 후 기입 |
| 8 | Terms of Delivery | Incoterms 2020 규칙 + 장소 (FOB Busan) |
| 9 | Terms of Payment | T/T in advance, T/T 30/70, L/C at sight, D/P, D/A 등 |
| 10 | Marks & Nos | PL과 동일 |
| 11 | Description of Goods | 영문 품명, HS Code(6~10자리), 규격 |
| 12 | Quantity / Unit | PCS, CTN, KG 등 단위 통일 |
| 13 | Unit Price / Amount / Currency | 통화 3자리 코드(USD, EUR) |
| 14 | Total Amount (숫자 + 영문 금액 표기) | SAY TOTAL US DOLLARS ... ONLY |
| 15 | Country of Origin | Republic of Korea |
| 16 | Signature (Authorized Signatory) | 초안에는 비움 |

## Packing List (포장명세서)
| 순서 | 필드 |
|---|---|
| 1 | Shipper / Consignee / Notify (CI와 동일) |
| 2 | Invoice No. / Date (CI와 동일 번호) |
| 3 | Marks & Nos (화인) |
| 4 | Description of Goods (CI와 동일 품명 순서) |
| 5 | Quantity (수량) / Packing unit (입수) / No. of Packages (박스 수) |
| 6 | Net Weight (kg) / Gross Weight (kg) — 품목별·합계 |
| 7 | Measurement (CBM) — 박스 규격(L×W×H cm) × 박스 수 ÷ 1,000,000 |
| 8 | Total: Packages / N.W. / G.W. / CBM |

## Proforma Invoice (견적송장)
CI 필드에서 Vessel·B/L 항목을 빼고 **Validity(유효기간)**, **Delivery(리드타임)**, **Bank details(담당자 기입)**, **Remarks(샘플·포장 조건)** 를 추가한다. 제목은 "PROFORMA INVOICE".

## 단위·표기 통일
- 중량 kg → "KGS", 수량 → "PCS/CTN/SET", 통화 → ISO 3자리
- 날짜 → "DD MMM YYYY" (예: 05 OCT 2026) 또는 회사 관행
- 품명은 모든 서류에서 **글자 단위로 동일**하게
