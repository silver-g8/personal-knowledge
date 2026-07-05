# AI Investment Report Review Checklist

---
title: AI Investment Report Review Checklist
created: 2026-07-05
updated: 2026-07-05
status: draft
tags:
  - learning
  - ai
  - investing
  - checklist
aliases:
  - AI Investment Report Checklist
---

## Overview

AI investment report review checklist ใช้ตรวจรายงานวิเคราะห์งบที่ AI สร้างก่อนนำไปใช้เรียนรู้หรือตัดสินใจลงทุน source ย้ำว่า AI เป็นผู้ช่วย ไม่ใช่ผู้ตัดสินใจแทนนักลงทุน

## Learning Objective

หลังอ่าน note นี้ ควรมี checklist สั้น ๆ สำหรับตรวจว่า report จาก AI มีข้อมูลครบ น่าเชื่อถือ และไม่ overclaim เกิน source หรือไม่

## Source

- NotebookLM raw synthesis: [2026-07-05-analyzing-financial-statements-of-foreign-and-thai-stocks-notebooklm.md](../../../09-Archive/Inbox/2026-07-05/2026-07-05-analyzing-financial-statements-of-foreign-and-thai-stocks-notebooklm.md)
- NotebookLM notebook: `8924ac68-2ca6-46f1-b454-42ea2924fce6`
- NotebookLM source: `56e3b2c6-8d4d-4ac6-ab80-b61e88c58d79`

## Checklist

### Source Quality

- [ ] รายงานระบุแหล่งข้อมูลที่ใช้
- [ ] ตัวเลขสำคัญมีที่มา เช่น filing, financial statement, MD&A หรือ earnings data
- [ ] สำหรับหุ้นไทย ใช้ไฟล์จาก SET หรือแหล่งต้นทางที่ตรวจสอบได้
- [ ] แยกข้อมูลจาก source ออกจากความเห็นของ AI

### Financial Statement Coverage

- [ ] Revenue
- [ ] EPS or net profit
- [ ] Gross margin and operating margin
- [ ] Cash flow quality
- [ ] Balance sheet strength
- [ ] Debt and liquidity
- [ ] Capex and major investment needs
- [ ] One-time gains or losses
- [ ] Segment or business unit performance
- [ ] Management explanation from MD&A

### Analysis Quality

- [ ] มี key takeaways ที่ชัดเจน
- [ ] อธิบาย bright spots และ red flags แยกกัน
- [ ] ระบุ investment thesis โดยไม่สรุปเป็นคำสั่งซื้อขาย
- [ ] ระบุ valuation หรือ scenario พร้อม caveat
- [ ] ระบุสิ่งที่ต้องติดตามในไตรมาสถัดไป
- [ ] มี open questions ที่ควรตรวจเอง

### AI Risk Controls

- [ ] ไม่เชื่อ valuation ของ AI โดยไม่ตรวจซ้ำ
- [ ] ไม่ใช้รายงาน AI เป็นคำแนะนำซื้อขาย
- [ ] ตรวจเลขสำคัญกับ source ต้นทาง
- [ ] ตรวจว่า AI ไม่สร้างข้อมูลที่ไม่มีใน source
- [ ] บันทึกข้อจำกัดของรายงานไว้ใน note

## Example

```text
Before saving this report into PKS, verify:
1. Which source files were used?
2. Which numbers came directly from filings?
3. Which sections are AI interpretation?
4. What must be checked manually before any investment decision?
```

## Notes

source แสดงให้เห็นว่า AI สามารถสร้างรายงานที่ดูเป็นมืออาชีพ มีตารางและกราฟได้เร็วมาก แต่ความสวยของรายงานไม่เท่ากับความถูกต้อง นักลงทุนต้องตรวจคุณภาพข้อมูลและเหตุผลด้วยตนเอง

## Tips

- ตรวจเลขก่อนตรวจความเห็น
- ถ้ารายงานไม่มี source list ให้ถือว่ายังไม่พร้อมใช้
- ถ้า AI ให้ buy/sell conclusion ให้เปลี่ยนเป็น question หรือ thesis ที่ต้องตรวจเอง
- เก็บ checklist นี้คู่กับ report template หากสร้าง workflow วิเคราะห์งบซ้ำบ่อย

## Questions

- ควรทำ report template แยกสำหรับหุ้นไทยและหุ้นต่างประเทศหรือไม่
- ควรเก็บ AI-generated reports ไว้ใน project รายตัวหุ้นหรือ reference กลาง
- ควรกำหนดสถานะ `draft`, `reviewed`, และ `verified` สำหรับรายงานลงทุนหรือไม่

## Related

- [AI Earnings Analysis Workflow](ai-earnings-analysis-workflow.md)
- [Thai And Foreign Stock Financial Statement Analysis](thai-and-foreign-stock-financial-statement-analysis.md)
- [AI Review Checklist](../../../08-AI/checklists/ai-review-checklist.md)
- [Vocabulary Index](../../../04-Reference/Vocabulary/vocabulary-index.md)

## Next Actions

- [ ] Use this checklist on one AI-generated earnings report.
- [ ] Add missing report sections to a future investment report template.
- [ ] Decide where verified company-specific reports should live in PKS.
