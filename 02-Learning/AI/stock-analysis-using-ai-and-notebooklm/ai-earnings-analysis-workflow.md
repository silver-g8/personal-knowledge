# AI Earnings Analysis Workflow

---
title: AI Earnings Analysis Workflow
created: 2026-07-05
updated: 2026-07-05
status: draft
tags:
  - learning
  - ai
  - investing
  - financial-statements
aliases:
  - Earnings Analysis Workflow
---

## Overview

AI earnings analysis คือ workflow ที่ใช้ AI และ plugin หรือ skill เฉพาะทางช่วยสร้างรายงานวิเคราะห์งบการเงินเบื้องต้น เช่น สรุปผลประกอบการ ตาราง กราฟ จุดเด่น ความเสี่ยง investment thesis และ valuation

source เน้นว่า AI ช่วยลดเวลาการทำงานจากหลายชั่วโมงหรือเป็นวันให้เหลือประมาณ 5-7 นาทีต่อบริษัท แต่ไม่ได้ทำให้นักลงทุนเลิกตรวจสอบข้อมูลเองได้

## Learning Objective

หลังอ่าน note นี้ ควรเข้าใจว่า:

- AI ใช้ช่วยวิเคราะห์งบได้ตรงไหน
- รายงาน AI ควรมีส่วนประกอบอะไร
- ต้องตรวจสอบอะไรซ้ำก่อนนำรายงานไปใช้ตัดสินใจลงทุน

## Source

- NotebookLM raw synthesis: [2026-07-05-analyzing-financial-statements-of-foreign-and-thai-stocks-notebooklm.md](../../../09-Archive/Inbox/2026-07-05/2026-07-05-analyzing-financial-statements-of-foreign-and-thai-stocks-notebooklm.md)
- NotebookLM notebook: `8924ac68-2ca6-46f1-b454-42ea2924fce6`
- NotebookLM source: `56e3b2c6-8d4d-4ac6-ab80-b61e88c58d79`

## Concepts

- `Earnings Analysis`: ฟังก์ชันหรือ agent ที่ช่วยวิเคราะห์ผลประกอบการและสร้างรายงาน
- `Plugin`: ชุดเครื่องมือที่รวม skill หลายด้านเพื่อให้ AI ทำงานเฉพาะทาง
- `Skill`: ความสามารถย่อย เช่น วิเคราะห์งบ สร้างรายงาน หรือทำ model
- `Investment Thesis`: เหตุผลหลักที่อธิบายว่าทำไมบริษัทนี้อาจน่าสนใจหรือไม่น่าสนใจ
- `Token`: โควตาหรือทรัพยากรการประมวลผลของ AI ที่ถูกใช้ตามความซับซ้อนของงาน

## Workflow

1. เลือกบริษัทที่ต้องการวิเคราะห์
2. เรียก workflow วิเคราะห์งบ เช่น `/earnings analysis`
3. ระบุ focus area เช่น revenue, EPS, margin, cash flow, debt, capex หรือ risk
4. ให้ AI สร้างรายงานเบื้องต้น
5. ตรวจโครงสร้างรายงานว่าครบหรือไม่
6. ตรวจเลขสำคัญกับงบต้นทาง
7. บันทึกรายงานไว้ใน PKS เพื่อเทียบกับไตรมาสถัดไป

## Verified Plugin Repository

Verified on: 2026-07-05

| Item | Value |
| --- | --- |
| GitHub organization | `anthropics` |
| Repository | `anthropics/financial-services` |
| Repository URL | <https://github.com/anthropics/financial-services> |
| Repo title | Claude for Financial Services |
| License shown on GitHub | Apache-2.0 |
| Relevant vertical plugin | `equity-research` |
| Relevant command in repo | `/earnings` |
| Relevant skill/command name in repo | `earnings-analysis` |

GitHub shows the `anthropics` organization as verified and controlling the `anthropic.com` domain. The source transcript appears to say `Antropic's Financial Services`, but the verified repository name is `anthropics/financial-services`.

