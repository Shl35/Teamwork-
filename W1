# ระบบบริหารจัดการร้านตัดผม
## Software Requirement Specification (SRS)

**เวอร์ชัน:** 1.0  
**วันที่:** 10 ธันวาคม 2024  
**จัดทำโดย:** ทีมพัฒนาระบบบริหารจัดการร้านตัดผม  

---

## ประวัติการจัดทำเอกสาร

| วันที่ | เวอร์ชัน | รายละเอียดการเปลี่ยนแปลง | ผู้ดำเนินการ |
|------|---------|------------------------|-------------|
| 10/12/2024 | 1.0 | จัดทำเอกสารข้อกำหนดความต้องการระบบ | ทีมพัฒนา |

---

## สารบัญ
1. [Introduction](#1-introduction)
2. [System Requirements](#2-system-requirements)
3. [Software Requirements](#3-software-requirements)
4. [Non-Functional Requirements](#4-non-functional-requirements)

---

## 1. Introduction

### 1.1 วัตถุประสงค์
- เพื่อพัฒนาระบบบริหารจัดการร้านตัดผมแบบครบวงจร  
- เพื่ออำนวยความสะดวกในการจองคิวและใช้บริการของลูกค้า  
- เพื่อเพิ่มประสิทธิภาพในการจัดการช่าง ตารางงาน และการเงิน  
- เพื่อจัดเก็บข้อมูลลูกค้า ประวัติทรงผม และวิเคราะห์ข้อมูล  

---

### 1.2 ภาพรวมของระบบ
ระบบบริหารจัดการร้านตัดผมเป็นแพลตฟอร์มที่ช่วยให้ร้านสามารถจัดการการจองคิว การให้บริการลูกค้า การจัดการช่าง การชำระเงิน และการออกรายงานได้อย่างมีประสิทธิภาพ รองรับการใช้งานผ่านเว็บและแอปพลิเคชันมือถือ

โมดูลหลักของระบบประกอบด้วย:
1. ระบบลูกค้าและสมาชิก  
2. ระบบจองคิว  
3. ระบบจัดการช่าง  
4. ระบบบริการและราคา  
5. ระบบชำระเงิน  
6. ระบบคลังสินค้า  
7. ระบบรายงานและ Dashboard  

---

### 1.3 ขอบเขตของระบบ
- การจองคิวออนไลน์และ Walk-in  
- การจัดการลูกค้าและสมาชิก  
- การจัดการช่างและตารางงาน  
- การคำนวณราคาและชำระเงิน  
- การออกรายงานและวิเคราะห์ข้อมูล  

---

### 1.4 กลุ่มผู้ใช้งาน
1. ลูกค้า  
   - ลูกค้าทั่วไป  
   - สมาชิก  
2. พนักงานร้าน  
   - ช่างตัดผม  
   - พนักงานหน้าร้าน  
3. ผู้บริหาร / ผู้ดูแลระบบ  

---

## 2. System Requirements

### 2.1 Hardware Requirements
- **Server**
  - CPU: Intel Xeon หรือเทียบเท่า  
  - RAM: 16GB ขึ้นไป  
  - Storage: SSD 500GB ขึ้นไป  

- **Client**
  - อุปกรณ์ที่เชื่อมต่ออินเทอร์เน็ต  
  - Smart Phone / Tablet / PC  

---

### 2.2 Software Requirements
- Operating System: Windows Server / Linux  
- Web Server: Apache หรือ Nginx  
- Database: MySQL 8.0+  
- Backend: PHP / Node.js  
- Frontend: HTML5, CSS, JavaScript  
- Mobile App: iOS / Android  

---

### 2.3 External Interfaces

#### 2.3.1 User Interfaces

| Interface ID | Description | Platform |
|------------|------------|---------|
| UI-01 | เว็บสำหรับลูกค้า | Web Responsive |
| UI-02 | ระบบหลังบ้านร้านตัดผม | Web Desktop |
| UI-03 | แอปพลิเคชันลูกค้า | iOS / Android |
| UI-04 | หน้าจอแสดงคิว | TV Display |

---

#### 2.3.2 Hardware Interfaces

| Interface ID | Description | Protocol |
|------------|------------|----------|
| HW-01 | POS Terminal | HTTPS |
| HW-02 | เครื่องสแกน QR | TCP/IP |

---

#### 2.3.3 Software Interfaces

| Interface ID | Description | API |
|------------|------------|-----|
| SW-01 | ระบบชำระเงิน | Payment Gateway API |
| SW-02 | ระบบแจ้งเตือน | LINE / SMS API |
| SW-03 | แผนที่ร้าน | Google Maps API |

---

## 3. Software Requirements

### 3.1 ระบบลูกค้าและสมาชิก

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| CUS-01 | ระบบต้องจัดเก็บข้อมูลลูกค้าและประวัติทรงผม | High |
| CUS-02 | ระบบต้องรองรับระดับสมาชิกและสิทธิพิเศษ | High |
| CUS-03 | ระบบต้องสะสมแต้มและแลกส่วนลด | High |

---

### 3.2 ระบบจองคิว

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| QUE-01 | ระบบต้องรองรับการจองคิวออนไลน์และ Walk-in | High |
| QUE-02 | ระบบต้องเลือกบริการ วันที่ เวลา และช่าง | High |
| QUE-03 | ระบบต้องแจ้งเตือนลูกค้าก่อนถึงคิว | High |
| QUE-04 | ระบบต้องเลื่อนหรือยกเลิกคิวได้ | High |

---

### 3.3 ระบบจัดการช่าง

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| BAR-01 | ระบบต้องจัดเก็บข้อมูลช่างและความเชี่ยวชาญ | High |
| BAR-02 | ระบบต้องจัดการตารางงานและวันลา | High |
| BAR-03 | ระบบต้องกระจายคิวอัตโนมัติ | High |
| BAR-04 | ระบบต้องคำนวณค่าคอมมิชชั่น | High |

---

### 3.4 ระบบบริการและราคา

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| SER-01 | ระบบต้องจัดการบริการหลัก บริการเสริม และแพ็คเกจ | High |
| SER-02 | ระบบต้องจัดการราคาและโปรโมชัน | High |

---

### 3.5 ระบบชำระเงิน

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| PAY-01 | รองรับเงินสด บัตร QR และ E-Wallet | High |
| PAY-02 | ออกใบเสร็จอิเล็กทรอนิกส์ | High |

---

### 3.6 ระบบคลังสินค้า

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| INV-01 | ระบบต้องจัดการสต็อกสินค้า | High |
| INV-02 | ระบบต้องแจ้งเตือนสินค้าใกล้หมด | High |

---

### 3.7 ระบบรายงานและ Dashboard

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| REP-01 | Dashboard แสดงรายได้และจำนวนลูกค้า | High |
| REP-02 | รายงานรายวันและรายเดือน | High |
| REP-03 | รายงานประสิทธิภาพช่าง | High |

---

## 4. Non-Functional Requirements

### 4.1 Performance Requirements

| ID | Description | Metric |
|----|------------|--------|
| PRF-01 | รองรับผู้ใช้งานพร้อมกัน | ≥ 100 Users |
| PRF-02 | เวลาตอบสนองระบบ | ≤ 2 วินาที |

---

### 4.2 Security Requirements

| ID | Description | Priority |
|----|------------|----------|
| SEC-01 | ระบบยืนยันตัวตนและกำหนดสิทธิ์ผู้ใช้ | High |
| SEC-02 | เข้ารหัสข้อมูลตาม PDPA | High |
| SEC-03 | Session Timeout 30 นาที | Medium |

---

### 4.3 Usability Requirements

| ID | Description | Priority |
|----|------------|----------|
| USB-01 | ใช้งานง่าย เป็นภาษาไทย | High |
| USB-02 | รองรับทุกขนาดหน้าจอ | High |

---

### 4.4 Reliability Requirements

| ID | Description | Metric |
|----|------------|--------|
| REL-01 | System Uptime | 99% |
| REL-02 | สำรองข้อมูลอัตโนมัติ | ทุกวัน |

---
