# 🧮 Complex Number Calculator (Калькулятор комплексных чисел)

Учебный Java-проект, реализующий калькулятор для работы с комплексными числами. Проект спроектирован с использованием принципов объектно-ориентированного программирования (ООП), паттернов проектирования (через интерфейс операций) и включает систему логирования.

---

## 📂 Структура проекта

Исходный код приложения находится в директории `src` и разделен на логические пакеты:

```text
src/
├── app/
│   └── Main.java                      # Точка входа в приложение
├── model/
│   ├── CalculatorModel.java           # Модель калькулятора (выполнение и логирование)
│   ├── ComplexNumber.java             # Представление комплексного числа
│   └── operations/
│       ├── ComplexOperation.java      # Интерфейс для математических операций
│       ├── AdditionOperation.java     # Операция сложения
│       ├── MultiplicationOperation.java # Операция умножения
│       └── DivisionOperation.java     # Операция деления
└── service/
    └── OperationLogger.java           # Сервис логирования действий




package app;

import model.CalculatorModel;
import model.ComplexNumber;
import model.operations.AdditionOperation;
import model.operations.DivisionOperation;
import model.operations.MultiplicationOperation;
import service.OperationLogger;

public class Main {
    public static void main(String[] args) {
        OperationLogger logger = new OperationLogger();
        CalculatorModel calculator = new CalculatorModel(logger);

        ComplexNumber num1 = new ComplexNumber(3, 2);
        ComplexNumber num2 = new ComplexNumber(1, 4);

        // Сложение
        ComplexNumber sum = calculator.calculate(new AdditionOperation(), num1, num2);
        System.out.println("Result: " + sum);

        // Умножение
        ComplexNumber product = calculator.calculate(new MultiplicationOperation(), num1, num2);
        System.out.println("Result: " + product);

        // Деление
        ComplexNumber quotient = calculator.calculate(new DivisionOperation(), num1, num2);
        System.out.println("Result: " + quotient);
    }
}
    
