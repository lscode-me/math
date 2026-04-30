---
description: "Обратные тригонометрические функции: arcsin, arccos, arctan, их области, графики, тождества и уравнения."
---

# Глава 3.4. Обратные тригонометрические функции

## 3.4.1. Зачем нужны обратные функции

В [§3.3](equations.md) мы написали $x = \arcsin a$ как формальное обозначение. Пора разобраться, что это такое.

**Проблема:** Функция $\sin x$ не является взаимно однозначной — например, $\sin 30° = \sin 150° = \frac{1}{2}$. У «обратной» функции должен быть единственный ответ на вопрос «при каком $x$ значение равно $a$?» Это требует **ограничения области определения**.

Математика договорилась: выбрать на каждой тригонометрической функции «главную ветвь» — промежуток, на котором функция строго монотонна. На этой ветви обратная функция определена однозначно.

---

## 3.4.2. Арксинус

**Определение.** $y = \arcsin x$ — это угол $y \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$, синус которого равен $x$:

$$\arcsin x = y \quad \Leftrightarrow \quad \sin y = x \quad \text{и} \quad y \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$$

**Область определения:** $x \in [-1, 1]$.  
**Область значений:** $y \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$.  
**Монотонность:** строго возрастает.  
**Нечётность:** $\arcsin(-x) = -\arcsin x$.

### Таблица значений

| $x$ | $-1$ | $-\frac{\sqrt{3}}{2}$ | $-\frac{\sqrt{2}}{2}$ | $-\frac{1}{2}$ | $0$ | $\frac{1}{2}$ | $\frac{\sqrt{2}}{2}$ | $\frac{\sqrt{3}}{2}$ | $1$ |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| $\arcsin x$ | $-\frac{\pi}{2}$ | $-\frac{\pi}{3}$ | $-\frac{\pi}{4}$ | $-\frac{\pi}{6}$ | $0$ | $\frac{\pi}{6}$ | $\frac{\pi}{4}$ | $\frac{\pi}{3}$ | $\frac{\pi}{2}$ |

---

## 3.4.3. Арккосинус

**Определение.** $y = \arccos x$ — угол $y \in [0, \pi]$, косинус которого равен $x$:

$$\arccos x = y \quad \Leftrightarrow \quad \cos y = x \quad \text{и} \quad y \in [0, \pi]$$

**Область определения:** $x \in [-1, 1]$.  
**Область значений:** $y \in [0, \pi]$.  
**Монотонность:** строго убывает.  
**Симметрия:** $\arccos(-x) = \pi - \arccos x$.

---

## 3.4.4. Арктангенс

**Определение.** $y = \arctan x$ — угол $y \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$, тангенс которого равен $x$:

$$\arctan x = y \quad \Leftrightarrow \quad \tan y = x \quad \text{и} \quad y \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$$

**Область определения:** $x \in \mathbb{R}$ (тангенс принимает все вещественные значения).  
**Область значений:** $y \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$.  
**Горизонтальные асимптоты:** $y \to \pm\frac{\pi}{2}$ при $x \to \pm\infty$.  
**Нечётность:** $\arctan(-x) = -\arctan x$.

!!! note "Арккотангенс"
    Аналогично вводится $\text{arccot}\, x = y \in (0, \pi)$ такое, что $\cot y = x$. В задачах встречается реже.

---

## 3.4.5. Ключевые тождества

### Связь $\arcsin$ и $\arccos$

$$\arcsin x + \arccos x = \frac{\pi}{2}, \quad x \in [-1, 1]$$

**Доказательство.** Пусть $\arcsin x = \alpha$. Тогда $\sin\alpha = x$, и $\cos\!\left(\frac{\pi}{2} - \alpha\right) = \sin\alpha = x$, причём $\frac{\pi}{2} - \alpha \in [0, \pi]$ — значит, $\arccos x = \frac{\pi}{2} - \alpha$. ∎

### Связь $\arctan$ и $\text{arccot}$

