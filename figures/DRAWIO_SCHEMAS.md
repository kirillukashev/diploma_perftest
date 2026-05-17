# Схемы для диплома — шаблоны для draw.io и Python

Все схемы рисуются в draw.io или генерируются Python-скриптом.  
**Как вставить XML в draw.io:** открыть draw.io → `Extras → Edit Diagram` (Ctrl+Shift+X) → вставить XML → ОК.  
Экспортировать: `File → Export as → PNG`, масштаб 2x.

---

## Схема 1 — Верхнеуровневая архитектура системы (4 слоя)

**Файл:** `figures/architecture_layers.png`  
**Используется:** Глава 2, раздел 2.2.1 (Рисунок 2.1)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1200" dy="700" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- YAML Layer -->
    <mxCell id="2" value="&lt;b style='font-size:15px'&gt;YAML-конфигурация&lt;/b&gt;&lt;br&gt;&lt;font color='#aecbf5' style='font-size:12px'&gt;Декларативное описание сценария:&lt;br&gt;тип теста · паттерн нагрузки · параметры VU · URL&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1a3a5c;strokeColor=#3B82F6;strokeWidth=2;fontSize=12;verticalAlign=middle;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="100" y="40" width="640" height="80" as="geometry" />
    </mxCell>

    <!-- Arrow YAML → Core -->
    <mxCell id="3" value="&lt;i&gt;парсинг и валидация&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=11;strokeColor=#9CA3AF;" edge="1" source="2" target="4" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Core Layer -->
    <mxCell id="4" value="&lt;b style='font-size:15px'&gt;Ядро&lt;/b&gt;&lt;br&gt;&lt;font color='#a7f3d0' style='font-size:12px'&gt;Управление виртуальными пользователями (VU)&lt;br&gt;Генерация HTTP-запросов · Функциональные тесты · Агрегация результатов&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#064e3b;strokeColor=#10B981;strokeWidth=2;fontSize=12;verticalAlign=middle;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="100" y="180" width="640" height="90" as="geometry" />
    </mxCell>

    <!-- Arrow Core → Monitoring -->
    <mxCell id="5" value="&lt;i&gt;метрики каждые 5 с&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;strokeColor=#9CA3AF;exitX=0.25;exitY=1;exitDx=0;exitDy=0;" edge="1" source="4" target="6" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Arrow Core → Reporting -->
    <mxCell id="7" value="&lt;i&gt;по завершении теста&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;strokeColor=#9CA3AF;exitX=0.75;exitY=1;exitDx=0;exitDy=0;" edge="1" source="4" target="8" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Monitoring Layer -->
    <mxCell id="6" value="&lt;b style='font-size:15px'&gt;Мониторинг&lt;/b&gt;&lt;br&gt;&lt;font color='#fde68a' style='font-size:12px'&gt;Метрики в реальном времени&lt;br&gt;RPS · p50/p95/p99 · error rate&lt;br&gt;Prometheus → Grafana&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#451a03;strokeColor=#F59E0B;strokeWidth=2;fontSize=12;verticalAlign=middle;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="100" y="340" width="300" height="110" as="geometry" />
    </mxCell>

    <!-- Reporting Layer -->
    <mxCell id="8" value="&lt;b style='font-size:15px'&gt;Отчётность&lt;/b&gt;&lt;br&gt;&lt;font color='#fbcfe8' style='font-size:12px'&gt;HTML-отчёт по результатам&lt;br&gt;Графики · Гистограммы латентности&lt;br&gt;Сводная таблица метрик&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#4a0030;strokeColor=#EC4899;strokeWidth=2;fontSize=12;verticalAlign=middle;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="440" y="340" width="300" height="110" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Схема 2 — Поток выполнения (Execution Flow)

