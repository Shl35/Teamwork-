# ระบบบริหารจัดการร้านตัดผม
## Software Requirement Specification Document

**เวอร์ชัน:** 1.0  
**วันที่:** 17 ธันวาคม 2024  
**จัดทำโดย:** ทีมพัฒนาระบบบริหารจัดการร้านตัดผม

---

## ประวัติการจัดทำเอกสาร

| วันที่ | เวอร์ชัน | รายละเอียดการเปลี่ยนแปลง | ผู้ดำเนินการ |
|-------|----------|------------------------|------------|
| 17/12/2024 | 1.0 | จัดทำเอกสารฉบับแรก (Initial Draft) | ทีมพัฒนา |

---

## สารบัญ
1. [Introduction](#1-introduction)
   - 1.1 วัตถุประสงค์
   - 1.2 ภาพรวมของระบบ
   - 1.3 ขอบเขต
   - 1.4 กลุ่มผู้ใช้งาน

2. [System Requirements](#2-system-requirements)
   - 2.1 Hardware Requirements
   - 2.2 Software Requirements
   - 2.3 External Interfaces

3. [Software Requirements](#3-software-requirements)
   - 3.1 ระบบจัดการลูกค้าและสมาชิก (Customer & CRM)
   - 3.2 ระบบจองคิวและบริหารจัดการคิว (Queue & Booking)
   - 3.3 ระบบปฏิบัติการและบริการ (Operation & Service)
   - 3.4 ระบบการเงินและคลังสินค้า (POS & Inventory)
   - 3.5 ระบบรายงานและ Dashboard

4. [Non-Functional Requirements](#4-non-functional-requirements)
   - 4.1 Performance Requirements
   - 4.2 Security Requirements
   - 4.3 Usability Requirements
   - 4.4 Reliability Requirements
   - 4.5 System Constraints

---

## 1. Introduction

### 1.1 วัตถุประสงค์
- เพื่อจัดการการจองคิวตัดผมทั้งรูปแบบออนไลน์และหน้าร้าน (Walk-in) ให้มีประสิทธิภาพ
- เพื่อจัดเก็บประวัติทรงผมและข้อมูลลูกค้าเพื่อการบริการที่ดียิ่งขึ้น
- เพื่อบริหารจัดการตารางงานช่าง การคำนวณค่าคอมมิชชั่น และรายได้
- เพื่อควบคุมสต็อกสินค้าและการชำระเงินที่แม่นยำ

### 1.2 ภาพรวมของระบบ
ระบบบริหารจัดการร้านตัดผมเป็นแพลตฟอร์มแบบครบวงจรที่เชื่อมโยงระหว่างหน้าร้านและออนไลน์ รองรับการทำงานตั้งแต่การจองคิว การบันทึกประวัติการตัดผม การจัดการระบบสมาชิก การขายสินค้า ไปจนถึงการวิเคราะห์ข้อมูลทางธุรกิจ

ระบบงานประกอบด้วยส่วนสำคัญดังนี้:
1. **ระบบบริหารจัดการคิว** - รองรับทั้งการจองล่วงหน้าและลูกค้า Walk-in พร้อมจอแสดงสถานะคิว
2. **ระบบ CRM** - เก็บข้อมูลลูกค้า ระดับสมาชิก (Tier) และประวัติทรงผม (รูปถ่าย)
3. **ระบบ POS และสต็อก** - จัดการการชำระเงิน ตัดสต็อกสินค้า และคำนวณค่ามือช่าง
4. **ระบบพนักงาน** - จัดการตารางงาน เข้างาน/ออกงาน และสรุปผลงานรายบุคคล

### 1.3 ขอบเขต
- ระบบรองรับการจองผ่าน Web, Mobile App และ LINE Official
- ระบบบริหารจัดการหน้าร้าน (POS) และสต็อกสินค้า
- ระบบจัดการข้อมูลช่างและตารางงาน
- ระบบวิเคราะห์ข้อมูลและออกรายงานสำหรับผู้บริหาร

### 1.4 กลุ่มผู้ใช้งาน
1. **ลูกค้า (Customer)**
   - ผู้ใช้งานทั่วไป (Guest)
   - สมาชิก (Member/VIP)
2. **เจ้าหน้าที่ร้าน (Staff)**
   - ช่างตัดผม (Barber/Stylist)
   - พนักงานต้อนรับ/แคชเชียร์ (Receptionist)
3. **ผู้บริหาร/เจ้าของร้าน (Admin/Owner)**

---

## 2. System Requirements

### 2.1 Hardware Requirements
- **Server Requirements:**
  - CPU: 4 Cores ขึ้นไป
  - RAM: 16GB ขึ้นไป
  - Storage: SSD 500GB ขึ้นไป (เน้นพื้นที่สำหรับเก็บรูปภาพทรงผม)

- **Client Requirements:**
  - **Reception Point:** PC หรือ Tablet ประสิทธิภาพสูง พร้อมจอสัมผัส
  - **Barber Station:** Tablet สำหรับช่างเพื่อดูประวัติและถ่ายรูปผลงาน
  - **Display:** Smart TV สำหรับแสดงลำดับคิว

### 2.2 Software Requirements
- **Operating System:** Linux Server (Ubuntu/CentOS) หรือ Windows Server
- **Web Server:** Nginx หรือ Apache
- **Database:** PostgreSQL หรือ MySQL (รองรับ JSON และ Blob สำหรับรูปภาพ)
- **Programming Language:** Node.js, Go หรือ PHP (Laravel)
- **Frontend:** React.js หรือ Vue.js / Mobile: Flutter หรือ React Native

### 2.3 External Interfaces

#### 2.3.1 User Interfaces
| Interface ID | Description | Platform/Technology |
|-------------|-------------|-------------------|
| UI-01 | หน้าเว็บไซต์จองคิวสำหรับลูกค้า | Web Browser (Responsive) |
| UI-02 | แอปพลิเคชันลูกค้า | iOS, Android |
| UI-03 | ระบบหลังบ้าน (Back-office & POS) | Web Browser (Desktop/Tablet) |
| UI-04 | หน้าจอแสดงคิว (Queue Display) | Smart TV Browser |

#### 2.3.2 Hardware Interfaces
| Interface ID | Description | Protocol |
|-------------|-------------|----------|
| HW-01 | เครื่องพิมพ์ใบเสร็จความร้อน | USB/LAN |
| HW-02 | ลิ้นชักเก็บเงิน | RJ11 (ผ่าน Printer) |
| HW-03 | เครื่องสแกนบาร์โค้ด | USB/Bluetooth |
| HW-04 | กล้องถ่ายรูป (บน Tablet/Mobile) | OS Camera API |

#### 2.3.3 Software Interfaces
| Interface ID | Description | Protocol/API |
|-------------|-------------|--------------|
| SW-01 | ระบบชำระเงิน (QR/Credit Card) | Payment Gateway API |
| SW-02 | การแจ้งเตือน LINE OA | LINE Messaging API |
| SW-03 | ระบบ SMS Gateway | REST API |
| SW-04 | Google Maps (สาขา) | Google Maps API |

---

## 3. Software Requirements

### 3.1 ระบบจัดการลูกค้าและสมาชิก (Customer & CRM)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| CRM-01 | ระบบต้องบันทึกข้อมูลลูกค้า: รหัส, ชื่อ, เบอร์โทร, Line ID, วันเกิด, รูปถ่าย | High |
| CRM-02 | ระบบต้องจัดระดับสมาชิก (Bronze, Silver, Gold, Platinum) ตามเงื่อนไขที่กำหนด | High |
| CRM-03 | ระบบสะสมแต้มอัตโนมัติ (1 บาท = 1 แต้ม) และแต้มพิเศษวันเกิด (x2) | High |
| CRM-04 | รองรับสิทธิพิเศษสมาชิก: ส่วนลด (5-20%), สิทธิ์ข้ามคิว (Platinum) | Medium |
| CRM-05 | ระบบต้องสามารถแสดงประวัติการใช้บริการย้อนหลังและแต้มสะสมได้ | High |

### 3.2 ระบบจองคิวและบริหารจัดการคิว (Queue & Booking)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| QUE-01 | รองรับการจองออนไลน์: เลือกสาขา, บริการ, ช่าง, วัน/เวลา | High |
| QUE-02 | รองรับ Walk-in: ออกบัตรคิวหน้าร้านและคำนวณเวลารอโดยประมาณ | High |
| QUE-03 | ระบบแจ้งเตือนการจอง: ยืนยัน (QR Code), เตือนก่อนถึงเวลา, เตือนเมื่อถึงคิว | High |
| QUE-04 | ระบบจัดการสถานะคิว: รอคิว, กำลังบริการ, เสร็จสิ้น, No Show, ยกเลิก | High |
| QUE-05 | หน้าจอ Display แสดงคิวปัจจุบันและคิวถัดไปแบบ Real-time | High |

### 3.3 ระบบปฏิบัติการและบริการ (Operation & Service)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| OPS-01 | จัดการข้อมูลช่าง: ประวัติ, ความเชี่ยวชาญ, ตารางงาน, การลา | High |
| OPS-02 | ระบบกระจายงาน (Dispatch): อัตโนมัติ หรือ เลือกช่างตามความเชี่ยวชาญ | Medium |
| OPS-03 | บันทึกขั้นตอนบริการ: Check-in, ถ่ายรูป Before/After, บันทึกรายละเอียดทรงผม | High |
| OPS-04 | จัดการรายการบริการ (Service Catalog): ราคาปกติ/สมาชิก, ราคาตามความยาวผม | High |
| OPS-05 | Dashboard สำหรับช่าง: ดูคิวงานของตนเอง, รายได้วันนี้, สถิติความพึงพอใจ | Medium |

### 3.4 ระบบการเงินและคลังสินค้า (POS & Inventory)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| POS-01 | คำนวณค่าบริการ: ค่าบริการหลัก + บริการเสริม + สินค้า - ส่วนลด/แต้ม | High |
| POS-02 | รองรับการชำระเงินหลายรูปแบบ: เงินสด, บัตรเครดิต, QR, E-Wallet | High |
| POS-03 | ระบบคำนวณค่าคอมมิชชั่นให้ช่างตัดผมอัตโนมัติตามยอดขาย/บริการ | High |
| POS-04 | จัดการสต็อกสินค้า (Product): ตัดสต็อกเมื่อขาย/ใช้บริการ, แจ้งเตือนของใกล้หมด | High |
| POS-05 | จัดการโปรโมชัน: ซื้อแพ็คเกจ, Happy Hour, โปรโมชันสินค้า | Medium |

### 3.5 ระบบรายงานและ Dashboard (Reporting)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| RPT-01 | Dashboard ผู้บริหาร: รายได้ Real-time, จำนวนคิว, ประสิทธิภาพช่าง | High |
| RPT-02 | รายงานการดำเนินงาน: สรุปรายวัน/เดือน, ช่วงเวลา Peak Time | High |
| RPT-03 | รายงานการเงิน: รายได้แยกตามสาขา/ช่าง, กำไร-ขาดทุน | High |
| RPT-04 | รายงานลูกค้า: อัตราลูกค้าเก่ากลับมาใช้ซ้ำ (Retention Rate), พฤติกรรมลูกค้า | Medium |

---

## 4. Non-Functional Requirements

### 4.1 Performance Requirements

| Requirement ID | Requirement Description | Metric |
|---------------|------------------------|---------|
| PRF-01 | รองรับผู้ใช้งานพร้อมกัน (ลูกค้า+พนักงาน) | ≥ 100 users |
| PRF-02 | เวลาตอบสนองของระบบ (Response Time) | ≤ 2 วินาที |
| PRF-03 | การอัพเดตสถานะคิว (Real-time update) | < 1 วินาที (Delay) |
| PRF-04 | ระบบต้องทำงานได้ตลอดเวลา | 24/7 Availability |

### 4.2 Security Requirements

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| SEC-01 | ระบบต้องปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล (PDPA) | Critical |
| SEC-02 | การยืนยันตัวตน (Authentication) และกำหนดสิทธิ์ (Authorization) | High |
| SEC-03 | Session Timeout เมื่อไม่มีการใช้งานเกิน 30 นาที | Medium |
| SEC-04 | การสำรองข้อมูล (Backup) อัตโนมัติทุกวัน | High |

### 4.3 Usability Requirements

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| USB-01 | รองรับภาษาไทยสมบูรณ์แบบ | High |
| USB-02 | Responsive Design (ใช้ได้ทั้ง Mobile, Tablet, Desktop) | High |
| USB-03 | ระบบ Offline Mode (ทำงานได้บางส่วนเมื่อเน็ตหลุด) | Medium |

### 4.4 Reliability Requirements

| Requirement ID | Requirement Description | Metric |
|---------------|------------------------|---------|
| REL-01 | System Uptime | 99% |
| REL-02 | ระยะเวลาการกู้คืนระบบ (Recovery Time) | ≤ 2 ชั่วโมง |
| REL-03 | ระบบแจ้งเตือนผู้ดูแลเมื่อเกิดข้อผิดพลาด (Error Alert) | ทันที |

### 4.5 System Constraints

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| CON-01 | รูปภาพทรงผมต้องมีขนาดไม่เกิน 5MB ต่อรูป | Medium |
| CON-02 | ต้องมีการเชื่อมต่ออินเทอร์เน็ตสำหรับการจองออนไลน์และการชำระเงิน | Critical |
| CON-03 | Mobile Application รองรับ iOS 12+ และ Android 8.0+ | High |
| CON-04 | เก็บข้อมูลย้อนหลังในระบบไม่น้อยกว่า 3 ปี | Medium |
