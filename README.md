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

`### คำสั่ง SELECT WHERE ดึงข้อมูลกรองเฉพาะเงื่อนไข (WHERE ยังใช้ร่วมกันกับคำสั่งอื่นๆ เช่น UPDATE, DELETE, etc.)`

```sql
SELECT * FROM Customers
WHERE City = 'Berlin';

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง City = Berlin เท่านั้น
#SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

```sql
SELECT * FROM Customers
WHERE CustomerID = 5;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง CustomerID = 5 เท่านั้น
```

```sql
SELECT * FROM Customers
WHERE CustomerID < 80;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง CustomerID น้อยกว่า 80 เท่านั้น
```

### คำสั่ง ORDER BY ใช้เรียงลำดับชุดข้อมูลจาก น้อยไปมาก หรือ มากไปน้อย

```sql
SELECT * FROM Products
ORDER BY Price;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Products เรียงลำดับ Price จากน้อยไปมาก
```

```sql
SELECT * FROM Products
ORDER BY Price DESC;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Products เรียงลำดับ Price จากมากไปน้อย
```

```sql
SELECT * FROM Products
ORDER BY ProductName;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Products เรียงลำดับ ProductName Column ตามตัวอักษร จาก A-Z
```

```sql
SELECT * FROM Products
ORDER BY ProductName DESC;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Products เรียงลำดับ ProductName Column ตามตัวอักษร จาก Z-A
```

```sql
SELECT * FROM Customers
ORDER BY Country, CustomerName;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers เรียงลำดับ Country, CustomerName Column ระบบจะเรียงลำดับตาม Country ก่อน หาก Country ซ้ำกัน ระบบจะเรียงตามชื่อ Customers
```

```sql
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers เรียงลำดับ Country Column จากน้อยไปมาก, CustomerName Column จากมากไปน้อย ระบบจะเรียงลำดับตาม Country ก่อน หาก Country ซ้ำกัน ระบบจะเรียงตามชื่อ Customers
```

### คำสั่ง AND ใช้กรองข้อมูลที่มากกว่า 1 เงื่อนไข (เงื่อนไขทั้งหมดต้องเป็นจริง)

```sql
SELECT * FROM Customers
WHERE Country = 'Mexico' AND CustomerName LIKE 'A%';

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรองประเทศ Mexico และ CustomerName อักษร A นำหน้า ('%A' = ลงท้ายด้วยตัวอักษร A, '%A%' = มีอักษร A เป็นส่วนประกอบ)
```

```sql
SELECT * FROM Customers
WHERE Country = 'Brazil'
AND City = 'Rio de Janeiro'
AND CustomerID > 50;

**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง Country = Brazil และ City = Rio de Janeiro และ CustomerID มากกว่า 50 
```

## Combining AND and OR

```sql
SELECT * FROM Customers
WHERE Country = 'Germany'
AND (CustomerName LIKE 'A%'
OR CustomerName LIKE 'T%');


**คำอธิบาย:**
เลือกทั้งหมด จาก Table Customers กรอง Country = Germany และ CustomerName = A นำหน้า หรือ CustomerName = T นำหน้า (ต้องใส่วงเล็บ ถ้าไม่ใส่ SQL จะแสดงผล ชื่อลูกค้าที่นำหน้าด้วยตัวอักษร A and T โดยกรองข้อมูลประเทศแค่ Germany จะมีผลลัพท์ ประเทศอื่นปะปนมาด้วย
```
