# Term Deposit Subscription Prediction

**Machine Learning Project | Python · Decision Tree · Random Forest · Scikit-learn**

## Project Overview

โปรเจกต์นี้เป็นการพัฒนา Machine Learning Classification Model เพื่อทำนายว่าลูกค้าธนาคารมีแนวโน้มสมัครบริการเงินฝากประจำ (Term Deposit) หรือไม่ โดยใช้ข้อมูลจาก Bank Marketing Dataset

กระบวนการวิเคราะห์ครอบคลุมการเตรียมข้อมูล การสำรวจข้อมูล การแปลงตัวแปรหมวดหมู่ การแบ่ง Training/Test Set การสร้างโมเดล และการเปรียบเทียบประสิทธิภาพระหว่าง Decision Tree และ Random Forest

## Objective

- สร้างโมเดล Classification สำหรับทำนายการสมัคร Term Deposit
- เปรียบเทียบประสิทธิภาพของ Decision Tree และ Random Forest
- ประเมินโมเดลภายใต้ปัญหา Class Imbalance
- วิเคราะห์ Feature Importance เพื่อระบุปัจจัยสำคัญที่มีผลต่อการทำนาย

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook / Google Colab
- Machine Learning
- Data Analysis

## Data Preparation

ขั้นตอนการเตรียมข้อมูลประกอบด้วย

- Data Cleaning
- Data Preprocessing
- Categorical Encoding
- Exploratory Data Analysis (EDA)
- Feature Preparation
- Train/Test Split
- Feature Scaling

ข้อมูลถูกแบ่งเป็น Training และ Testing Set โดยใช้ `test_size = 0.30`
และใช้ Stratified Sampling เพื่อรักษาสัดส่วนของ Target Class

## Models

### Decision Tree

ใช้ Decision Tree Classifier โดยกำหนด

- Criterion: Gini
- Max Depth: 8
- Class Weight: Balanced
- Random State: 0

### Random Forest

สร้าง Random Forest Classifier เพื่อเปรียบเทียบประสิทธิภาพกับ Decision Tree

## Model Evaluation

ใช้ Metric หลักในการประเมินโมเดล ได้แก่

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

### Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Decision Tree | 78.48% | 31.62% | 75.00% | 44.49% |
| Random Forest | 88.80% | 53.70% | 18.59% | 27.62% |

แม้ Random Forest จะมี Accuracy โดยรวมสูงกว่า แต่มี Recall สำหรับกลุ่มลูกค้าที่สมัครต่ำมาก

Decision Tree สามารถระบุกลุ่มลูกค้าที่สมัครได้ดีกว่า โดยมี Recall 75% จึงถูกเลือกเป็น Final Model สำหรับโปรเจกต์นี้

## Final Model

**Decision Tree Classifier**

Final Model Performance:

- Accuracy: 78.48%
- Precision: 31.62%
- Recall: 75.00%
- F1-Score: 44.49%

Confusion Matrix:

```text
[[948 253]
 [ 39 117]]
```

โมเดลสามารถระบุลูกค้าที่สมัครจริงได้ 117 ราย จากกลุ่มผู้สมัครจริง 156 ราย

## Feature Importance

จากการวิเคราะห์ Feature Importance พบว่า `duration` เป็นตัวแปรที่มีความสำคัญสูงที่สุด โดยมี Importance ประมาณ **0.53**

ตัวแปรสำคัญลำดับต้น ๆ ได้แก่

- `duration`
- `poutcome_success`
- `contact_unknown`
- `age`
- `balance`
- `day`
- `pdays`

## Key Insight

`duration` หรือระยะเวลาในการสนทนากับลูกค้าเป็นตัวแปรที่มีอิทธิพลต่อโมเดลสูงที่สุด

อย่างไรก็ตาม ตัวแปรนี้มีข้อจำกัดในเชิงการใช้งานจริง เพราะระยะเวลาการสนทนาจะทราบหลังจากการติดต่อเกิดขึ้นแล้ว จึงอาจไม่เหมาะสำหรับใช้ทำนายลูกค้าก่อนเริ่มการติดต่อ

## My Responsibilities

- ทำความสะอาดและเตรียมข้อมูลสำหรับ Machine Learning
- แปลงตัวแปรหมวดหมู่ให้อยู่ในรูปแบบที่โมเดลสามารถใช้งานได้
- ทำ Exploratory Data Analysis
- แบ่งข้อมูลเป็น Training และ Testing Set
- พัฒนา Decision Tree และ Random Forest Models
- ประเมินโมเดลด้วย Accuracy, Precision, Recall และ F1-Score
- วิเคราะห์ผลภายใต้ Class Imbalance
- เปรียบเทียบโมเดลและเลือก Final Model
- วิเคราะห์ Feature Importance และตีความผลลัพธ์

## Project Files

```text
term-deposit-subscription-prediction/
│
├── README.md
└── term-deposit-subscription-prediction.ipynb
```

## Project Type

**Academic Project — Machine Learning Classification**

โปรเจกต์นี้พัฒนาขึ้นเพื่อประยุกต์ใช้ Machine Learning ในการแก้ปัญหา Classification พร้อมฝึกการประเมินโมเดลภายใต้ Class Imbalance และการตีความ Feature Importance

> **Note:** โปรเจกต์นี้จัดทำขึ้นเพื่อการศึกษาและการนำเสนอผลงานใน Portfolio
