# ESU 公式设字典：从公式显相到公式 Being 的归一化表达框架

**版本**：v0.1 Concept Note  
**状态**：概念冻结，暂不工程化  
**主题**：数学公式归一字典 / Formula Persona Dictionary / ESU Formula Being  
**关键词**：ESU、公式设、Formula Being、LaTeX、显相、公式字典、BOR、Being Ontology、view、renderer、semantic formula

---

## 摘要

现代数学写作长期依赖 LaTeX、MathJax、Word Equation、MathML 等显相工具。这些工具很好地解决了公式如何显示的问题，却没有真正解决公式作为一个可命名、可调用、可复用的结构存在体的问题。大量高频公式，例如 \(re^{i\theta}\)、\(a+ib\)、\(r(t)e^{i(\omega t+\phi_0)}\)、抛物线公式、相位公式、导数、积分、矩阵等，虽然具有稳定结构、稳定类属和稳定意义，但在实际写作中仍然被反复手工输入或复制粘贴。

本文提出一种基于 BOR Being Ontology 的公式归一字典框架：将数学公式视为一种 structural presence / 结构显相存在体，并以 \(ESU=(E,s,u)\) 定义其本质公式设 / formula persona。公式的显相部分则由 \((\phi,r,c)\) 或更准确地由 `view_c(φ,r)` 决定。由此，公式不再只是 LaTeX 字符串，而是具有身份、结构、类属、意义和方向的 formula being。

本文同时指出，ESU 不应试图替代 LaTeX，也不应要求 LaTeX 原生读取 ESU。可行路径是：ESU 作为语义源层，插件或 exporter 将 ESU 字典编译为 LaTeX、Word、Obsidian、SVG、Python 等现有工具能够理解的显相格式。然而，由于工程量、品类定义复杂度和用户迁移成本较高，本文最终建议将该方向暂时封存为概念成果，而不立即启动完整开源工程。

---

## 1. 问题背景：公式写作的重复显相困境

现代数学公式写作有一个长期存在但很少被正面命名的问题：

> 许多公式已经具有稳定结构和稳定意义，却没有成为一个可调用的公式 being。

例如：

\[
re^{i\theta}
\]

这个表达式在复数、相位、波动、旋转、信号、傅里叶分析等场合反复出现。人们真正关心的常常只是其中的 \(r\) 和 \(\theta\)，但每次仍然必须完整写出：

```latex
re^{i\theta}
```

或者复制粘贴已有公式。

复制粘贴看似解决了重复输入问题，但它只是在复制一个显相结果，而不是在调用一个公式本体。换言之：

\[
\boxed{\text{copy 解决的是重复输入；ESU 解决的是本体调用。}}
\]

当前公式系统的死局在于：

```text
公式有结构 s；
公式有类属 u；
公式有稳定意义和方向；
但没有被赋予 being-ID。
```

因此，每一次使用都被迫回到底层显相：人工输入、复制、修改、重新排版。

---

## 2. LaTeX 的价值与边界

LaTeX 是非常优秀的数学显相工具。它解决了：

```text
分式如何排版；
上下标如何显示；
矩阵如何排列；
公式如何 inline 或 display；
符号如何美观显现。
```

但 LaTeX 本质上处理的是符号表象，而不是公式本体。

例如：

\[
y=ax^2+b
\]

在 LaTeX 中是：

```latex
y=ax^2+b
```

LaTeX 能够知道 `x^2` 是上标结构，知道 `a`、`x`、`b`、`y` 是数学字母，但它并不天然知道：

```text
u = parabola
s = quadratic / axis-symmetry / vertex-focus-directrix structure
a = curvature / opening parameter
x = phase input variable
b = vertical shift parameter
y = output manifestation
orientation = input phase → output manifestation
```

因此：

\[
\boxed{\text{LaTeX defines formula appearance; ESU defines formula being.}}
\]

中文可表述为：

\[
\boxed{\text{LaTeX 定义公式显相；ESU 定义公式本体。}}
\]

