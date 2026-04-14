# Stock Movement Prediction: A Comparative Study of Machine Learning Models
โครงการพยากรณ์ทิศทางราคาหุ้นกลุ่ม SET50 ด้วย Machine Learning: การวิเคราะห์เชิงเปรียบเทียบตามกลุ่มอุตสาหกรรม

## 📌 Project Overview
โปรเจกต์นี้มีวัตถุประสงค์เพื่อพยากรณ์ทิศทางราคาหุ้น (Up/Down) ในวันถัดไป โดยใช้ข้อมูลย้อนหลัง 5 ปี จากหุ้นตัวแทนใน 3 กลุ่มอุตสาหกรรมหลักของตลาดหุ้นไทย เพื่อศึกษาว่าปัจจัยทางเทคนิค (Technical Indicators) ชนิดใดมีผลต่อการเคลื่อนไหวของราคาหุ้นในแต่ละประเภทธุรกิจที่แตกต่างกัน

## 📊 Stocks Analyzed
PTT.BK (กลุ่มพลังงาน - Energy)

KBANK.BK (กลุ่มธนาคาร - Banking)

CPALL.BK (กลุ่มค้าปลีก - Retail)

## 🛠️ Tech Stack & Methodology
Data Source: Yahoo Finance API (yfinance)

Models: Random Forest Classifier & XGBoost Classifier

Features: SMA (20), RSI (14), MACD, Volatility (Standard Deviation), Relative Volume

Evaluation: Time-Series Split (เพื่อป้องกัน Data Leakage) และ Accuracy Score

| Stock | Winning Model | Accuracy | Primary Features (Top 3) |
| :--- | :--- | :--- | :--- |
| **PTT** | Random Forest / XGBoost | **62%** | MACD, Volatility, Rel. Volume |
| **KBANK** | Random Forest | **56%** | Volatility, MACD, RSI |
| **CPALL** | XGBoost | **54%** | RSI, SMA, Rel. Volume |

## 💡 Analyst Insight (สรุปบทวิเคราะห์)
จากผลการทดลอง พบข้อมูลที่น่าสนใจดังนี้:

Sector Behavior: หุ้นกลุ่มพลังงาน (PTT) ให้ผลลัพธ์แม่นยำที่สุดเนื่องจากมีแนวโน้ม (Trend) ที่ชัดเจน ขณะที่กลุ่มธนาคาร (KBANK) มีความอ่อนไหวต่อความเสี่ยงสูง (High Volatility Sensitivity)

Model Selection: XGBoost มีประสิทธิภาพโดดเด่นในหุ้นที่มีความซับซ้อนและ Noise สูงอย่าง CPALL โดยสามารถดึง Accuracy กลับมาได้ด้วยการให้ความสำคัญกับ RSI และ SMA

Limitations: ปัจจัยทางเทคนิคเพียงอย่างเดียวอาจไม่เพียงพอสำหรับหุ้นบางกลุ่มที่เคลื่อนไหวตามข่าวเศรษฐกิจมหภาค (Macro Events) ซึ่งเป็นโอกาสในการพัฒนาโมเดลโดยใช้ข้อมูลเชิงคุณภาพ (Sentiment Analysis) ในอนาคต
