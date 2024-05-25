Втора лабораториска вежба по Софтверско инженерство
---------------------------------------------------
Димитар Гештаковски, бр. на индекс 225053

2. Control Flow Graph

   ![Untitled Diagram drawio](https://github.com/DimeBlyat/SI_2024_lab2_225053/assets/150610538/1766182e-5842-4d1f-b3a9-44a3a0dc55fd)

3. Цикломатска комплексност
Цикломатската комплексност на овој код е 10, истата ја добив преку формулата P+1, каде што P е бројот на предикатни јазли. Во случајoв P=9, па цикломатската комплексност изнесува 10.
   
4. Тест случаи според критериумот Every statement
   
| `Тест случај` | `item.getPrice() > 300` | `item.getDiscount() > 0` | `item.getBarcode().charAt(0) == '0'` |
| --- | --- | --- | --- |
| 1 | false | false | false |
| 2 | false | false | true |
| 3 | false | true | false |
| 4 | false | true | true |
| 5 | true | false | false |
| 6 | true | false | true |
| 7 | true | true | false |
| 8 | true | true | true |