$$\arctan x + \text{arccot}\, x = \frac{\pi}{2}, \quad x \in \mathbb{R}$$

### Формула для $\arctan$ отрицательного аргумента

$$\arctan\frac{1}{x} = \begin{cases} \dfrac{\pi}{2} - \arctan x, & x > 0 \\ -\dfrac{\pi}{2} - \arctan x, & x < 0 \end{cases}$$

### «Тригонометрия от обратной тригонометрии»

Часто нужно вычислить $\sin(\arccos x)$ или $\cos(\arctan x)$. Нарисуем прямоугольный треугольник.

**Пример.** Найти $\sin(\arccos x)$.

Пусть $\arccos x = \alpha$. Тогда $\cos\alpha = x$, $\alpha \in [0, \pi]$, значит $\sin\alpha \geq 0$:

$$\sin(\arccos x) = \sqrt{1 - \cos^2\alpha} = \sqrt{1 - x^2}$$

**Пример.** Найти $\cos(\arctan x)$.

Пусть $\arctan x = \alpha$, $\tan\alpha = x$. Из $1 + \tan^2\alpha = \frac{1}{\cos^2\alpha}$:

$$\cos^2\alpha = \frac{1}{1 + \tan^2\alpha} = \frac{1}{1 + x^2}, \quad \cos\alpha > 0 \text{ (т.к. } \alpha \in (-\frac{\pi}{2}, \frac{\pi}{2}))$$

$$\cos(\arctan x) = \frac{1}{\sqrt{1+x^2}}$$

Полная таблица:

| Выражение | Значение |
|-----------|---------|
| $\sin(\arccos x)$ | $\sqrt{1-x^2}$ |
| $\cos(\arcsin x)$ | $\sqrt{1-x^2}$ |
| $\tan(\arcsin x)$ | $\dfrac{x}{\sqrt{1-x^2}}$ |
| $\sin(\arctan x)$ | $\dfrac{x}{\sqrt{1+x^2}}$ |
| $\cos(\arctan x)$ | $\dfrac{1}{\sqrt{1+x^2}}$ |
| $\tan(\arccos x)$ | $\dfrac{\sqrt{1-x^2}}{x}$ |

---

## 3.4.6. Формулы сложения для arctan

В олимпиадных задачах и при вычислениях пригодится:

$$\arctan a + \arctan b = \arctan\frac{a+b}{1-ab} + \begin{cases} \pi, & ab > 1,\, a > 0 \\ -\pi, & ab > 1,\, a < 0 \\ 0, & ab < 1 \end{cases}$$

**Пример.** Доказать, что $\arctan\frac{1}{2} + \arctan\frac{1}{3} = \frac{\pi}{4}$.

$$\arctan\frac{1}{2} + \arctan\frac{1}{3} = \arctan\frac{\frac{1}{2}+\frac{1}{3}}{1-\frac{1}{2}\cdot\frac{1}{3}} = \arctan\frac{5/6}{5/6} = \arctan 1 = \frac{\pi}{4}$$

(Поправка не нужна: $ab = \frac{1}{6} < 1$.)

**Формула Мэчина** (1706), использовавшаяся для вычисления $\pi$ вручную с сотнями знаков:

$$\frac{\pi}{4} = 4\arctan\frac{1}{5} - \arctan\frac{1}{239}$$

---

## 3.4.7. Уравнения с обратными тригонометрическими функциями

**Тип 1.** $\arcsin f(x) = \arcsin g(x)$

Поскольку $\arcsin$ — строго монотонная, это равносильно $f(x) = g(x)$ (при условии, что оба значения в $[-1, 1]$).

**Тип 2.** $\arcsin x = \arccos x$

Из тождества $\arcsin x + \arccos x = \frac{\pi}{2}$: $2\arcsin x = \frac{\pi}{2}$, т.е. $\arcsin x = \frac{\pi}{4}$, значит $x = \frac{\sqrt{2}}{2}$.

