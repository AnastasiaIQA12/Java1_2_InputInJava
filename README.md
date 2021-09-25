# Домашнее задание к занятию «1.1. Введение в Java: JDK, JRE, JVM, IntelliJ IDEA»

## Задача №2 - Credit Card Number Validator

### Легенда
Вы попали в небольшой стартап, который помогает осуществлять приём платежей с банковских карт различным организациям. Стартап находится в самом этапе зарождения, поэтому первое, что они решили сделать - реализовать функциональность валидации номера банковской карты. Но как всегда бывает в стартапах, программист, который взялся реализовывать эту функциональность, исчез и не отвечает на звонки.

Но от него остались некоторые наработки вот в таком виде:
```java
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}
```
Что нужно сделать:
1. Установить IntelliJ IDEA согласно 
2. Проверить работу этой программы с разными тестовыми данными 
3. Подготовьте отчёт о проведённом тестировании и разместите его в репозитории. 

Итого: должен быть репозиторий на GitHub, в котором расположен отчёт о проведённом тестировании и заведены баг-репорты в Issues (если баги есть).
