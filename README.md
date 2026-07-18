# SQL_exercises
คลังเก็บ Code และแบบฝึกหัดคำสั่ง SQL สำหรับการจัดการและวิเคราะห์ข้อมูล

### คำสั่ง SELECT ใช้สำหรับเลือกข้อมูลจากฐานข้อมูล

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
`### คำสั่ง SELECT DISTINCT ดึงเฉพาะข้อมูลที่ไม่ซ้ำกัน ของ Column1,Column2,... FROM Table_Name;`

```sql
SELECT DISTINCT City,Address FROM Customers;

**คำอธิบาย:**
ดึงเฉพาะข้อมูลที่ไม่ซ้ำกัน ของ Column City,Address FROM Table Customers;
```
`### คำสั่ง SELECT DISTINCT สำหรับ MS Access:`

```sql
SELECT Count(*) As DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);

**คำอธิบาย:**
วงเล็บชั้นใน คือการเลือก ข้อมูลในColumn ประเทศที่ไม่ซ้ำกัน จาก Customers Table
ชั้นนอก คือ นับข้อมูลจาก()ชั้นใน และตั้งชื่อColumn ผลลัพท์ใหม่ As DistinctCountries
```

### คำสั่ง WHERE ดึงข้อมูลแบบมีเงื่อนไข (WHERE ใช้สำหรับกรองข้อมูล)

`### คำสั่ง SELECT WHERE ดึงข้อมูลกรองเฉพาะเงื่อนไข`

```sql
SELECT * FROM Customers
WHERE City = 'Berlin';

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง Row City = Berlin เท่านั้น
```