**Файл:** `figures/execution_flow.png`  
**Используется:** Глава 2, раздел 2.2.2 (Рисунок 2.2)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1300" dy="900" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- YAML file -->
    <mxCell id="10" value="&lt;b&gt;YAML-сценарий&lt;/b&gt;" style="shape=document;whiteSpace=wrap;html=1;fillColor=#DBEAFE;strokeColor=#3B82F6;fontSize=13;" vertex="1" parent="1">
      <mxGeometry x="200" y="20" width="160" height="60" as="geometry" />
    </mxCell>

    <!-- Arrow YAML → Orchestrator -->
    <mxCell id="11" value="&lt;i&gt;парсинг&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="10" target="12" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Orchestrator -->
    <mxCell id="12" value="&lt;b&gt;Оркестратор&lt;/b&gt;&lt;br&gt;Запуск тестов и бенчмарков" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#064e3b;strokeColor=#10B981;strokeWidth=2;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="195" y="130" width="170" height="60" as="geometry" />
    </mxCell>

    <!-- Arrow Orchestrator → Load Scheduler -->
    <mxCell id="13" value="&lt;i&gt;запуск&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="12" target="14" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Arrow Orchestrator → Terminal output -->
    <mxCell id="30" value="&lt;i&gt;фоновый поток&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;strokeColor=#9CA3AF;exitX=1;exitY=0.3;exitDx=0;exitDy=0;" edge="1" source="12" target="20" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Arrow Orchestrator → Metrics streaming -->
    <mxCell id="31" value="&lt;i&gt;фоновый поток&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;strokeColor=#9CA3AF;exitX=1;exitY=0.7;exitDx=0;exitDy=0;" edge="1" source="12" target="21" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Load Scheduler -->
    <mxCell id="14" value="&lt;b&gt;Планировщик нагрузки&lt;/b&gt;&lt;br&gt;Управление пулом VU" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#064e3b;strokeColor=#10B981;strokeWidth=2;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="180" y="250" width="200" height="60" as="geometry" />
    </mxCell>

    <!-- Arrow Load Scheduler → VU workers -->
    <mxCell id="15" value="&lt;i&gt;N потоков&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="14" target="16" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- VU workers -->
    <mxCell id="16" value="&lt;b&gt;VU-потоки × N&lt;/b&gt;&lt;br&gt;HTTP-запросы (pycurl)&lt;br&gt;измерение латентности" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#451a03;strokeColor=#F59E0B;strokeWidth=2;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="170" y="370" width="220" height="70" as="geometry" />
    </mxCell>

    <!-- Arrow VU workers → Buffer -->
    <mxCell id="17" value="&lt;i&gt;сброс буфера&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="16" target="18" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Buffer -->
    <mxCell id="18" value="&lt;b&gt;Буфер результатов&lt;/b&gt;&lt;br&gt;(latency, timestamp, ok)&lt;br&gt;разделяемый, потокобезопасный" style="shape=cylinder3;whiteSpace=wrap;html=1;fillColor=#1f2937;strokeColor=#6B7280;strokeWidth=2;fontSize=11;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="175" y="500" width="210" height="80" as="geometry" />
    </mxCell>

    <!-- Arrow Buffer → Report generator -->
    <mxCell id="19" value="&lt;i&gt;по завершении теста&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="18" target="25" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Report generator -->
    <mxCell id="25" value="&lt;b&gt;Генератор отчёта&lt;/b&gt;&lt;br&gt;→ report.html" style="shape=document;whiteSpace=wrap;html=1;fillColor=#4a0030;strokeColor=#EC4899;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="200" y="640" width="160" height="60" as="geometry" />
    </mxCell>

    <!-- Terminal output -->
    <mxCell id="20" value="&lt;b&gt;Вывод в терминал&lt;/b&gt;&lt;br&gt;RPS · ошибки&lt;br&gt;каждые 400 мс" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1e3a5c;strokeColor=#3B82F6;strokeWidth=2;fontSize=11;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="520" y="130" width="200" height="70" as="geometry" />
    </mxCell>

    <!-- Metrics streaming -->
    <mxCell id="21" value="&lt;b&gt;Стриминг метрик&lt;/b&gt;&lt;br&gt;скользящее окно 30 с&lt;br&gt;каждые 5 с" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1e3a5c;strokeColor=#3B82F6;strokeWidth=2;fontSize=11;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="520" y="250" width="200" height="70" as="geometry" />
    </mxCell>

    <!-- Arrow Buffer → Metrics streaming -->
    <mxCell id="32" value="&lt;i&gt;читает&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;strokeColor=#9CA3AF;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" edge="1" source="18" target="21" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Arrow Metrics streaming → Metrics store -->
    <mxCell id="22" value="&lt;i&gt;обновляет&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="21" target="23" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Metrics store -->
    <mxCell id="23" value="&lt;b&gt;Хранилище метрик&lt;/b&gt;&lt;br&gt;TTL 15 с&lt;br&gt;p50 · p95 · p99 · RPS" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1e3a5c;strokeColor=#3B82F6;strokeWidth=2;fontSize=11;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="520" y="380" width="200" height="70" as="geometry" />
    </mxCell>

    <!-- Arrow Metrics store → Prometheus -->
    <mxCell id="24" value="&lt;i&gt;/metrics endpoint&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="23" target="26" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Prometheus -->
    <mxCell id="26" value="&lt;b&gt;Prometheus&lt;/b&gt;&lt;br&gt;pull каждые 5 с" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1e3a5c;strokeColor=#3B82F6;strokeWidth=2;fontSize=11;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="520" y="510" width="200" height="60" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Схема 3 — Иерархия профилей нагрузки (UML)