**Тип 3.** $\arctan x + \arctan\frac{1}{x} = \frac{\pi}{2}$ при $x > 0$.

Это просто тождество $\arctan x + \text{arccot}\, x = \frac{\pi}{2}$ (так как $\text{arccot}\, x = \arctan\frac{1}{x}$ при $x > 0$).

**Пример.** Решить $\arcsin(2x^2 - 1) = \arccos x$.

Из $\arcsin\alpha = \arccos\beta \Leftrightarrow \alpha = \sin(\arccos\beta) = \sqrt{1-\beta^2}$ (при $\alpha \geq 0$) или $\alpha = -\sqrt{1-\beta^2}$ (при $\alpha < 0$). Но удобнее использовать тождество: $\arcsin\alpha = \frac{\pi}{2} - \arccos\alpha$, поэтому уравнение равносильно $\arccos(1-2x^2) = \arccos x + \frac{\pi}{2}$... Проще так:

$\arcsin(2x^2-1) = \arccos x$ означает, что угол $\alpha$ такой, что $\sin\alpha = 2x^2-1$ и $\cos\alpha = x$ (ведь $\arccos x = \frac{\pi}{2} - \arcsin x$, т.е. $\arcsin(2x^2-1) = \frac{\pi}{2} - \arcsin x$, значит $\arcsin(2x^2-1) + \arcsin x = \frac{\pi}{2}$, значит $\arccos(2x^2-1) = \arcsin x$, то есть $2x^2-1 = \cos(\arcsin x) = \sqrt{1-x^2}$).

$$2x^2 - 1 = \sqrt{1-x^2}$$

Возведём в квадрат (при условии $2x^2 - 1 \geq 0$, т.е. $|x| \geq \frac{1}{\sqrt{2}}$):

$$(2x^2-1)^2 = 1-x^2 \quad \Rightarrow \quad 4x^4 - 4x^2 + 1 = 1 - x^2 \quad \Rightarrow \quad 4x^4 - 3x^2 = 0$$

$$x^2(4x^2 - 3) = 0 \quad \Rightarrow \quad x = 0 \text{ или } x = \pm\frac{\sqrt{3}}{2}$$

Проверка: $x = 0$ не удовлетворяет $|x| \geq \frac{1}{\sqrt{2}}$. $x = \frac{\sqrt{3}}{2}$: $2\cdot\frac{3}{4}-1 = \frac{1}{2} \geq 0$ ✓, $\sqrt{1-\frac{3}{4}} = \frac{1}{2}$ ✓. $x = -\frac{\sqrt{3}}{2}$: $\arccos\!\left(-\frac{\sqrt{3}}{2}\right) = \frac{5\pi}{6}$, но $\arcsin(\cdot) \in [-\frac{\pi}{2}, \frac{\pi}{2}]$ — не совпадёт. ✗

**Ответ:** $x = \frac{\sqrt{3}}{2}$.

---

!!! abstract "Резюме главы"
    - $\arcsin$, $\arccos$, $\arctan$ — «главные ветви» обратных тригонометрических функций с фиксированными областями значений $\left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$, $[0, \pi]$, $\left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$
    - Ключевое тождество: $\arcsin x + \arccos x = \frac{\pi}{2}$
    - «Тригонометрия от обратной тригонометрии» считается через прямоугольный треугольник (например, $\sin(\arccos x) = \sqrt{1-x^2}$)
    - Формула сложения $\arctan a + \arctan b$ позволяет суммировать арктангенсы и лежит в основе формул для вычисления $\pi$
    - Уравнения с обратными функциями решаются применением соответствующих прямых функций к обеим частям — с обязательной проверкой ОДЗ

---

!!! tip "Что дальше"
    Мы завершили тригонометрический раздел. Впереди — **комбинаторика**: искусство подсчёта. В [§4.1 «Комбинаторика»](../combinatorics/combinatorics.md) мы узнаем, сколькими способами можно выбрать, расставить и распределить объекты — и как не запутаться в формулах перестановок, размещений и сочетаний.
