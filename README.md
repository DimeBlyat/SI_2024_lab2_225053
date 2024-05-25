**Втора лабораториска вежба по Софтверско инженерство**
---------------------------------------------------
**Димитар Гештаковски, бр. на индекс 225053**

2. Control Flow Graph

   ![Untitled Diagram drawio](https://github.com/DimeBlyat/SI_2024_lab2_225053/assets/150610538/1766182e-5842-4d1f-b3a9-44a3a0dc55fd)

3. Цикломатска комплексност
Цикломатската комплексност на овој код е 10, истата ја добив преку формулата P+1, каде што P е бројот на предикатни јазли. Во случајoв P=9, па цикломатската комплексност изнесува 10.
   
4. Тест случаи според Every Branch критериумот

   Тест случај	allItems == null	item.getName() == null / item.getName().length() == 0	item.getBarcode() != null	allowed.indexOf(c) == -1	item.getDiscount() > 0	item.getBarcode().charAt(0) == '0'	item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0'	sum <= payment	allItems список	payment	Очекуван резултат	Објаснување
1	true	-	-	-	-	-	-	-	null	100	Исклучок	Списокот allItems е null и се фрла RuntimeException.
2	false	true / true	-	-	-	-	-	-	[new Item(null, "12345", 100, 0)]	100	true	Името на предметот е null и се поставува на "unknown".
3	false	false / false	true	false	true	false	false	true	[new Item("item", "12345", 100, 0.1f)]	100	true	Предметот има валиден баркод и попуст. Цената не е над 300 и баркодот не почнува со '0'.
4	false	false / false	true	true	-	-	-	-	[new Item("item", "12345a", 100, 0)]	100	Исклучок	Баркодот на предметот содржи невалиден карактер и се фрла RuntimeException.
5	false	false / false	false	-	-	-	-	-	[new Item("item", null, 100, 0)]	100	Исклучок	Предметот нема баркод и се фрла RuntimeException.
6	false	false / false	true	false	false	-	-	true	[new Item("item", "12345", 100, 0)]	100	true	Предметот има валиден баркод и нема попуст. Цената не е над 300.
7	false	false / false	true	false	true	true	true	true	[new Item("item", "012345", 400, 0.1f)]	100	true	Сите услови се исполнети, цената е над 300, предметот има попуст и баркодот почнува со '0'.
8	false	false / false	true	false	true	true	true	false	[new Item("item", "012345", 400, 0.1f)]	50	false	Сите услови се исполнети, цената е над 300, предметот има попуст и баркодот почнува со '0', но уплатата е помала од сумата.
5. Тест случаи според Multiple Condition критериумот
   
| `Тест случај` | `item.getPrice() > 300` | `item.getDiscount() > 0` | `item.getBarcode().charAt(0) == '0'` | `allItems список` | `payment` | `Очекуван резултат` | `Објаснување` |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | false | false | false | [new Item("item", "12345", 100, 0] | 100 | true | Ниту еден од условите не е исполнет, предметот нема попуст и има валиден баркод. |
| 2 | false | false | true | [new Item("item", "012345", 100, 0)] | 100 | true | Само третиот услов е исполнет, предметот нема попуст, цената е помала од 300. |
| 3 | false | true | false | [new Item("item", "12345", 100, 0.1f)] | 100 | true | Само вториот услов е исполнет, предметот има попуст, цената е помала од 300. |
| 4 | false | true | true | [new Item("item", "012345", 100, 0.1f)] | 100 | true | Вториот и третиот услов се исполнети, предметот има попуст, цената е помала од 300. |
| 5 | true | false | false | [new Item("item", "12345", 400, 0)] | 100 | true | Само првиот услов е исполнет, предметот нема попуст, баркодот не почнува со '0'. |
| 6 | true | false | true | [new Item("item", "012345", 400, 0)] | 100 | true | Првиот и третиот услов се исполнети, предметот нема попуст, цената е над 300. |
| 7 | true | true | false | [new Item("item", "12345", 400, 0.1f)] | 100 | true | Првиот и вториот услов се исполнети, предметот има попуст, баркодот не почнува со '0'. |
| 8 | true | true | true | [new Item("item", "012345", 400, 0.1f)] | 100 | true | Сите услови се исполнети, предметот има попуст, цената е над 300, баркодот почнува со '0'. |
