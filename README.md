# SQL_exercises
คลังเก็บ Code และแบบฝึกหัดคำสั่ง SQL สำหรับการจัดการและวิเคราะห์ข้อมูล

### คำสั่ง SELECT

`### คำสั่ง SELECT ดึงเฉพาะบาง Column`

```sql
SELECT CustomerName,City FROM Customers;

**คำอธิบาย:**
เลือก Column CustomerName,City จาก Customers Table ใช้เครื่องหมาย ;
เพื่อบอกว่าจบคำสั่งที่ 1 แล้วนะ #SELECT Column1,Column2,... FROM Table_Name;
```
`### คำสั่ง SELECT * ดึงข้อมูลทั้งหมด`

```sql
SELECT * FROM Customers; 

**คำอธิบาย:**
เลือก ทั้งหมด จาก Customers Table # SELECT STAR FROM Customers;
```
`### คำสั่ง SELECT DISTINCT ดึงเฉพาะข้อมูลที่ไม่ซ้ำกันทั้งหมด `

```sql
SELECT DISTINCT Country FROM Customers;

**คำอธิบาย:**
เลือก ข้อมูลประเทศที่ไม่ซ้ำกันทั้งหมด จาก Customers Table
```
