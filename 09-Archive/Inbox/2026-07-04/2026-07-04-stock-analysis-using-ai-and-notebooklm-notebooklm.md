# Stock Analysis Using AI And NotebookLM - NotebookLM Source Synthesis

---
title: Stock Analysis Using AI And NotebookLM - NotebookLM Source Synthesis
created: 2026-07-04
updated: 2026-07-04
status: archived
tags:
  - notebooklm
  - learning
  - ai
  - investing
source:
  notebook_id: 8924ac68-2ca6-46f1-b454-42ea2924fce6
  source_id: 099f074a-7d58-4070-b2bc-aa1800719ab5
processed:
  archived_at: 2026-07-04
  command: process-inbox
---

## Summary

- Source นี้สอนการใช้ AI กับการลงทุน โดยตัวอย่างหลักคือการสร้าง AI ผู้ช่วยใน Google Gemini Gems เพื่อจำลองกรอบความคิดของนักลงทุนต้นแบบ เช่น ดร.นิเวศน์
- เป้าหมายคือสร้างผู้ช่วยที่ตอบคำถามหุ้น เศรษฐกิจ และการลงทุนได้ซ้ำ ๆ โดยไม่ต้องเขียน prompt ใหม่ทุกครั้ง
- เครื่องมือหลักคือ Gemini Gems สำหรับสร้าง custom AI และ NotebookLM สำหรับจัดการ knowledge source ที่ AI จะใช้อ้างอิง
- โครงสร้างคำสั่ง AI ใช้สูตร CTFC: Context, Task, Format, Constraint
- NotebookLM และ Deep Research ถูกใช้เพื่อรวบรวมแนวคิดของต้นแบบและนำมาเป็นฐานความรู้เฉพาะทาง
- Source เน้นว่าต้องใส่ constraint ชัดเจน เช่น ถ้าข้อมูลไม่พอให้บอกว่าไม่รู้ และห้ามมั่วข้อมูล
- AI แบบนี้เหมาะกับการจำลองผู้เชี่ยวชาญที่มี framework ชัดเจนและสม่ำเสมอ ไม่เหมาะกับต้นแบบที่เปลี่ยนแนวคิดบ่อย
- ตัวอย่างการวิเคราะห์เน้นกรอบ VI เช่น moat, intrinsic value, ราคาที่เหมาะสม และความแตกต่างระหว่างการลงทุนกับการเก็งกำไร
- Source มีตัวอย่างการถาม AI เกี่ยวกับ Nvidia, Bitcoin, ทองคำ และเหตุการณ์สงคราม เพื่อทดสอบว่าคำตอบยังอยู่ในกรอบความคิดของต้นแบบหรือไม่
- Source ยังแนะนำหนังสือด้านการลงทุนหลายเล่มเพื่อใช้ศึกษา mindset และระบบการลงทุนเพิ่มเติม

## Main Concepts

| Concept | Explanation | Why It Matters |
| --- | --- | --- |
| Gemini Gems | Custom AI ใน Gemini ที่เก็บ persona, instructions และ knowledge สำหรับงานซ้ำ ๆ | ลดการเขียน prompt ซ้ำและทำให้ workflow คงที่ |
| CTFC | Framework การเขียน prompt: Context, Task, Format, Constraint | ช่วยกำหนดบทบาท งาน รูปแบบคำตอบ และ guardrails |
| NotebookLM Knowledge Integration | ใช้ NotebookLM เป็นฐานความรู้เฉพาะทางเพื่อป้อนข้อมูลให้ AI | ทำให้ AI ตอบตาม source มากกว่าตอบแบบทั่วไป |
| Deep Research | ฟีเจอร์ช่วยค้นและรวบรวมข้อมูลจากหลายแหล่ง | ลดเวลาสร้าง knowledge base |
| Investment Persona | การจำลองนักลงทุนต้นแบบที่มีหลักคิดชัดเจน | ทำให้ AI ตอบตามกรอบคิดเดียวกันอย่างสม่ำเสมอ |

## Key Terms

| Term | Meaning From Source | Related Topic |
| --- | --- | --- |
| Gems | เครื่องมือสร้าง AI ผู้ช่วยเฉพาะทางใน Gemini | AI automation |
| CTFC | สูตรเขียนคำสั่ง AI แบบ Context, Task, Format, Constraint | Prompt engineering |
| Instructions | พื้นที่กำหนดพฤติกรรมและหน้าที่ของ AI | AI assistant design |
| Knowledge | ฐานข้อมูลหรือ source ที่ให้ AI ใช้ตอบคำถาม | Knowledge management |
| NotebookLM | เครื่องมือจัดการและถามตอบกับ source | PKS, research workflow |
| Deep Research | การรวบรวมข้อมูลเพื่อสร้างฐานความรู้ | Research automation |
| Moat | ความได้เปรียบเชิงแข่งขันที่ยั่งยืน | Value investing |
| Intrinsic Value | มูลค่าที่แท้จริงของกิจการหรือสินทรัพย์ | Fundamental analysis |

