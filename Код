import tkinter as tk
from tkinter import messagebox

def determine_triangle_type(side1, side2, side3):
    """
    Функция вычисляет тип треугольника.
    Возвращает строку с результатом.
    """
    # 1. Проверка на отрицательные или нулевые значения
    if side1 <= 0 or side2 <= 0 or side3 <= 0:
        return "Ошибка: длины сторон должны быть больше нуля!"

    # 2. Проверка неравенства треугольника
    if (side1 + side2 <= side3) or (side1 + side3 <= side2) or (side2 + side3 <= side1):
        return "Ошибка: треугольника с такими сторонами не существует!"

    # 3. Определение типа
    if side1 == side2 and side2 == side3:
        return "Тип треугольника: Равносторонний"
    elif side1 == side2 or side1 == side3 or side2 == side3:
        return "Тип треугольника: Равнобедренный"
    else:
        return "Тип треугольника: Разносторонний"


def on_verify_click():
    """Обработчик нажатия на кнопку"""
    try:
        # Получаем данные из полей и убираем пробелы
        val1 = int(entry_side1.get().strip())
        val2 = int(entry_side2.get().strip())
        val3 = int(entry_side3.get().strip())
    except ValueError:
        # Если ввели не числа — показываем ошибку
        messagebox.showerror("Ошибка данных", "Пожалуйста, введите целые числа!")
        lbl_result.config(text="")
        return

    # Вызываем функцию проверки
    result_text = determine_triangle_type(val1, val2, val3)
    
    # Выводим результат на экран (меняем цвет, если ошибка)
    if "Ошибка" in result_text:
        lbl_result.config(text=result_text, fg="red")
    else:
        lbl_result.config(text=result_text, fg="green")


# --- Создание графического интерфейса ---
window = tk.Tk()
window.title("Тест: Виды треугольников")
window.geometry("450x350")
window.resizable(False, False)

# Рамка для полей ввода, чтобы было красиво
frame_inputs = tk.Frame(window, pady=15)
frame_inputs.pack()

# Поля ввода (используем grid для ровного выравнивания)
tk.Label(frame_inputs, text="Длина стороны А:", font=("Arial", 10)).grid(row=0, column=0, sticky="e", pady=5, padx=5)
entry_side1 = tk.Entry(frame_inputs, width=15)
entry_side1.grid(row=0, column=1, pady=5)

tk.Label(frame_inputs, text="Длина стороны B:", font=("Arial", 10)).grid(row=1, column=0, sticky="e", pady=5, padx=5)
entry_side2 = tk.Entry(frame_inputs, width=15)
entry_side2.grid(row=1, column=1, pady=5)

tk.Label(frame_inputs, text="Длина стороны C:", font=("Arial", 10)).grid(row=2, column=0, sticky="e", pady=5, padx=5)
entry_side3 = tk.Entry(frame_inputs, width=15)
entry_side3.grid(row=2, column=1, pady=5)

# Кнопка проверки
btn_check = tk.Button(window, text="Определить тип", command=on_verify_click, 
                      bg="#4CAF50", fg="white", font=("Arial", 11, "bold"), width=20)
btn_check.pack(pady=10)

# Место для вывода результата
lbl_result = tk.Label(window, text="Здесь появится результат", font=("Arial", 12, "italic"), fg="gray")
lbl_result.pack(pady=10)

# Запуск приложения
window.mainloop()