**Файл:** `figures/load_profiles_hierarchy.png`  
**Используется:** Глава 2, раздел 2.4.1 (Рисунок 2.3)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1500" dy="600" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1400" pageHeight="600" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- Base Profile (abstract) -->
    <mxCell id="2" value="&lt;i&gt;&lt;b&gt;Базовый профиль нагрузки&lt;/b&gt;&lt;/i&gt;&lt;br&gt;&lt;font color='#374151' style='font-size:11px'&gt;Параметры: число VU, длительность&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#E5E7EB;strokeColor=#6B7280;strokeWidth=2;fontSize=13;arcSize=5;" vertex="1" parent="1">
      <mxGeometry x="490" y="30" width="320" height="60" as="geometry" />
    </mxCell>

    <!-- Inheritance lines from Base to each subclass -->
    <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c1" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c2" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c3" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c4" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c5" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=block;endFill=0;strokeColor=#6B7280;" edge="1" source="2" target="c6" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Constant -->
    <mxCell id="c1" value="&lt;b&gt;Constant&lt;/b&gt;&lt;br&gt;Постоянная нагрузка&lt;br&gt;Фиксированное число VU&lt;br&gt;&lt;font color='#1D4ED8' size='16'&gt;————&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#DBEAFE;strokeColor=#3B82F6;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="20" y="180" width="170" height="100" as="geometry" />
    </mxCell>

    <!-- Ramp-up -->
    <mxCell id="c2" value="&lt;b&gt;Ramp-up&lt;/b&gt;&lt;br&gt;Линейный рост&lt;br&gt;от min до max VU&lt;br&gt;&lt;font color='#15803D' size='14'&gt;╱‾‾‾&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#DCFCE7;strokeColor=#22C55E;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="220" y="180" width="170" height="100" as="geometry" />
    </mxCell>

    <!-- Spike -->
    <mxCell id="c3" value="&lt;b&gt;Spike&lt;/b&gt;&lt;br&gt;Кратковременный пик&lt;br&gt;база + всплеск VU&lt;br&gt;&lt;font color='#B45309' size='14'&gt;_╱‾╲_&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#FEF9C3;strokeColor=#EAB308;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="420" y="180" width="170" height="100" as="geometry" />
    </mxCell>

    <!-- Stepped -->
    <mxCell id="c4" value="&lt;b&gt;Stepped&lt;/b&gt;&lt;br&gt;Ступенчатый рост&lt;br&gt;шаг VU + выдержка&lt;br&gt;&lt;font color='#6D28D9' size='14'&gt;⌐⌐⌐⌐&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#EDE9FE;strokeColor=#7C3AED;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="620" y="180" width="170" height="100" as="geometry" />
    </mxCell>

    <!-- Stress -->
    <mxCell id="c5" value="&lt;b&gt;Stress&lt;/b&gt;&lt;br&gt;Нагрузка до отказа&lt;br&gt;рост + удержание пика&lt;br&gt;&lt;font color='#B91C1C' size='14'&gt;╱‾‾╲&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#FEE2E2;strokeColor=#EF4444;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="820" y="180" width="170" height="100" as="geometry" />
    </mxCell>

    <!-- Soak -->
    <mxCell id="c6" value="&lt;b&gt;Soak&lt;/b&gt;&lt;br&gt;Длительная нагрузка&lt;br&gt;выявление деградации&lt;br&gt;&lt;font color='#0E7490' size='14'&gt;──────&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#CFFAFE;strokeColor=#06B6D4;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="1020" y="180" width="170" height="100" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Схема 4 — Пайплайн мониторинга

