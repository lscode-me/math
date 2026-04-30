# Журнал вычитки и редактуры (QA Tracker)

Этот документ — центральный дашборд для отслеживания качества всех написанных глав учебника. Мы используем его для сохранения единого стиля, фиксации принятых решений по итогам ревью и ведения учета проверенных материалов.

## Целевая аудитория
Материал должен быть написан так, чтобы его мог с интересом читать **школьник**, находить в нем пользу **студент** или **выпускник**, использовать для уроков **учитель**, и получать эстетическое удовольствие математический **энтузиаст**.

---

## 1. Критерии оценки качества (Чек-лист ревьюера)

Для каждой главы мы применяем строгий набор фильтров:

### 1.1. Архитектура и фокус (Никакого хаоса)
- **Логический стержень:** Тема должна раскрываться последовательно. Каждая мысль вытекает из предыдущей.
- **Строгий тайминг тем:** Никакого перепрыгивания. Если мы говорим о функции Эйлера, мы не отвлекаемся на теорему Гаусса, если это не нужно для прямого доказательства.

### 1.2. Градиент сложности (Плавное погружение)
- **От простого к сложному:** Глава должна начинаться с интуитивного примера (на пальцах, спичках, монетах) и только потом переходить к строгим формулам.
- **Никакой "магии":** Каждый шаг в выводах должен быть прозрачен. Не должно быть резких скачков сложности, когда читатель перестает понимать происходящее.

### 1.3. Наглядность и глубина (Показывать, а не рассказывать)
- **Разбор деталей:** Нужно обращать внимание на тонкие и парадоксальные моменты. Почему сделано так, а не иначе? Какие есть подводные камни?
- **Демонстрация:** Теория должна подкрепляться геометрическими визуализациями, мысленными экспериментами или таблицами. 
- *Примечание по коду:* Ограниченное использование программного кода. Код (например, Python) добавляется только если он критически важен для понимания механизма, в остальных случаях упор делается на математическую суть.

### 1.4. Единая экосистема (Перекрестные ссылки)
- **Опора на фундамент:** Если в главе используется концепт из прошлого, должна быть явная ссылка (например, *«как мы видели в главе про инварианты (`§4.3`)»*).
- **Задел на будущее:** Главы должны "продавать" следующие разделы, показывая, как текущий инструмент поможет решить более крутые задачи дальше.

---

## 2. Процесс работы (Workflow)

Ревью происходит по следующему алгоритму:
1. Выбирается глава или блок глав (по порядку или по темам).
2. Текст анализируется через призму четырех критериев (см. п. 1).
3. Формируется диагностический отчет с предложениями: где сгладить углы, добавить ссылку или переписать сухой абзац.
4. После согласования вносятся изменения в файлы глав.
5. Завершенные главы отмечаются в "Общем чек-листе" ниже, а ключевые выводы логируются в разделе "История ревью".

---

## 3. История ревью и принятые решения

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

### Батч 2 (Числа: запись и делимость)
**Проверенные главы:**
1. `docs/chapters/numbers/digits-vs-numbers.md`
2. `docs/chapters/numbers/divisibility.md`

**Принятые решения:**
- **Перекрёстные ссылки на позиционную запись:** В `divisibility.md` признаки делимости теперь явно ссылаются на §1.1 (позиционная система), с пояснением, что признаки — свойства *записи*, а не самих чисел. Добавлен пример: в восьмеричной системе аналогичный признак суммы цифр работал бы для делимости на 7.
- **Задел на будущее (мостики):** В `digits-vs-numbers.md` добавлен блок «Что дальше» — связь позиционной записи с признаками делимости и модулярной арифметикой. В `divisibility.md` раздел о делении с остатком теперь «продаёт» главу о модулярной арифметике (сложение, умножение остатков → криптография и олимпиады).
- **Уточнение признака на 11:** Переписано объяснение знакочередующейся суммы — добавлена пошаговая визуализация обхода цифр справа налево с чередованием знаков ($\underset{+}{8},\; \underset{-}{2},\; \underset{+}{9},\; \underset{-}{1},\; \underset{+}{8}$).

### Батч 3 (Физика: реструктуризация)
**Проверенные главы:**
1. `docs/chapters/physics/mechanics.md` → разбита на 3 главы

**Принятые решения:**
- **Реструктуризация:** Монолитная глава `mechanics.md` разбита на три:
  - `kinematics.md` (§18.1) — равноускоренное движение, бросок под углом с детальным анализом через свойства параболы, огибающая Торричелли, вращательное движение и полярные координаты.
  - `dynamics.md` (§18.2) — законы Ньютона, равновесие, наклонная плоскость, фермы (добавлен конкретный пример треугольной фермы), упругий удар, законы сохранения и теорема Нётер.
  - `mechanics.md` (§18.3) — вариационные принципы: брахистохрона, принцип Ферма, уравнение Эйлера–Лагранжа, принцип наименьшего действия, хаос.
- **Борьба с «магией»:** В §18.3 добавлено интуитивное объяснение функционала («функция от функций» + аналогия: $f'(x)=0$ ↔ Эйлер–Лагранж). Добавлен раздел «Почему прямая не оптимальна» перед формулами.
- **Перекрёстные ссылки:** Фалес → §8.2 (геометрия), фракталы → §8.4 (фрактальная геометрия), парабола → §2.5 (алгебра), закон сохранения энергии → §18.2.4.
- **Задачи:** Все три главы получили блоки задач трёх уровней (⭐/⭐⭐/⭐⭐⭐).
- **Мостики:** Каждая глава заканчивается блоком «Что дальше» со ссылкой на следующую.

---

## 4. Общий чек-лист глав (Прогресс вычитки)

- `[ ]` **Intro**
  - `[ ]` docs/chapters/intro/preface.md
- `[ ]` **Numbers (Числа)**
  - `[x]` docs/chapters/numbers/collatz.md
  - `[ ]` docs/chapters/numbers/complex.md
  - `[x]` docs/chapters/numbers/digits-vs-numbers.md
  - `[x]` docs/chapters/numbers/divisibility.md
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
  - `[ ]` docs/chapters/strategic-games/board-games.md
- `[ ]` **Information Theory (Теория информации)**
  - `[ ]` docs/chapters/information-theory/shannon.md
- `[ ]` **Physics (Физика)**
  - `[x]` docs/chapters/physics/kinematics.md
  - `[x]` docs/chapters/physics/dynamics.md
  - `[x]` docs/chapters/physics/mechanics.md
- `[ ]` **Problem Solving (Решение задач)**
  - `[ ]` docs/chapters/problem-solving/arithmetic-puzzles.md
  - `[ ]` docs/chapters/problem-solving/lateral-thinking.md
  - `[ ]` docs/chapters/problem-solving/logic-puzzles.md
  - `[ ]` docs/chapters/problem-solving/missing-data.md
  - `[x]` docs/chapters/problem-solving/weighing.md