LaTeX 是“衣服”，ESU 是“公式灵魂”。二者不是竞争关系，而是层级不同。

---

## 3. 公式 Being 的六基组

在 BOR 本体框架中，公式可以视为一种 structural presence / 结构存在体。其完整六基组可写为：

\[
\mathcal F_{\text{being}}
=
\mathcal F(E,s,u,r,\phi,c)
\]

其中：

| 基 | 含义 | 在公式 being 中的对应 |
|---|---|---|
| \(E\) | Essence / 身份权柄 | 公式 ID、token 权柄、尺度、方向、占位、orientation |
| \(s\) | Structure / 结构基 | 字符集、结构骨架、subclass、不变量、上下位置关系、组合方式 |
| \(u\) | Class / 类属基 | 数学公式、物理公式、化学公式、parabola、phase、wave 等 |
| \(r\) | Layout / 显相布局 | inline、display、block、图显、列显、矩阵显相 |
| \(\phi\) | State / 相态参数 | 当前实例参数，如 \(r,\theta\)、\(a,b\)、\(h,k,p\) |
| \(c\) | View / Render context | LaTeX、Word、SVG、Python、Cartesian、polar、complex 等显相视角 |

进一步讨论后，本文将六基拆成两层：

\[
\boxed{
\mathcal F_{\text{being}}
=
\left[
\underbrace{E,s,u}_{\text{ESU：公式设 / 类本质}}
\mid
\underbrace{\phi,r,c}_{\text{显相个体化条件}}
\right]
}
\]

其中：

\[
\boxed{ESU=(E,s,u)}
\]

是数学公式 being 的本质公式设 / formula persona。

---

## 4. ESU：公式的本质人设 / 公式设

对于数学公式这类 being，\(E,s,u\) 构成其类本质。

\[
\boxed{
ESU_{\mathcal F}=(E,s,u)
}
\]

ESU 决定：

```text
这个公式是谁；
它属于哪一类；
它的结构骨架是什么；
它的 token 由谁授权；
它的 meaning 与 orientation 是什么；
它如何被复用。
```

因此，ESU 不是 LaTeX 命令，不是字符串模板，也不是图片。ESU 是公式的 formula persona / 公式设。

### 4.1 \(E\)：身份、token 权柄与方向

在 ESU 中，字符集并不是由 LaTeX 定义的，而是由 \(E\) 确立。

例如在：

\[
re^{i\theta}
\]

中，\(r\)、\(e\)、\(i\)、\(\theta\) 并非只是排版字符，而是具有角色意义：

```text
r = radius / magnitude
θ = phase angle
i = orthogonal rotation unit
e^{iθ} = unit phase rotation
```

在 ESU 中：

\[
\boxed{
\Sigma_{\mathcal F} \subset E_{\mathcal F}
}
\]

也就是说，公式 token 集合属于该公式 being 的身份定义，而不是属于某一种显相语言。

### 4.2 \(s\)：结构骨架与 subclass

\(s\) 定义公式的结构不变量，而不是每次显相的具体数值。

例如 \(re^{i\theta}\) 的结构为：

\[
s = r \cdot e^{i\theta}
\]

其中有稳定的乘法结构、指数结构、相位结构、复数旋转结构。

### 4.3 \(u\)：class / 物种

\(u\) 定义公式 being 的类属。例如：

```text
u = complex polar form
u = phase vector
u = parabola
u = derivative
u = wave
u = matrix
```

本文强调：\(u\) 基不应试图重新创造全数学分类，而应先做 **class recognition / 类识别**。即承认数学传统中已经稳定存在的 class，然后为高复用 class 建立 ESU。

---

## 5. φ、r、c：显相个体化条件

早期表述中曾说：

```text
φ, r, c 不负责本质。
```

后续修正为：

\[
\boxed{
\phi,r,c \text{ 不负责类本质，但负责当前个体显相的次要本质。}
}
\]