**Файл:** `figures/monitoring_pipeline.png`  
**Используется:** Глава 2, раздел 2.5.1 (Рисунок 2.4)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1300" dy="500" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1200" pageHeight="500" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- perftest process swimlane -->
    <mxCell id="2" value="&lt;b&gt;Система нагрузочного тестирования&lt;/b&gt;" style="swimlane;fillColor=#064e3b;strokeColor=#10B981;strokeWidth=2;fontSize=13;startSize=30;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="30" y="80" width="370" height="220" as="geometry" />
    </mxCell>

    <!-- VU workers inside -->
    <mxCell id="3" value="&lt;b&gt;VU-потоки × N&lt;/b&gt;&lt;br&gt;HTTP-запросы к SUT" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#451a03;strokeColor=#F59E0B;fontSize=11;fontColor=#ffffff;" vertex="1" parent="2">
      <mxGeometry x="20" y="50" width="160" height="60" as="geometry" />
    </mxCell>

    <!-- Metrics aggregation inside -->
    <mxCell id="4" value="&lt;b&gt;Агрегация метрик&lt;/b&gt;&lt;br&gt;каждые 5 с&lt;br&gt;скользящее окно 30 с" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1e3a5c;strokeColor=#3B82F6;fontSize=11;fontColor=#ffffff;" vertex="1" parent="2">
      <mxGeometry x="20" y="130" width="160" height="70" as="geometry" />
    </mxCell>

    <!-- Metrics store inside -->
    <mxCell id="5" value="&lt;b&gt;Хранилище метрик&lt;/b&gt;&lt;br&gt;TTL 15 с&lt;br&gt;p50 · p95 · p99 · RPS" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#451a03;strokeColor=#F59E0B;fontSize=11;fontColor=#ffffff;" vertex="1" parent="2">
      <mxGeometry x="195" y="90" width="155" height="80" as="geometry" />
    </mxCell>

    <!-- arrows inside swimlane -->
    <mxCell id="e1" value="&lt;i&gt;результаты&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=9;" edge="1" source="3" target="4" parent="2">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>
    <mxCell id="e2" value="&lt;i&gt;обновляет&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=9;" edge="1" source="4" target="5" parent="2">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- HTTP /metrics endpoint -->
    <mxCell id="6" value="&lt;b&gt;Endpoint /metrics&lt;/b&gt;&lt;br&gt;&lt;font color='#6B7280' style='font-size:10px'&gt;Формат Prometheus&lt;br&gt;RPS · p50 · p95 · p99&lt;br&gt;error rate&lt;/font&gt;" style="shape=document;whiteSpace=wrap;html=1;fillColor=#F9FAFB;strokeColor=#6B7280;strokeWidth=2;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="450" y="110" width="185" height="110" as="geometry" />
    </mxCell>

    <!-- Arrow MetricsStore → /metrics -->
    <mxCell id="e3" value="&lt;i&gt;GET&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" edge="1" source="5" target="6" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Prometheus -->
    <mxCell id="7" value="&lt;b&gt;Prometheus&lt;/b&gt;&lt;br&gt;порт 9090&lt;br&gt;scrape каждые 5 с" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#7f1d1d;strokeColor=#EF4444;strokeWidth=2;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="690" y="115" width="160" height="80" as="geometry" />
    </mxCell>

    <!-- Arrow /metrics → Prometheus -->
    <mxCell id="e4" value="&lt;i&gt;scrape&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="6" target="7" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Grafana -->
    <mxCell id="8" value="&lt;b&gt;Grafana&lt;/b&gt;&lt;br&gt;порт 3000&lt;br&gt;обновление 5 с&lt;br&gt;Дашборд (автопровизия)" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#431407;strokeColor=#F97316;strokeWidth=2;fontSize=12;fontColor=#ffffff;" vertex="1" parent="1">
      <mxGeometry x="910" y="100" width="185" height="110" as="geometry" />
    </mxCell>

    <!-- Arrow Prometheus → Grafana -->
    <mxCell id="e5" value="&lt;i&gt;PromQL&lt;/i&gt;" style="edgeStyle=orthogonalEdgeStyle;html=1;fontSize=10;" edge="1" source="7" target="8" parent="1">
      <mxGeometry relative="1" as="geometry" />
    </mxCell>

    <!-- Docker Compose note -->
    <mxCell id="9" value="Запуск: docker compose up" style="text;html=1;align=center;fontStyle=1;fontSize=11;fillColor=#1f2937;strokeColor=#4B5563;rounded=1;fontColor=#9CA3AF;" vertex="1" parent="1">
      <mxGeometry x="720" y="250" width="360" height="30" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Схема 5 — Сравнение кумулятивных vs скользящих перцентилей

