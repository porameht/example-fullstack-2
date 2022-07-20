# example-fullstack-2

2. Up To You
จงออกแบบข้อสอบเอง พร้อมเฉลย อย่างน้อย 1 ข้อ

***โจทย์ จงอธิบายสาเหตุและประสิทธิภาพของ Searching algorithms ต่อไปนี้ จากนั้นทำการปรับปรุงให้มีประสิทธิภาพสูงสุด โดยโจทย์ให้เป็นการเข้าถึงรายชื่อของพนักงานที่มีรายชื่อ 1 ล้านรายชื่อ***

```
employee_list = [{"id": 12345, "name": "John", "department": "Kitchen"}, {"id": 12458, "name": "Paul", "department": "House Floor"}]
def get_employee(id):
  for employee in employee_list:
    if employee['id'] == id:
  return employee
  
print(get_employee(12458));
## OUTPUT
{'id': 12458, 'name': 'Paul', 'department': 'House Floor'}
```

*เฉลย*
1. big o-notaion ของ algorithms นี้อยู่ที่ o(n) ซึ่งก่อให้เกิดปัญหาทางด้านเวลาและ computation สาเหตุเกิดจาก การเข้าถึงข้อมูลที่เป็นลักษณะตรวจสอบทีละ index กรณีนี้จะใช้เวลานานมาก ถ้าลำดับของ id อยู่ท้ายๆ

2. วิธีการแก้ไขปัญหา ใน ภาษา python จะเลือกใช้เป็น Dictionaries หรือ object แทนการเข้าถึงที่เป็นลักษณะ array หรือ list และทำการเก็บข้อมูลให้อยู่ในรูปของ key แทน index ซึ่งสามารถปรับปรุงประสิทธิภาพให้อยู่ที่ o(1) ได้ สามารถดูได้จากโค้ดตัวอย่างด้านล่าง

```
employee_dict = {
12345: {
"id": "12345",
"name": "John",
"department": "Kitchen"}
,
12458: {
"id": "12458",
"name": "Paul",
"department": "House Floor"}
}
def get_employee_from_dict(id):
  return employee_dict[id];
print(get_employee_from_dict(12458));
## OUTPUT
{'id': 12458, 'name': 'Paul', 'department': 'House Floor'}
```