也就是说：

\[
\boxed{
ESU=(E,s,u) \Rightarrow \text{类本质 / formula persona}
}
\]

\[
\boxed{
(\phi,r,c) \Rightarrow \text{当前显相个体化条件}
}
\]

\(\phi,r,c\) 决定当前这个公式实例与其他公式实例不同的地方。它们不改变公式的类本质，但决定当前公式如何显相、以何种 view 出现、处于何种状态。

---

## 6. c-view：显相层的关键解耦

最关键的结构突破是将 \(c\) 从“工具介质”改写为 **view selector / 显相视角选择器**。

原来容易写成：

\[
(E,s,u,r,\phi,c)
\]

这会让 \(c\) 与本体混在一起，并造成接口负担。更好的写法是：

\[
\boxed{
\mathrm{FormulaBeing}
=
\mathrm{ESU}
+
\mathrm{view}_c(\phi,r)
}
\]

也就是：

```text
ESU    = 本体公式设，不变
c-view = 从哪个视角观察/解释
φ,r    = 在该视角下的当前状态与布局
```

可以写成：

\[
\boxed{
\mathrm{Manifest}
=
\mathrm{view}_c(ESU;\phi,r)
}
\]

例如：

```text
parabola.view(cartesian)
parabola.view(polar)
ComplexPhase.view(polar)
ComplexPhase.view(rectangular)
ComplexPhase.view(time)
```

这里 `view(...)` 不定义新的结构语言，它只是选择观察镜头。

---

## 7. 案例一：\(re^{i\theta}\) 作为 ComplexPhase Being

### 7.1 ESU 定义

\(re^{i\theta}\) 可以定义为一个 stable formula being：

```text
ID:
  math.complex.phase.polar

ESU:
  E:
    token authority:
      r: magnitude / radius
      θ: phase angle
      i: orthogonal rotation unit
      e: exponential phase carrier
    orientation:
      radial magnitude + phase angle → complex point

  s:
    structure:
      radius × unit phase rotation
      r · exp(iθ)

  u:
    class:
      complex polar phase
    parent:
      complex number / phase expression
```

### 7.2 不同 view 下的显相

同一个 ESU 可以在不同 view 下显相为：

| view | 显相 |
|---|---|
| polar view | \(re^{i\theta}\) |
| Euler view | \(r(\cos\theta+i\sin\theta)\) |
| rectangular view | \(a+ib\) |
| time view | \(r(t)e^{i(\omega t+\phi_0)}\) |
| wave view | \(Ae^{i(kx-\omega t+\phi_0)}\) |
| phasor view | \(R\angle\theta\) |

其中：

\[
a=r\cos\theta
\]

\[
b=r\sin\theta
\]

所以：

\[
re^{i\theta}=a+ib
\]

关键是：

\[
\boxed{
a+ib \text{ 不是另一个 being，而是 } re^{i\theta} \text{ 的 rectangular view。}
}
\]

而：

\[
r(t)e^{i(\omega t+\phi_0)}
\]

则是同一个 ComplexPhase being 在 time-domain / oscillation view 下的显相。

因此：

\[
\boxed{
\text{view 改变显相律，不改变 ESU 本质。}
}
\]

---

## 8. 案例二：Parabola Being

### 8.1 Parabola 的 ESU

抛物线也可以定义为一个 formula / curve being：

\[
ESU_{\mathrm{parabola}}
=
(E_{\mathrm{para}},s_{\mathrm{para}},u_{\mathrm{parabola}})
\]

其最小 ESU 可写为：

```text
ID:
  math.curve.conic.parabola

ESU:
  E:
    name: parabola
    token authority:
      x: input_phase
      y: output_manifestation
      a: curvature_opening
      h: vertex_x
      k: vertex_y
      p: focal_parameter
    orientation:
      primary: locus condition → curve
      function-view: input → output

  s:
    invariants:
      - conic
      - eccentricity = 1
      - focus-directrix equality
      - one axis of symmetry
      - one vertex
      - no finite center

  u:
    class: parabola
    parent: conic
    domain: geometry / algebraic curve
```