The repository README says it provides reference agents, skills, and data connectors for financial-services workflows such as investment banking, equity research, private equity, and wealth management. It can be installed as a Claude Cowork plugin or used through Claude Managed Agents API. It also lists `Earnings Reviewer` as an agent and `equity-research` as the vertical plugin that includes earnings notes, model updates, thesis tracking, and the `/earnings` command.

### Claude Cowork Install Path

In Claude Cowork:

1. Open `Settings`.
2. Go to `Plugins`.
3. Choose `Add plugin`.
4. Paste this repository URL:

```text
https://github.com/anthropics/financial-services
```

Then select only the agents or vertical plugins you actually need.

### Claude Code Install Commands

The repository README gives these commands:

```bash
claude plugin marketplace add anthropics/financial-services
claude plugin install financial-analysis@claude-for-financial-services
claude plugin install equity-research@claude-for-financial-services
```

The source note's `/earnings analysis` wording maps most closely to the repo's `/earnings` command under the `equity-research` vertical plugin.

### Safety Notes

- Treat this as a research and drafting tool, not an investment decision system.
- The repository README states that the agents draft analyst work product for professional review and do not make investment recommendations.
- MCP connectors listed in the repo may require separate subscriptions or API keys from data providers.
- Install only the verticals you need, because extra tools and connectors can increase complexity and token usage.

## Report Structure To Expect

รายงานที่ source แสดงควรมีอย่างน้อย:

- Executive summary
- Key takeaways
- Revenue analysis
- EPS and margin analysis
- Cash flow quality
- Balance sheet position
- Segment or business unit breakdown
- Bright spots
- Key risks
- Management view or MD&A summary
- Investment thesis
- Valuation or scenario view
- Source list

## Example

```text
Analyze the latest earnings for <ticker>.
Focus equally on revenue growth, EPS, margin, cash flow, debt, capex, and key risks.
Do not make a buy or sell decision. Produce a review report for further checking.
```

## Notes

AI เหมาะกับการทำร่างวิเคราะห์และช่วยไม่ให้พลาดหัวข้อสำคัญ แต่การตัดสินใจลงทุนยังต้องอยู่กับนักลงทุน เพราะ source ย้ำว่า valuation และมุมมองของ AI ต้องตรวจสอบซ้ำเสมอ

source ยังระบุว่าการทำรายงานหนึ่งฉบับอาจใช้ token สูงมาก จึงควรเลือกไฟล์และคำสั่งอย่างระมัดระวัง โดยเฉพาะเมื่อวิเคราะห์หุ้นไทยที่ต้องอัปโหลดเอกสารเอง

## Tips

- เริ่มจากบริษัทที่รู้จักก่อน เพื่อเทียบว่า AI สรุปตรงกับความเข้าใจเดิมหรือไม่
- ระบุ focus area ให้ชัด แทนการให้ AI วิเคราะห์ทุกอย่างแบบกว้างเกินไป
- ใช้ภาษาอังกฤษใน prompt เมื่อเหมาะสม เพราะ source ระบุว่าอาจช่วยประหยัด token
- อย่าใช้รายงาน AI เป็นสัญญาณซื้อขายโดยตรง
- เก็บรายงานเป็น Markdown เพื่อเชื่อมกับ note อื่นใน PKS ได้ง่าย

## Questions

- รายงานที่ AI สร้างควรมีเกณฑ์คุณภาพขั้นต่ำแบบใดก่อนเก็บเข้าคลังถาวร
- ควรสร้าง template รายงานผลประกอบการใน PKS หรือไม่

## Related

- [Thai And Foreign Stock Financial Statement Analysis](thai-and-foreign-stock-financial-statement-analysis.md)
- [AI Investment Report Review Checklist](ai-investment-report-review-checklist.md)
- [NotebookLM Knowledge Integration](notebooklm-knowledge-integration.md)
- [Investment Reading List](../../../04-Reference/Investment/investment-reading-list.md)
- [Vocabulary Index](../../../04-Reference/Vocabulary/vocabulary-index.md)

## Next Actions

- [x] Verify the official plugin/repository name before installing anything.
- [ ] Test this workflow on one foreign stock and one Thai stock.
- [ ] Convert stable report structure into a reusable template if repeated.
