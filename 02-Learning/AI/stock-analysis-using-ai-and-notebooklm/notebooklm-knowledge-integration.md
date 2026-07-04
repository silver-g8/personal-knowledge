# NotebookLM Knowledge Integration

---
title: NotebookLM Knowledge Integration
created: 2026-07-04
updated: 2026-07-04
status: draft
tags:
  - learning
  - notebooklm
  - ai
  - knowledge-management
aliases:
  - NotebookLM Knowledge Base
---

## Overview

NotebookLM ใช้เป็นพื้นที่รวบรวม source และสร้าง knowledge base สำหรับ AI assistant

ใน workflow ของ source นี้ NotebookLM ช่วยรวบรวมแนวคิดของนักลงทุนต้นแบบ แล้วนำข้อมูลนั้นไปเชื่อมกับ Gemini Gems เพื่อให้ AI ตอบคำถามในกรอบความคิดที่กำหนดไว้

## Learning Objective

- เข้าใจบทบาทของ NotebookLM ในการสร้าง AI assistant
- ใช้ source และ Deep Research เพื่อสร้าง knowledge base ได้
- รู้ว่าต้องคัดกรอง source ก่อนใช้งานจริง

## Source

- NotebookLM notebook: `8924ac68-2ca6-46f1-b454-42ea2924fce6`
- NotebookLM source: `099f074a-7d58-4070-b2bc-aa1800719ab5`
- Raw synthesis: [Archived inbox note](../../../09-Archive/Inbox/2026-07-04/2026-07-04-stock-analysis-using-ai-and-notebooklm-notebooklm.md)

## Concepts

- `Source`: เอกสาร คลิป เว็บไซต์ หรือข้อมูลที่ NotebookLM ใช้อ้างอิง
- `Deep Research`: ฟีเจอร์ช่วยค้นและรวบรวมข้อมูลจากอินเทอร์เน็ต
- `Import`: การนำข้อมูลที่รวบรวมได้กลับเข้า notebook
- `Filter`: การคัด source ที่ fail หรือไม่น่าเชื่อถือออก
- `Knowledge Integration`: การนำ notebook ไปใช้เป็นฐานความรู้ให้ AI assistant

## Example

```text
1. สร้าง NotebookLM notebook สำหรับหัวข้อการลงทุน
2. เพิ่ม source เช่น คลิป บทสัมภาษณ์ บทความ หรือหนังสือ
3. ใช้ Deep Research เพื่อรวบรวม framework ของนักลงทุนต้นแบบ
4. ลบ source ที่ fail หรือไม่น่าเชื่อถือ
5. เชื่อม notebook เข้ากับ Gemini Gems ในส่วน Knowledge
6. ทดสอบถามหุ้นหรือเหตุการณ์เศรษฐกิจ แล้วดูว่าคำตอบอยู่ในกรอบหรือไม่
```

## Notes

NotebookLM ไม่ได้แทนที่การตรวจสอบข้อมูล แต่ช่วยทำให้ AI มี source ที่ชัดเจนขึ้น

สำหรับ PKS v2 จุดที่มีคุณค่าคือการเปลี่ยน source ให้กลายเป็น notes ที่ค้นคืนได้ เช่น Learning Notes, Reference Notes และ prompt templates

## Tips

- ใช้ NotebookLM เพื่อถาม source เป็นชุด ไม่ถามคำถามใหญ่ครั้งเดียว
- บันทึกผลดิบไว้ใน `00-Inbox/` ก่อนแตกเป็น notes
- แยก learning notes ออกจาก reference notes
- คง caveat ไว้เมื่อ source ไม่ครอบคลุมพอ

## Questions

- ควรแบ่ง NotebookLM notebooks ตาม domain เช่น AI, Investment, Linux หรือแยกตาม project
- ควรเก็บ source metadata ใน frontmatter ทุกครั้งหรือไม่

## Related

- [Google Gemini Gems Setup](google-gemini-gems-setup.md)
- [CTFC Prompting Framework](ctfc-prompting-framework.md)
- [NotebookLM Workflow](../../../08-AI/notebooklm-workflow.md)
- [learn-from-source](../../../08-AI/commands/learn-from-source.md)

## Next Actions

- [ ] ทดลองใช้ workflow นี้กับ source อื่น
- [ ] สร้าง checklist สำหรับคัดกรอง NotebookLM sources
- [ ] เพิ่มตัวอย่าง NotebookLM prompt library