### 8.2 Parabola 的不同 view

```text
parabola.view(cartesian)
  → y = ax² + b

parabola.view(vertex_form)
  → y = a(x-h)² + k

parabola.view(polar)
  → r = p/(1+cosθ)

parabola.view(graph)
  → plotted curve

parabola.view(code)
  → y = a*(x-h)**2 + k
```

这些不同表达不是不同的 parabola being，而是同一 ESU 在不同 view 下的显相。

---

## 9. 接口问题：不要把八个参数直接传给 view

讨论中进一步指出，若 ESU 依照 E-surface 展开，可能出现高达 8 个甚至更多参数。不能将这些参数直接作为 positional arguments 传给 view：

```text
view(E,s,u,r,φ,c,...)
```

这会导致接口混乱。

更好的方式是建立：

\[
\boxed{
\text{Formula Passport / ESU Card}
}
\]

即公式护照。ESU 作为只读语义卡片，view 只声明自己需要哪些槽位，由 resolver 提供最小 view model。

流程如下：

```text
1. ESUCard 固定不变
2. φ,r 提供当前实例状态
3. c-view 声明 required slots
4. Resolver 按名字读取槽位
5. 生成 ViewModel_c
6. 后端工具显相
```

核心原则：

\[
\boxed{
\text{不要传递全部参数；只传递 view 所需的命名槽位。}
}
\]

\[
\boxed{
\text{view 不拥有 ESU；view 只读取 ESU 的只读公式护照。}
}
\]

---

## 10. 工程路径：不是让 LaTeX 读取 ESU，而是在 LaTeX 之前编译 ESU

现实问题是：LaTeX、Word、Obsidian、Python 等现有工具都不是 ESU-native 的。它们不会主动读取 ESU 的 \(E,s,u,\phi,r,c\)。

因此，正确的工程路径不是：

```text
让 LaTeX 学会 ESU
```

而是：

```text
ESU → plugin/exporter → LaTeX
```

即：

\[
\boxed{
\text{不是让 LaTeX 读取 ESU，而是在 LaTeX 之前把 ESU 编译成 LaTeX。}
}
\]

对于 LaTeX 来说，这就是一个插件或 exporter：

```text
ESU-LaTeX Plugin
读取 ESU 公式字典
解析 formula persona
根据 view 请求生成 LaTeX 表达
交给 LaTeX 正常渲染
```

其他 renderer 也是类似：

```text
ESU → Word exporter
ESU → Obsidian / MathJax exporter
ESU → SVG exporter
ESU → Python exporter
ESU → plain text exporter
```

这一路线不是替代 LaTeX，而是把 LaTeX 放回它最擅长的位置：显相后端。

---

## 11. Open-source 方向：开放公式设字典

如果该系统要工程化，合理形态应是开源项目：

```text
ESU Formula Dictionary
├── core/
│   ├── formula personas
│   ├── class / subclass definitions
│   ├── token meanings
│   └── orientation definitions
│
├── views/
│   ├── cartesian
│   ├── polar
│   ├── complex
│   ├── graph
│   └── code
│
├── exporters/
│   ├── latex
│   ├── mathjax
│   ├── obsidian
│   ├── word
│   ├── svg
│   ├── python
│   └── plain text
│
└── contributions/
    ├── new formula beings
    ├── improved subclass definitions
    ├── new exporters
    └── domain-specific dictionaries
```

项目定位不是：

```text
又一个 LaTeX 宏包
```

也不是：

```text
又一个数学排版语言
```

而是：

\[
\boxed{
\text{Open Formula Persona Dictionary}
}
\]

中文可称：

```text
开放公式设字典
```

它的使命是：

\[
\boxed{
\text{定义公式的本体；让各种工具负责显相。}
}
\]

---

## 12. 为什么暂不工程化

