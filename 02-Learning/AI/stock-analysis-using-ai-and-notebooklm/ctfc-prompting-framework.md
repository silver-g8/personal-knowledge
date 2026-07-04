# CTFC Prompting Framework

---
title: CTFC Prompting Framework
created: 2026-07-04
updated: 2026-07-04
status: draft
tags:
  - learning
  - prompt-engineering
  - ai
aliases:
  - CTFC
---

## Overview

CTFC คือ framework การเขียน prompt หรือ instruction สำหรับ AI โดยแบ่งเป็น Context, Task, Format และ Constraint

ใน source นี้ CTFC ถูกใช้เพื่อสร้าง AI assistant ที่ตอบคำถามการลงทุนตามกรอบคิดที่กำหนดไว้ และลดโอกาสที่ AI จะตอบมั่วหรือออกนอกบทบาท

## Learning Objective

- เข้าใจส่วนประกอบทั้ง 4 ของ CTFC
- นำ CTFC ไปออกแบบ instruction สำหรับ AI assistant ได้
- รู้ว่าข้อจำกัดหรือ constraint สำคัญต่อคุณภาพคำตอบอย่างไร

## Source

- NotebookLM notebook: `8924ac68-2ca6-46f1-b454-42ea2924fce6`
- NotebookLM source: `099f074a-7d58-4070-b2bc-aa1800719ab5`
- Raw synthesis: [Archived inbox note](../../../09-Archive/Inbox/2026-07-04/2026-07-04-stock-analysis-using-ai-and-notebooklm-notebooklm.md)

## Concepts

| Component | Meaning | Example For Stock Analysis |
| --- | --- | --- |
| Context | AI คือใคร และควรคิดจากมุมมองใด | คุณคือผู้ช่วยวิเคราะห์หุ้นตามกรอบ VI |
| Task | ให้ AI ทำอะไร | วิเคราะห์หุ้น ข่าวเศรษฐกิจ หรือสินทรัพย์ |
| Format | ต้องการคำตอบแบบใด | ตอบสั้น 5 บรรทัด หรือเป็นตาราง |
| Constraint | ข้อห้ามและ guardrails | ห้ามมั่ว ถ้าข้อมูลไม่พอให้บอกว่าไม่พอ |

## Example

```text
Context:
คุณคือผู้ช่วยวิเคราะห์หุ้นตามกรอบ Value Investing

Task:
ช่วยวิเคราะห์ธุรกิจ ความเสี่ยง moat และความเหมาะสมของราคา

Format:
ตอบเป็น bullet สั้น ๆ ไม่เกิน 5 ข้อ ใช้ภาษาง่าย

Constraint:
ถ้าข้อมูลไม่พอให้บอกว่าข้อมูลไม่พอ ห้ามเดา และห้ามสรุปเป็นคำแนะนำซื้อขายโดยตรง
```

## Notes

ส่วนที่ทำให้ CTFC มีพลังคือการบอกทั้ง “อยากให้ทำอะไร” และ “ไม่อยากให้ทำอะไร”

ในงานลงทุน constraint สำคัญมาก เพราะ AI อาจสร้างความมั่นใจเกินจริงได้ ถ้าไม่ได้บังคับให้ยอมรับว่า source ไม่พอหรือไม่สามารถทำนายอนาคตได้

## Tips

- เขียน context ให้ชัด แต่ไม่ควรอ้างว่า AI เป็นบุคคลจริง
- ใช้ task ที่วัดได้ เช่น วิเคราะห์ moat, risk, valuation, uncertainty
- ใช้ format ที่อ่านง่ายและซ้ำได้
- ใส่ constraint เกี่ยวกับ source coverage และ hallucination เสมอ

## Questions

- CTFC ควรถูกบันทึกเป็น template กลางของ PKS หรือไม่
- ควรมี CTFC variant สำหรับ investment, research, writing และ coding หรือไม่

## Related

- [Google Gemini Gems Setup](google-gemini-gems-setup.md)
- [NotebookLM Knowledge Integration](notebooklm-knowledge-integration.md)
- [Codex Workflow](../../../08-AI/codex-workflow.md)

## Next Actions

- [ ] สร้าง prompt template สำหรับ stock analysis assistant
- [ ] สร้าง prompt template สำหรับ NotebookLM source synthesis
- [ ] เพิ่ม CTFC เป็นหัวข้อใน prompt engineering reference ภายหลัง
