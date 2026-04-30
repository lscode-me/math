# Журнал вычитки и редактуры (QA Tracker)

Этот документ — центральный дашборд для отслеживания качества всех написанных глав учебника. Мы используем его для сохранения единого стиля, фиксации принятых решений по итогам ревью и ведения учета проверенных материалов.

---

## 1. Критерии оценки качества (Чек-лист ревьюера)

Для каждой главы мы применяем строгий набор правил:

- **Архитектура и фокус:** Плавное, логичное повествование без скачков на побочные темы. Строгий тайминг выдачи информации.
- **Градиент сложности:** Никакой "магии". Сложные формулы и теоремы выводятся "на пальцах". Постепенное погружение (от яблок/монет к строгим математическим объектам).
- **Наглядность и глубина:** Разбор тонких моментов, деревьев решений и математических парадоксов. Фокус на объяснении механизмов, а не просто констатации фактов. Ограниченное использование программного кода (только если он критически важен для понимания).
- **Единая экосистема:** Обязательное наличие перекрестных ссылок на другие главы (например, отсылка от задач на взвешивания к системам счисления или теории информации).

---

## 2. История ревью и принятые решения

Здесь мы логируем ключевые выводы после проверки батчей (групп глав), чтобы не повторять одни и те же ошибки и придерживаться выбранного курса.

### Батч 1 (Пилотный)
**Проверенные главы:** 
1. `docs/chapters/numbers/collatz.md`
2. `docs/chapters/algorithms/game-of-life.md`
3. `docs/chapters/problem-solving/weighing.md`

**Принятые решения:**
- **Отказ от излишнего кода:** Отклонили идею добавлять Python-сниппеты для симуляций (Коллатц, Игра «Жизнь»), чтобы сфокусироваться на чистом математическом и логическом повествовании.
- **Борьба с "магией" в задачах:** Выявили проблему сухости в `weighing.md` (скачки сложности). Глава была полностью переписана:
  - Добавлено детальное дерево решений для сложной задачи о 12 монетах (ход с перетасовкой).
  - Введена информационная граница Шеннона ($3^k \ge 2n+1$).
  - Добавлен наглядный пример симметричной троичной системы в задаче Баше (взвешивание арбуза).
  - Базовая задача заменена с 8 на 9 монет для идеальной иллюстрации связи с троичной логикой ($3^2 = 9$).

---

## 3. Общий чек-лист глав (Прогресс вычитки)

- `[ ]` **Intro**
  - `[ ]` docs/chapters/intro/preface.md
- `[ ]` **Numbers (Числа)**
  - `[x]` docs/chapters/numbers/collatz.md
  - `[ ]` docs/chapters/numbers/complex.md
  - `[ ]` docs/chapters/numbers/digits-vs-numbers.md
  - `[ ]` docs/chapters/numbers/divisibility.md
  - `[ ]` docs/chapters/numbers/floating-point.md
  - `[ ]` docs/chapters/numbers/infinity.md
  - `[ ]` docs/chapters/numbers/number-types.md
  - `[ ]` docs/chapters/numbers/operations.md
  - `[ ]` docs/chapters/numbers/tables.md
  - `[ ]` docs/chapters/numbers/tetration.md
  - `[ ]` docs/chapters/numbers/transcendental.md
- `[ ]` **Algebra (Алгебра)**
  - `[ ]` docs/chapters/algebra/cubic.md
  - `[ ]` docs/chapters/algebra/dottie.md
  - `[ ]` docs/chapters/algebra/equations.md
  - `[ ]` docs/chapters/algebra/functional-equations.md
  - `[ ]` docs/chapters/algebra/idempotent.md
  - `[ ]` docs/chapters/algebra/quadratic.md
  - `[ ]` docs/chapters/algebra/systems.md
- `[ ]` **Trigonometry (Тригонометрия)**
  - `[ ]` docs/chapters/trigonometry/equations.md
  - `[ ]` docs/chapters/trigonometry/identities.md
  - `[ ]` docs/chapters/trigonometry/inverse.md
  - `[ ]` docs/chapters/trigonometry/trig-values.md
- `[ ]` **Combinatorics (Комбинаторика)**
  - `[ ]` docs/chapters/combinatorics/combinatorics.md
  - `[ ]` docs/chapters/combinatorics/game-theory.md
  - `[ ]` docs/chapters/combinatorics/invariants.md
  - `[ ]` docs/chapters/combinatorics/pigeonhole.md
- `[ ]` **Statistics (Статистика)**
  - `[ ]` docs/chapters/statistics/statistics.md
- `[ ]` **Algorithms (Алгоритмы)**
  - `[ ]` docs/chapters/algorithms/complexity.md
  - `[ ]` docs/chapters/algorithms/data-structures.md
  - `[x]` docs/chapters/algorithms/game-of-life.md
  - `[ ]` docs/chapters/algorithms/probabilistic.md
- `[ ]` **Geometry (Геометрия)**
  - `[ ]` docs/chapters/geometry/areas.md
  - `[ ]` docs/chapters/geometry/circles.md
  - `[ ]` docs/chapters/geometry/euclidea.md
  - `[ ]` docs/chapters/geometry/fractals.md
  - `[ ]` docs/chapters/geometry/inequalities.md
  - `[ ]` docs/chapters/geometry/polyhedra.md
  - `[ ]` docs/chapters/geometry/transformations.md
  - `[ ]` docs/chapters/geometry/triangle-area.md
  - `[ ]` docs/chapters/geometry/triangle-points.md
- `[ ]` **Inequalities (Неравенства)**
  - `[ ]` docs/chapters/inequalities/classical.md
- `[ ]` **Logic (Логика)**
  - `[ ]` docs/chapters/logic/contradiction.md
  - `[ ]` docs/chapters/logic/induction.md
  - `[ ]` docs/chapters/logic/infinite-descent.md
  - `[ ]` docs/chapters/logic/statements.md
- `[ ]` **Number Theory (Теория чисел)**
  - `[ ]` docs/chapters/number-theory/diophantine.md
  - `[ ]` docs/chapters/number-theory/modular.md
  - `[ ]` docs/chapters/number-theory/ramanujan.md
- `[ ]` **Sequences (Последовательности)**
  - `[ ]` docs/chapters/sequences/recurrences.md
  - `[ ]` docs/chapters/sequences/summation.md
- `[ ]` **Probability (Вероятность)**
  - `[ ]` docs/chapters/probability/classical.md
- `[ ]` **Graph Theory (Графы)**
  - `[ ]` docs/chapters/graph-theory/basics.md
- `[ ]` **Set Theory (Теория множеств)**
  - `[ ]` docs/chapters/set-theory/infinity.md
- `[ ]` **Strategic Games (Стратегические игры)**
  - `[ ]` docs/chapters/strategic-games/game-theory.md
- `[ ]` **Information Theory (Теория информации)**
  - `[ ]` docs/chapters/information-theory/shannon.md
- `[ ]` **Physics (Физика)**
  - `[ ]` docs/chapters/physics/mechanics.md
- `[ ]` **Problem Solving (Решение задач)**
  - `[ ]` docs/chapters/problem-solving/arithmetic-puzzles.md
  - `[ ]` docs/chapters/problem-solving/lateral-thinking.md
  - `[ ]` docs/chapters/problem-solving/logic-puzzles.md
  - `[ ]` docs/chapters/problem-solving/missing-data.md
  - `[x]` docs/chapters/problem-solving/weighing.md
