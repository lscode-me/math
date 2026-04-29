---
description: "Тригонометрические тождества: пифагоровы, двойной и половинный угол, формулы сложения и произведения, метод вспомогательного аргумента, олимпиадные приёмы."
---

# Глава 3.2. Тригонометрические тождества и преобразования

## 3.2.1. Что такое тригонометрическое тождество

**Тождество** — это равенство, верное для всех допустимых значений переменной. В отличие от уравнения (которое надо решить), тождество надо **доказать** — показать, что левая и правая части всегда равны.

Базовое тождество, из которого всё вытекает:

$$\sin^2 x + \cos^2 x = 1$$

Это прямое следствие теоремы Пифагора: если точка $(x, y)$ лежит на единичной окружности ($x^2 + y^2 = 1$), то $x = \cos\alpha$, $y = \sin\alpha$.

Из этого одного тождества, зная определения тангенса и котангенса, немедленно выводятся три **пифагоровых тождества**:

$$\sin^2 x + \cos^2 x = 1$$

$$1 + \tan^2 x = \frac{1}{\cos^2 x} \quad (= \sec^2 x)$$

$$1 + \cot^2 x = \frac{1}{\sin^2 x} \quad (= \csc^2 x)$$

!!! note "Как вывести"
    Второе: разделить первое тождество на $\cos^2 x$. Третье: разделить на $\sin^2 x$.

---

## 3.2.2. Формулы сложения

Ключевые формулы, связывающие тригонометрические функции суммы и разности углов:

$$\sin(\alpha + \beta) = \sin\alpha\cos\beta + \cos\alpha\sin\beta$$

$$\sin(\alpha - \beta) = \sin\alpha\cos\beta - \cos\alpha\sin\beta$$

