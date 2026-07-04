# Google Gemini Gems Setup

---
title: Google Gemini Gems Setup
created: 2026-07-04
updated: 2026-07-04
status: draft
tags:
  - learning
  - ai
  - gemini
  - investing
aliases:
  - Gemini Gems
---

## Overview

Gemini Gems คือการสร้าง custom AI assistant ใน Google Gemini สำหรับงานที่ต้องทำซ้ำ เช่น ผู้ช่วยวิเคราะห์หุ้นตามกรอบความคิดของนักลงทุนต้นแบบ

แนวคิดสำคัญคือไม่ต้องเริ่ม prompt ใหม่ทุกครั้ง แต่ตั้งค่า persona, instructions และ knowledge ไว้ล่วงหน้าให้ AI ทำงานเหมือนผู้ช่วยประจำตัว

## Learning Objective

- เข้าใจว่า Gemini Gems ต่างจากการถาม Gemini แบบทั่วไปอย่างไร
- เข้าใจว่าควรกำหนด role, instruction และ knowledge ให้ AI อย่างไร
- เห็นข้อจำกัดของการใช้ AI persona ด้านการลงทุน

## Source

- NotebookLM notebook: `8924ac68-2ca6-46f1-b454-42ea2924fce6`
- NotebookLM source: `099f074a-7d58-4070-b2bc-aa1800719ab5`
- Raw synthesis: [Archived inbox note](../../../09-Archive/Inbox/2026-07-04/2026-07-04-stock-analysis-using-ai-and-notebooklm-notebooklm.md)

## Concepts

- `Name` และ `Description` ช่วยให้ผู้ใช้จำได้ว่า Gem นี้ทำหน้าที่อะไร
- `Instructions` เป็นหัวใจของ Gem เพราะกำหนดบทบาท งาน รูปแบบคำตอบ และข้อจำกัด
- `Knowledge` ใช้เติม source เฉพาะ เช่น framework การลงทุน เอกสาร หรือ NotebookLM
- Gem เหมาะกับงานซ้ำ ๆ ที่ต้องการคำตอบใน style เดิม

## Example

```text
Name: VI Stock Analysis Assistant

Description:
ช่วยวิเคราะห์หุ้นและข่าวเศรษฐกิจตามกรอบการลงทุนแบบ VI

Instructions:
ใช้ CTFC เพื่อกำหนด Context, Task, Format และ Constraint

Knowledge:
เชื่อมต่อ NotebookLM ที่เก็บ source เกี่ยวกับกรอบการลงทุนของนักลงทุนต้นแบบ
```

## Notes

การสร้าง Gem ไม่ได้ทำให้ AI กลายเป็นผู้เชี่ยวชาญจริง แต่ช่วยสร้าง assistant ที่ตอบซ้ำได้ในกรอบที่กำหนดไว้

สำหรับงานด้านหุ้น จุดสำคัญไม่ใช่แค่ให้ AI ตอบว่า “ซื้อหรือขาย” แต่ให้ AI อธิบายด้วยกรอบคิด เช่น moat, intrinsic value, ความเสี่ยง และความเหมาะสมของราคา

## Tips

- เริ่มจาก persona ที่มีหลักคิดชัดเจนและสม่ำเสมอ
- อย่าใช้ Gem เป็นเครื่องมือทำนายราคาหุ้นระยะสั้น
- เพิ่ม constraint ว่าถ้าข้อมูลไม่พอให้บอกตรง ๆ
- ตรวจ source ที่ใช้ใน Knowledge เสมอ

## Questions

- ควรแยก Gem ตามประเภทงาน เช่น stock analysis, portfolio review, macro summary หรือไม่
- ควรใช้ source แบบใดเป็น ground truth สำหรับแต่ละ persona

## Related

- [CTFC Prompting Framework](ctfc-prompting-framework.md)
- [NotebookLM Knowledge Integration](notebooklm-knowledge-integration.md)
- [Dr. Niwet VI Persona](../../../04-Reference/Investment/dr-niwet-vi-persona.md)

## Next Actions

- [ ] สร้างตัวอย่าง CTFC prompt สำหรับ stock analysis assistant
- [ ] ทดลองเชื่อม NotebookLM source กับ Gemini Gems
- [ ] บันทึกผลลัพธ์และข้อจำกัดหลังทดลองใช้งานจริง