**Файл:** `figures/sliding_window_comparison.png`  
**Используется:** Глава 2, раздел 2.5.2 (Рисунок 2.5)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1400" dy="600" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1100" pageHeight="430" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- ===== ЛЕВАЯ ПАНЕЛЬ: Кумулятивный расчёт ===== -->
    <mxCell id="p1bg" value="" style="rounded=1;fillColor=#FFF7F7;strokeColor=#D1D5DB;strokeWidth=1;" vertex="1" parent="1">
      <mxGeometry x="10" y="10" width="470" height="370" as="geometry" />
    </mxCell>
    <mxCell id="p1title" value="&lt;b&gt;Кумулятивный расчёт&lt;/b&gt;" style="text;html=1;align=center;fontSize=14;fontColor=#374151;" vertex="1" parent="1">
      <mxGeometry x="10" y="15" width="470" height="28" as="geometry" />
    </mxCell>

    <!-- Spike zone left (t=40..70 → x=183..248 при chart_x=70..450) -->
    <mxCell id="p1spike" value="&lt;font color='#92400E'&gt;spike&lt;br&gt;40–70 с&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;fillColor=#FEF3C7;strokeColor=#F59E0B;strokeWidth=1;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="183" y="55" width="65" height="282" as="geometry" />
    </mxCell>

    <!-- Axes left -->
    <mxCell id="p1yax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="338" as="sourcePoint" />
        <mxPoint x="70" y="55" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p1xax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="338" as="sourcePoint" />
        <mxPoint x="455" y="338" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p1ylabel" value="Латентность, мс" style="text;html=1;align=center;fontSize=10;fontColor=#6B7280;rotation=-90;" vertex="1" parent="1">
      <mxGeometry x="18" y="195" width="120" height="18" as="geometry" />
    </mxCell>
    <mxCell id="p1xlabel" value="Время теста, с →" style="text;html=1;align=center;fontSize=10;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="220" y="348" width="150" height="18" as="geometry" />
    </mxCell>

    <!-- Cumulative p50 (green): rises slowly, ends near middle -->
    <mxCell id="p1p50" value="" style="endArrow=none;strokeColor=#22C55E;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="318" as="sourcePoint" />
        <mxPoint x="453" y="304" as="targetPoint" />
        <Array as="points">
          <mxPoint x="183" y="318" />
          <mxPoint x="216" y="290" />
          <mxPoint x="248" y="298" />
          <mxPoint x="330" y="310" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Cumulative p95 (orange): spikes, slowly recovers -->
    <mxCell id="p1p95" value="" style="endArrow=none;strokeColor=#F97316;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="290" as="sourcePoint" />
        <mxPoint x="453" y="277" as="targetPoint" />
        <Array as="points">
          <mxPoint x="183" y="290" />
          <mxPoint x="216" y="215" />
          <mxPoint x="248" y="230" />
          <mxPoint x="330" y="258" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Cumulative p99 (red): big spike, very slow recovery, converges toward p95 -->
    <mxCell id="p1p99" value="" style="endArrow=none;strokeColor=#EF4444;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="263" as="sourcePoint" />
        <mxPoint x="453" y="249" as="targetPoint" />
        <Array as="points">
          <mxPoint x="183" y="263" />
          <mxPoint x="210" y="105" />
          <mxPoint x="248" y="135" />
          <mxPoint x="330" y="193" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Annotation: lines converge -->
    <mxCell id="p1ann" value="&lt;font color='#6B7280'&gt;p50/p95/p99&lt;br&gt;сходятся — история&lt;br&gt;размывает эффект&lt;/font&gt;" style="text;html=1;align=left;fontSize=9;" vertex="1" parent="1">
      <mxGeometry x="360" y="215" width="115" height="52" as="geometry" />
    </mxCell>
    <mxCell id="p1annarr" value="" style="endArrow=open;endFill=0;strokeColor=#9CA3AF;strokeWidth=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="365" y="242" as="sourcePoint" />
        <mxPoint x="453" y="277" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- ===== ПРАВАЯ ПАНЕЛЬ: Скользящее окно 30с ===== -->
    <mxCell id="p2bg" value="" style="rounded=1;fillColor=#F0FDF4;strokeColor=#D1D5DB;strokeWidth=1;" vertex="1" parent="1">
      <mxGeometry x="600" y="10" width="470" height="370" as="geometry" />
    </mxCell>
    <mxCell id="p2title" value="&lt;b&gt;Скользящее окно 30 с&lt;/b&gt;" style="text;html=1;align=center;fontSize=14;fontColor=#374151;" vertex="1" parent="1">
      <mxGeometry x="600" y="15" width="470" height="28" as="geometry" />
    </mxCell>

    <!-- Spike zone right (offset +590) -->
    <mxCell id="p2spike" value="&lt;font color='#92400E'&gt;spike&lt;br&gt;40–70 с&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;fillColor=#FEF3C7;strokeColor=#F59E0B;strokeWidth=1;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="773" y="55" width="65" height="282" as="geometry" />
    </mxCell>

    <!-- Axes right -->
    <mxCell id="p2yax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="660" y="338" as="sourcePoint" />
        <mxPoint x="660" y="55" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p2xax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="660" y="338" as="sourcePoint" />
        <mxPoint x="1045" y="338" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p2ylabel" value="Латентность, мс" style="text;html=1;align=center;fontSize=10;fontColor=#6B7280;rotation=-90;" vertex="1" parent="1">
      <mxGeometry x="608" y="195" width="120" height="18" as="geometry" />
    </mxCell>
    <mxCell id="p2xlabel" value="Время теста, с →" style="text;html=1;align=center;fontSize=10;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="810" y="348" width="150" height="18" as="geometry" />
    </mxCell>

    <!-- Sliding p50 (green): stays flat, tiny bump during spike -->
    <mxCell id="p2p50" value="" style="endArrow=none;strokeColor=#22C55E;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="660" y="318" as="sourcePoint" />
        <mxPoint x="1043" y="318" as="targetPoint" />
        <Array as="points">
          <mxPoint x="773" y="318" />
          <mxPoint x="806" y="295" />
          <mxPoint x="840" y="318" />
          <mxPoint x="890" y="318" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Sliding p95 (orange): spikes and recovers fast -->
    <mxCell id="p2p95" value="" style="endArrow=none;strokeColor=#F97316;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="660" y="290" as="sourcePoint" />
        <mxPoint x="1043" y="290" as="targetPoint" />
        <Array as="points">
          <mxPoint x="773" y="290" />
          <mxPoint x="806" y="183" />
          <mxPoint x="840" y="173" />
          <mxPoint x="862" y="242" />
          <mxPoint x="892" y="290" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Sliding p99 (red): BIG spike then FAST full recovery — key visual! -->
    <mxCell id="p2p99" value="" style="endArrow=none;strokeColor=#EF4444;strokeWidth=2.5;html=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="660" y="263" as="sourcePoint" />
        <mxPoint x="1043" y="263" as="targetPoint" />
        <Array as="points">
          <mxPoint x="773" y="263" />
          <mxPoint x="800" y="85" />
          <mxPoint x="840" y="75" />
          <mxPoint x="862" y="163" />
          <mxPoint x="887" y="252" />
          <mxPoint x="912" y="263" />
        </Array>
      </mxGeometry>
    </mxCell>

    <!-- Annotation: fast recovery -->
    <mxCell id="p2ann" value="&lt;b&gt;&lt;font color='#EF4444'&gt;p99 резко растёт&lt;br&gt;и быстро падает!&lt;/font&gt;&lt;/b&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="840" y="82" width="130" height="38" as="geometry" />
    </mxCell>
    <mxCell id="p2annarr" value="" style="endArrow=open;endFill=0;strokeColor=#EF4444;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="862" y="120" as="sourcePoint" />
        <mxPoint x="845" y="100" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- Recovery annotation -->
    <mxCell id="p2rec" value="&lt;font color='#16A34A'&gt;✓ вернулся&lt;br&gt;к baseline&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="942" y="233" width="95" height="36" as="geometry" />
    </mxCell>
    <mxCell id="p2recarr" value="" style="endArrow=open;endFill=0;strokeColor=#16A34A;strokeWidth=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="952" y="252" as="sourcePoint" />
        <mxPoint x="1028" y="263" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- ===== ЛЕГЕНДА ===== -->
    <mxCell id="leg50b" value="" style="fillColor=#22C55E;strokeColor=none;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="320" y="392" width="28" height="8" as="geometry" />
    </mxCell>
    <mxCell id="leg50t" value="p50" style="text;html=1;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="352" y="386" width="35" height="20" as="geometry" />
    </mxCell>
    <mxCell id="leg95b" value="" style="fillColor=#F97316;strokeColor=none;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="398" y="392" width="28" height="8" as="geometry" />
    </mxCell>
    <mxCell id="leg95t" value="p95" style="text;html=1;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="430" y="386" width="35" height="20" as="geometry" />
    </mxCell>
    <mxCell id="leg99b" value="" style="fillColor=#EF4444;strokeColor=none;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="476" y="392" width="28" height="8" as="geometry" />
    </mxCell>
    <mxCell id="leg99t" value="p99" style="text;html=1;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="508" y="386" width="35" height="20" as="geometry" />
    </mxCell>
    <mxCell id="legspb" value="" style="fillColor=#FEF3C7;strokeColor=#F59E0B;rounded=1;" vertex="1" parent="1">
      <mxGeometry x="554" y="388" width="14" height="14" as="geometry" />
    </mxCell>
    <mxCell id="legspt" value="spike-зона" style="text;html=1;fontSize=11;" vertex="1" parent="1">
      <mxGeometry x="572" y="386" width="80" height="20" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Схема 6 — Точка насыщения (Saturation Point)