尽管理论框架成立，当前仍不建议立刻启动完整工程。原因包括：

```text
1. 数学公式 being 数量巨大，分类繁杂。
2. 定义 u-class 与 s-subclass 非常费神。
3. projection / view 若越界，容易变成第二套数学语言。
4. LaTeX 等工具没有原生 ESU 读取层，必须写 exporter。
5. 用户习惯强大，许多人宁愿复制粘贴也不学习新字典。
6. 工程成本与 adoption barrier 都较高。
```

因此，本文建议：

\[
\boxed{
\text{概念冻结，暂不工程化。}
}
\]

未来若需要，可先从个人工作流中的 10–20 个高复用公式 being 开始，而不是启动大规模开源项目。

---

## 13. 可行的最小版本

如果未来重新启动，最小可行版本应当很小：

```text
BOR Formula Persona Dictionary v0.1

核心条目：
1. phase
2. complex phase / re^{iθ}
3. E-surface
4. parabola
5. circle
6. wave
7. derivative
8. integral
9. vector
10. matrix
```

并且只先实现：

```text
ESU source
→ LaTeX exporter
→ boreqs.tex
```

也就是说，不追求全平台，不追求完整显相生态，只解决自身写作中最高频、最痛苦、最值得复用的公式。

---

## 14. 结论

本文的核心发现可以概括为：

\[
\boxed{
\text{没有 ID 的公式只能重写；有 ESU 的公式才能调用。}
}
\]

或：

\[
\boxed{
\text{没有 ESU 的公式，是可复制的显相；有 ESU 的公式，是可调用的 being。}
}
\]

LaTeX 让公式显得漂亮，但它并没有让公式成为一个被命名、被理解、被调用的 being。ESU 的意义在于给公式以本体身份、结构意义、类属归位和方向定义。

对于 \(re^{i\theta}\) 这样的公式，人们真正需要关注的往往只是 \(r\) 与 \(\theta\)，但因为没有公式 ID 和 ESU，它只能一遍又一遍以完整显相被手写或复制。ESU 公式设字典试图改变这一点：让高复用、高书写成本、高语义密度的公式从“显相字符串”升级为“可调用公式 being”。

最终原则为：

\[
\boxed{
\text{ESU defines what the formula is; c-view defines how it is seen; }(\phi,r)\text{ define its current appearance under that view.}
}
\]

中文：

\[
\boxed{
\text{ESU 定义公式是什么；c-view 定义从哪里看；}\;(\phi,r)\;\text{定义在该视角下当前怎样显相。}
}
\]

因此，本成果不主张立即替代 LaTeX，也不主张重新发明数学排版系统。它提出的是一个更高层的解释框架：

```text
LaTeX 负责显相；
ESU 负责公式 being；
view 负责观察面；
exporter 负责桥接；
公式字典负责命名和复用。
```

这就是“数学公式归一字典”的本体基础。

---

## 附录 A：核心术语

| 术语 | 定义 |
|---|---|
| Formula Being | 作为结构存在体的数学公式 |
| ESU | \(E,s,u\)，公式的本质公式设 |
| E | 公式身份、token 权柄、意义方向、尺度边界 |
| s | 结构骨架、subclass、不变量 |
| u | class / 数学物种 / 公式类属 |
| \(\phi\) | 当前状态参数 |
| r | 显相布局，如 inline、display、block、graph |
| c | view / 显相视角，如 Cartesian、polar、LaTeX、SVG |
| c-view | 某种显相观察面 |
| Formula Passport | ESU Card，公式护照，只读语义卡片 |
| Exporter | 将 ESU + view 编译成具体工具格式的插件 |
| Formula Persona Dictionary | 公式设字典，保存公式 being 的 ESU |

---

## 附录 B：一句话摘要

```text
公式写作的痛苦，不是因为 LaTeX 不够强，
而是因为公式没有被命名为 being。
LaTeX 复制显相，ESU 调用本体。
```