$$\cos(\alpha + \beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta$$

$$\cos(\alpha - \beta) = \cos\alpha\cos\beta + \sin\alpha\sin\beta$$

$$\tan(\alpha + \beta) = \frac{\tan\alpha + \tan\beta}{1 - \tan\alpha\tan\beta}, \quad \tan(\alpha - \beta) = \frac{\tan\alpha - \tan\beta}{1 + \tan\alpha\tan\beta}$$

### Геометрическое доказательство формулы косинуса разности

Рассмотрим единичную окружность. Точка $A = (\cos\alpha, \sin\alpha)$ и точка $B = (\cos\beta, \sin\beta)$.

Расстояние $|AB|^2 = (\cos\alpha - \cos\beta)^2 + (\sin\alpha - \sin\beta)^2 = 2 - 2(\cos\alpha\cos\beta + \sin\alpha\sin\beta)$.

С другой стороны, хорда определяется углом между $A$ и $B$: $|AB|^2 = 2 - 2\cos(\alpha - \beta)$.

Приравниваем: $\cos(\alpha - \beta) = \cos\alpha\cos\beta + \sin\alpha\sin\beta$.

Из этой единственной формулы все остальные выводятся заменами ($\beta \to -\beta$, $\alpha \to 90° - \alpha$, сложение и т.д.).

---

## 3.2.3. Формулы двойного угла

Подставим $\beta = \alpha$ в формулы сложения:

$$\sin 2\alpha = 2\sin\alpha\cos\alpha$$

$$\cos 2\alpha = \cos^2\alpha - \sin^2\alpha = 1 - 2\sin^2\alpha = 2\cos^2\alpha - 1$$

$$\tan 2\alpha = \frac{2\tan\alpha}{1 - \tan^2\alpha}$$

Три формы для $\cos 2\alpha$ — не избыточность, а удобство: каждая нужна в разных ситуациях.

!!! tip "Применение"
    Формула $\cos 2\alpha = 1 - 2\sin^2\alpha$ немедленно даёт $\sin^2\alpha = \frac{1 - \cos 2\alpha}{2}$ — понижение степени. Аналогично $\cos^2\alpha = \frac{1 + \cos 2\alpha}{2}$.

**Пример.** Вычислить $\sin^4\alpha + \cos^4\alpha$.

$$\sin^4\alpha + \cos^4\alpha = (\sin^2\alpha + \cos^2\alpha)^2 - 2\sin^2\alpha\cos^2\alpha = 1 - 2\sin^2\alpha\cos^2\alpha$$

$$= 1 - \frac{\sin^2 2\alpha}{2} = 1 - \frac{1 - \cos 4\alpha}{4} = \frac{3 + \cos 4\alpha}{4}$$

---

## 3.2.4. Формулы половинного угла

Из $\cos 2\alpha = 1 - 2\sin^2\alpha$ при замене $\alpha \to \alpha/2$:

$$\sin\frac{\alpha}{2} = \pm\sqrt{\frac{1 - \cos\alpha}{2}}$$

$$\cos\frac{\alpha}{2} = \pm\sqrt{\frac{1 + \cos\alpha}{2}}$$

$$\tan\frac{\alpha}{2} = \pm\sqrt{\frac{1 - \cos\alpha}{1 + \cos\alpha}} = \frac{\sin\alpha}{1 + \cos\alpha} = \frac{1 - \cos\alpha}{\sin\alpha}$$

Знак $\pm$ выбирается по четверти, в которой лежит угол $\alpha/2$.

!!! important "Подстановка Вейерштрасса"
    Обозначим $t = \tan\dfrac{\alpha}{2}$. Тогда:
    
    $$\sin\alpha = \frac{2t}{1+t^2}, \qquad \cos\alpha = \frac{1-t^2}{1+t^2}, \qquad d\alpha = \frac{2\,dt}{1+t^2}$$
    
    Эта замена превращает любое рациональное выражение от $\sin\alpha$ и $\cos\alpha$ в рациональную функцию от $t$. В интегральном исчислении она известна как **универсальная тригонометрическая подстановка** и позволяет вычислить любой интеграл вида $\int R(\sin x, \cos x)\,dx$.

---

## 3.2.5. Формулы произведения и суммы

Из формул сложения можно вывести формулы, выражающие **произведение** функций через **сумму** (и обратно).

### Произведение → сумма

Сложим и вычтем формулы для $\cos(\alpha - \beta)$ и $\cos(\alpha + \beta)$:

$$\cos\alpha\cos\beta = \frac{\cos(\alpha-\beta) + \cos(\alpha+\beta)}{2}$$

$$\sin\alpha\sin\beta = \frac{\cos(\alpha-\beta) - \cos(\alpha+\beta)}{2}$$

$$\sin\alpha\cos\beta = \frac{\sin(\alpha+\beta) + \sin(\alpha-\beta)}{2}$$

### Сумма → произведение

Замена $\alpha = \frac{p+q}{2}$, $\beta = \frac{p-q}{2}$:

$$\sin p + \sin q = 2\sin\frac{p+q}{2}\cos\frac{p-q}{2}$$

$$\sin p - \sin q = 2\cos\frac{p+q}{2}\sin\frac{p-q}{2}$$

$$\cos p + \cos q = 2\cos\frac{p+q}{2}\cos\frac{p-q}{2}$$

$$\cos p - \cos q = -2\sin\frac{p+q}{2}\sin\frac{p-q}{2}$$

**Пример.** Упростить $\sin 75° + \sin 15°$.

$$\sin 75° + \sin 15° = 2\sin\frac{75°+15°}{2}\cos\frac{75°-15°}{2} = 2\sin 45°\cos 30° = 2\cdot\frac{\sqrt{2}}{2}\cdot\frac{\sqrt{3}}{2} = \frac{\sqrt{6}}{2}$$

---

## 3.2.6. Метод вспомогательного аргумента

Комбинация $a\sin x + b\cos x$ встречается очень часто — в задачах на нахождение максимума, в тригонометрических уравнениях, в физике (сложение гармонических колебаний).

$$a\sin x + b\cos x = R\sin(x + \varphi)$$

Найдём $R$ и $\varphi$. Раскроем правую часть:

$$R\sin(x+\varphi) = R\cos\varphi\cdot\sin x + R\sin\varphi\cdot\cos x$$

Сравниваем коэффициенты:

$$R\cos\varphi = a, \quad R\sin\varphi = b$$

$$R = \sqrt{a^2 + b^2}, \quad \tan\varphi = \frac{b}{a}$$

!!! important "Вывод"
    $$a\sin x + b\cos x = \sqrt{a^2+b^2}\cdot\sin(x + \varphi), \quad \text{где} \quad \tan\varphi = \frac{b}{a}$$
    
    Максимум выражения равен $\sqrt{a^2+b^2}$, минимум — $-\sqrt{a^2+b^2}$.

**Пример.** Найти максимум $f(x) = 3\sin x + 4\cos x$.

$$R = \sqrt{9 + 16} = 5, \quad f_{\max} = 5.$$

Достигается при $x + \varphi = 90°$, то есть $x = 90° - \varphi = 90° - \arctan\frac{4}{3} \approx 53.1°$.

---

## 3.2.7. Олимпиадные приёмы

### Телескопические произведения

Используя формулу $\sin 2\alpha = 2\sin\alpha\cos\alpha$, запишем:

$$\cos\alpha = \frac{\sin 2\alpha}{2\sin\alpha}$$

Тогда произведение косинусов удваивающихся углов «телескопируется»:

$$\prod_{k=0}^{n-1}\cos\frac{\alpha}{2^k} = \cos\alpha\cdot\cos\frac{\alpha}{2}\cdots\cos\frac{\alpha}{2^{n-1}} = \frac{\sin\alpha}{2^n\sin(\alpha/2^n)}$$

**Пример.** Вычислить $\cos 20°\cdot\cos 40°\cdot\cos 80°$.

Заметим, что $20°, 40°, 80°$ — это $\frac{60°}{3}, \frac{60°\cdot 2}{3}, \frac{60°\cdot 4}{3}$... нет, удобнее другой путь:

$$\cos 20°\cdot\cos 40°\cdot\cos 80° = \cos 20°\cdot\cos(60°-20°)\cdot\cos(60°+20°)$$

Используем тождество $\cos\theta\cdot\cos(60°-\theta)\cdot\cos(60°+\theta) = \frac{\cos 3\theta}{4}$:

$$= \frac{\cos 60°}{4} = \frac{1/2}{4} = \frac{1}{8}$$

### Тождество $\cos\theta\cdot\cos(60°-\theta)\cdot\cos(60°+\theta) = \frac{\cos 3\theta}{4}$

Это полезное тождество выводится из формулы $\cos 3\theta = 4\cos^3\theta - 3\cos\theta$ и замечания, что $\cos(60°-\theta)\cdot\cos(60°+\theta) = \cos^2 60° - \sin^2\theta = \frac{1}{4} - \sin^2\theta$... Проще напрямую:

$$\cos(60°-\theta)\cdot\cos(60°+\theta) = \frac{1}{2}[\cos(-2\theta) + \cos 120°] = \frac{\cos 2\theta}{2} - \frac{1}{4}$$

Тогда:

$$\cos\theta\cdot\left(\frac{\cos 2\theta}{2} - \frac{1}{4}\right) = \frac{\cos\theta\cos 2\theta}{2} - \frac{\cos\theta}{4} = \frac{\cos\theta + \cos 3\theta}{4} - \frac{\cos\theta}{4} = \frac{\cos 3\theta}{4}$$

---

## Итоги главы

- Все тождества вытекают из **основного** $\sin^2 x + \cos^2 x = 1$ и **формулы косинуса разности**.
- Формулы двойного угла (3 варианта для $\cos 2\alpha$) и половинного угла позволяют **понижать степень** тригонометрических выражений.
- **Подстановка Вейерштрасса** $t = \tan(\alpha/2)$ рационализирует любое выражение от $\sin$ и $\cos$.
- **Метод вспомогательного аргумента**: $a\sin x + b\cos x = \sqrt{a^2+b^2}\sin(x+\varphi)$ — стандартный приём нахождения экстремума.
- Формулы «произведение ↔ сумма» и телескопические произведения — основные олимпиадные инструменты.