**Файл:** `figures/saturation_point.png`  
**Используется:** Глава 3, раздел 3.4.2 (Рисунок 3.4)  
**Данные:** реальные результаты из HTML-отчёта (таблица 3.3 диплома)

<details>
<summary>▶ Draw.io XML — вставить через Extras → Edit Diagram</summary>

```xml
<mxGraphModel dx="1200" dy="700" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="900" pageHeight="630" math="0" shadow="0">
  <root>
    <mxCell id="0" />
    <mxCell id="1" parent="0" />

    <!-- Заголовок -->
    <mxCell id="title" value="&lt;b&gt;Пропускная способность и хвостовая латентность Django dev-сервера&lt;br&gt;по шести профилям нагрузки (реальные данные)&lt;/b&gt;" style="text;html=1;align=center;fontSize=13;" vertex="1" parent="1">
      <mxGeometry x="50" y="8" width="800" height="38" as="geometry" />
    </mxCell>

    <!-- ===== ВЕРХНИЙ ГРАФИК: RPS ===== -->
    <mxCell id="rps_yl" value="RPS, req/s" style="text;html=1;align=center;fontSize=11;fontStyle=1;rotation=-90;" vertex="1" parent="1">
      <mxGeometry x="5" y="130" width="80" height="18" as="geometry" />
    </mxCell>
    <mxCell id="y_1650" value="1650" style="text;html=1;align=right;fontSize=9;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="34" y="53" width="32" height="14" as="geometry" />
    </mxCell>
    <mxCell id="y_1600" value="1600" style="text;html=1;align=right;fontSize=9;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="34" y="103" width="32" height="14" as="geometry" />
    </mxCell>
    <mxCell id="y_1500" value="1500" style="text;html=1;align=right;fontSize=9;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="34" y="233" width="32" height="14" as="geometry" />
    </mxCell>
    <!-- Линия насыщения ~1600 -->
    <mxCell id="rps_sat" value="" style="endArrow=none;strokeColor=#9CA3AF;strokeWidth=1;dashed=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="110" as="sourcePoint" />
        <mxPoint x="738" y="110" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="rps_sat_lbl" value="~ 1600 req/s" style="text;html=1;align=left;fontSize=9;fontColor=#9CA3AF;" vertex="1" parent="1">
      <mxGeometry x="742" y="104" width="80" height="14" as="geometry" />
    </mxCell>
    <!-- X/Y оси RPS -->
    <mxCell id="rps_xax" value="" style="endArrow=none;strokeColor=#6B7280;strokeWidth=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="247" as="sourcePoint" />
        <mxPoint x="738" y="247" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="rps_yax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="247" as="sourcePoint" />
        <mxPoint x="70" y="50" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- RPS BARS (y_base=247, chart_h=190, scale=(rps-1500)/150*190) -->
    <!-- Soak 1609.85 → h=138 → y=109 -->
    <mxCell id="b1r" value="1610" style="fillColor=#06B6D4;strokeColor=#0891B2;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="75" y="109" width="90" height="138" as="geometry" />
    </mxCell>
    <!-- Constant 1599.81 → h=126 → y=121 -->
    <mxCell id="b2r" value="1600" style="fillColor=#3B82F6;strokeColor=#2563EB;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="185" y="121" width="90" height="126" as="geometry" />
    </mxCell>
    <!-- Ramp-up 1581.57 → h=104 → y=143 -->
    <mxCell id="b3r" value="1582" style="fillColor=#22C55E;strokeColor=#16A34A;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="295" y="143" width="90" height="104" as="geometry" />
    </mxCell>
    <!-- Spike 1636.85 → h=172 → y=75 -->
    <mxCell id="b4r" value="1637" style="fillColor=#EAB308;strokeColor=#CA8A04;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="405" y="75" width="90" height="172" as="geometry" />
    </mxCell>
    <!-- Stepped 1597.46 → h=122 → y=125 -->
    <mxCell id="b5r" value="1597" style="fillColor=#7C3AED;strokeColor=#6D28D9;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="515" y="125" width="90" height="122" as="geometry" />
    </mxCell>
    <!-- Stress 1585.23 → h=108 → y=139 -->
    <mxCell id="b6r" value="1585" style="fillColor=#EF4444;strokeColor=#DC2626;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="625" y="139" width="90" height="108" as="geometry" />
    </mxCell>

    <!-- РАЗДЕЛИТЕЛЬ -->
    <mxCell id="div" value="" style="endArrow=none;strokeColor=#E5E7EB;strokeWidth=1;dashed=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="30" y="282" as="sourcePoint" />
        <mxPoint x="850" y="282" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- ===== НИЖНИЙ ГРАФИК: p99 ===== -->
    <mxCell id="p99_yl" value="p99, мс" style="text;html=1;align=center;fontSize=11;fontStyle=1;rotation=-90;" vertex="1" parent="1">
      <mxGeometry x="5" y="420" width="80" height="18" as="geometry" />
    </mxCell>
    <mxCell id="p99_y75" value="75 мс" style="text;html=1;align=right;fontSize=9;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="34" y="302" width="32" height="14" as="geometry" />
    </mxCell>
    <mxCell id="p99_y0" value="0" style="text;html=1;align=right;fontSize=9;fontColor=#6B7280;" vertex="1" parent="1">
      <mxGeometry x="34" y="558" width="32" height="14" as="geometry" />
    </mxCell>
    <!-- Baseline 7.1 мс -->
    <mxCell id="p99_base" value="" style="endArrow=none;strokeColor=#3B82F6;strokeWidth=1;dashed=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="545" as="sourcePoint" />
        <mxPoint x="738" y="545" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p99_base_lbl" value="baseline p99 = 7.1 мс" style="text;html=1;align=left;fontSize=9;fontColor=#3B82F6;" vertex="1" parent="1">
      <mxGeometry x="742" y="539" width="130" height="14" as="geometry" />
    </mxCell>
    <!-- X/Y оси p99 -->
    <mxCell id="p99_xax" value="" style="endArrow=none;strokeColor=#6B7280;strokeWidth=1;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="572" as="sourcePoint" />
        <mxPoint x="738" y="572" as="targetPoint" />
      </mxGeometry>
    </mxCell>
    <mxCell id="p99_yax" value="" style="endArrow=open;endFill=0;strokeColor=#6B7280;strokeWidth=1.5;" edge="1" parent="1">
      <mxGeometry relative="1" as="geometry">
        <mxPoint x="70" y="572" as="sourcePoint" />
        <mxPoint x="70" y="300" as="targetPoint" />
      </mxGeometry>
    </mxCell>

    <!-- P99 BARS (y_base=572, chart_h=265, scale=p99/75*265) -->
    <!-- Soak 6.022 → h=21 → y=551 -->
    <mxCell id="b1p" value="6.0" style="fillColor=#06B6D4;strokeColor=#0891B2;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="75" y="551" width="90" height="21" as="geometry" />
    </mxCell>
    <!-- Constant 7.053 → h=25 → y=547 -->
    <mxCell id="b2p" value="7.1" style="fillColor=#3B82F6;strokeColor=#2563EB;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="185" y="547" width="90" height="25" as="geometry" />
    </mxCell>
    <!-- Ramp-up 9.313 → h=33 → y=539 -->
    <mxCell id="b3p" value="9.3" style="fillColor=#22C55E;strokeColor=#16A34A;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="295" y="539" width="90" height="33" as="geometry" />
    </mxCell>
    <!-- Spike 38.586 → h=136 → y=436 -->
    <mxCell id="b4p" value="38.6 мс" style="fillColor=#EAB308;strokeColor=#CA8A04;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="405" y="436" width="90" height="136" as="geometry" />
    </mxCell>
    <!-- Stepped 46.807 → h=165 → y=407 -->
    <mxCell id="b5p" value="46.8 мс" style="fillColor=#7C3AED;strokeColor=#6D28D9;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="515" y="407" width="90" height="165" as="geometry" />
    </mxCell>
    <!-- Stress 69.044 → h=244 → y=328 -->
    <mxCell id="b6p" value="69.0 мс" style="fillColor=#EF4444;strokeColor=#DC2626;fontSize=10;fontColor=#fff;fontStyle=1;verticalAlign=top;" vertex="1" parent="1">
      <mxGeometry x="625" y="328" width="90" height="244" as="geometry" />
    </mxCell>
    <!-- Аннотация ×9.8 -->
    <mxCell id="ann98" value="&lt;b&gt;×9.8 от baseline!&lt;/b&gt;" style="text;html=1;align=center;fontSize=10;fontColor=#EF4444;" vertex="1" parent="1">
      <mxGeometry x="617" y="308" width="108" height="18" as="geometry" />
    </mxCell>

    <!-- X labels -->
    <mxCell id="xl1" value="Soak&lt;br&gt;&lt;font color='#6B7280'&gt;4 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="75" y="576" width="90" height="28" as="geometry" />
    </mxCell>
    <mxCell id="xl2" value="Constant&lt;br&gt;&lt;font color='#6B7280'&gt;5 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="185" y="576" width="90" height="28" as="geometry" />
    </mxCell>
    <mxCell id="xl3" value="Ramp-up&lt;br&gt;&lt;font color='#6B7280'&gt;→10 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="295" y="576" width="90" height="28" as="geometry" />
    </mxCell>
    <mxCell id="xl4" value="Spike&lt;br&gt;&lt;font color='#6B7280'&gt;peak 15 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="405" y="576" width="90" height="28" as="geometry" />
    </mxCell>
    <mxCell id="xl5" value="Stepped&lt;br&gt;&lt;font color='#6B7280'&gt;→20 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="515" y="576" width="90" height="28" as="geometry" />
    </mxCell>
    <mxCell id="xl6" value="Stress&lt;br&gt;&lt;font color='#6B7280'&gt;→20 VU&lt;/font&gt;" style="text;html=1;align=center;fontSize=10;" vertex="1" parent="1">
      <mxGeometry x="625" y="576" width="90" height="28" as="geometry" />
    </mxCell>

  </root>
</mxGraphModel>
```