## Differences From Previous Methods

| Old Way | New Way From Source | Practical Impact |
| --- | --- | --- |
| ถามผู้เชี่ยวชาญโดยตรง ต้องรอโอกาสและเกรงใจ | สร้าง AI persona ที่จำลองกรอบคิดของผู้เชี่ยวชาญ | ถามได้บ่อยขึ้นและไม่รบกวนบุคคลจริง |
| ใช้ chatbot ทั่วไป ต้องเขียน prompt ซ้ำทุกครั้ง | ใช้ Gemini Gems เก็บ role, instructions และ knowledge | ได้ workflow ที่ทำซ้ำได้และลดความผิดพลาด |
| ค้นข้อมูลเองทีละแหล่ง | ใช้ NotebookLM และ Deep Research รวม source | สร้างฐานความรู้ได้เร็วขึ้น |
| AI ตอบจากความรู้ทั่วไป | AI ตอบจาก source และ constraint ที่กำหนด | ลด hallucination และคุมกรอบคำตอบได้ดีขึ้น |

## Practical Actions

- [ ] สร้าง Gemini Gem ด้วย CTFC
  - Reason: เพื่อกำหนด persona, task, response format และข้อจำกัด
  - Expected result: ได้ AI ผู้ช่วยด้านการวิเคราะห์หุ้นที่มีกรอบตอบชัดเจน
- [ ] รวบรวม source ใน NotebookLM
  - Reason: เพื่อสร้าง knowledge base จากแนวคิดของนักลงทุนต้นแบบ
  - Expected result: AI ตอบโดยอิง source มากกว่าตอบทั่วไป
- [ ] ใช้ Deep Research เพื่อหา framework ของต้นแบบ
  - Reason: ลดงานค้นคว้าด้วยมือ
  - Expected result: ได้ source ตั้งต้นสำหรับสอน AI
- [ ] ตรวจและคัดกรอง source ที่ import แล้ว
  - Reason: ลด source ที่ fail หรือไม่น่าเชื่อถือ
  - Expected result: knowledge base สะอาดขึ้น
- [ ] อัปเดตข้อมูลและ prompt ต่อเนื่อง
  - Reason: ตลาดและข้อมูลเปลี่ยนได้
  - Expected result: AI assistant มีความทันสมัยและใช้ได้จริงขึ้น

## Learning Note Plan

| Proposed File | Main Idea | Suggested Folder | Decision | Reason |
| --- | --- | --- | --- | --- |
| `google-gemini-gems-setup.md` | วิธีสร้าง Gemini Gem สำหรับ stock analysis | `02-Learning/AI/stock-analysis-using-ai-and-notebooklm/` | Create New | ยังไม่มี note เฉพาะเรื่องนี้ |
| `ctfc-prompting-framework.md` | Framework CTFC สำหรับ prompt ที่ควบคุมคุณภาพคำตอบ | `02-Learning/AI/stock-analysis-using-ai-and-notebooklm/` | Create New | ใช้ซ้ำได้กับหลาย AI workflow |
| `notebooklm-knowledge-integration.md` | ใช้ NotebookLM/Deep Research เป็น knowledge base ให้ AI | `02-Learning/AI/stock-analysis-using-ai-and-notebooklm/` | Create New | เชื่อม AI workflow กับ PKS โดยตรง |
| `dr-niwet-vi-persona.md` | Persona/reference สำหรับกรอบคิด VI ที่ source ใช้เป็นตัวอย่าง | `04-Reference/Investment/` | Create New | เป็น reference มากกว่า learning note |
| `investment-reading-list.md` | รายชื่อหนังสือและแหล่งศึกษาที่ source กล่าวถึง | `04-Reference/Investment/` | Create New | เป็น reference สำหรับศึกษาเพิ่ม |

## Related Topics

| Topic | Relationship | Suggested Link Type |
| --- | --- | --- |
| Gemini Gems | Direct | Tool / feature reference |
| CTFC Framework | Direct | Methodology / standard |
| NotebookLM Deep Research | Direct | Research workflow |
| Value Investing | Direct | Investment framework |
| Economic Moat | Direct | Core concept |
| Intrinsic Value | Direct | Valuation concept |
| Prompt Engineering | AI suggestion | Parent category |
| Knowledge Management | AI suggestion | General system |
| Asset Allocation | AI suggestion | Strategy / portfolio |
| Behavioral Finance | AI suggestion | Academic / theory |

## Source Caveats

- Source นี้เน้น workflow การสร้าง AI ผู้ช่วย ไม่ใช่บทเรียนการวิเคราะห์งบการเงินเชิงลึก
- Source ไม่ได้เปรียบเทียบกับ stock screener, technical analysis tools หรือ quantitative systems โดยตรง
- ตัวอย่างคำตอบของ AI ใน source เป็นการสาธิตกรอบความคิด ไม่ใช่คำแนะนำลงทุน
- ควรตรวจสอบข้อมูลหลักทรัพย์จริงจากแหล่งทางการก่อนตัดสินใจลงทุน