</details>

---

## Уже есть (не нужно рисовать)

| Файл | Содержание | Используется |
|---|---|---|
| `figures/vu_threading_diagram.png` | VU-потоки → буфер результатов → агрегация метрик | Глава 2, §2.3 |
| `figures/grafana_dashboard_all_profiles.png` | Grafana дашборд (реальный скрин) | Глава 3, §3.4, Рисунок 3.1 |
| `figures/html_report_part1.png` | HTML-отчёт часть 1: Summary + Constant + Ramp-up + Spike | Глава 3, §3.4, Рисунок 3.2 |
| `figures/html_report_part2.png` | HTML-отчёт часть 2: Stepped + Stress + Soak + таблица | Глава 3, §3.4, Рисунок 3.3 |

---

## Приоритет создания

| Приоритет | Схема | Почему важна |
|---|---|---|
| Обязательно | Схема 1 (архитектура 4 слоя) | Ключевая схема для Главы 2 |
| Обязательно | Схема 6 (saturation_point) | Главный экспериментальный результат |
| Желательно | Схема 5 (sliding_window) | Иллюстрирует научную новизну |
| Желательно | Схема 3 (иерархия профилей) | Архитектурное решение |
| Опционально | Схема 2 (поток выполнения) | Детализация |
| Опционально | Схема 4 (пайплайн мониторинга) | Дублирует текст |
