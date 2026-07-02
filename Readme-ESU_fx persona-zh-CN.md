
# ESU 公式设字典

**ESU 公式设字典** 是一个概念框架，用来把数学公式理解为一种 **formula being / 公式存在体**，而不仅仅是 LaTeX 表达式、符号字符串，或可以复制粘贴的排版结果。

核心思想：

> LaTeX 定义公式显相。  
> ESU 定义公式本体。

在这个框架中，一个数学公式不只是等待渲染的字符串。它有自己的本质公式设：

\[
ESU = (E, s, u)
\]

其中：

- **E** 定义公式身份、token 权柄、意义方向、尺度边界和角色边界。
- **s** 定义公式结构不变量、subclass 和内部结构模式。
- **u** 定义公式所属的 class，也就是数学物种。

公式的可见形态则由另一层处理：

\[
view_c(\phi, r)
\]

其中：

- **φ** 定义当前状态参数或实例参数。
- **r** 定义显相布局，例如 inline、display、graph、block。
- **c-view** 定义显相视角，例如 LaTeX、Cartesian、polar、rectangular、SVG、Python、Word、Obsidian 等。

## 为什么需要这个框架

很多公式具有稳定结构和稳定意义，却没有稳定的 being-ID。

例如：

\[
re^{i\theta}
\]

这个公式在数学、物理、信号、波动、旋转、复数表示中反复出现。人们通常会一遍又一遍写它，或者写一次之后复制粘贴。

但它实际上已经具有稳定结构：

- 它是 complex phase / polar complex form。
- 它有半径或模长 \(r\)。
- 它有相位角 \(\theta\)。
- 它可以显相为 \(a+ib\)。
- 它可以显相为 \(r(t)e^{i(\omega t+\phi_0)}\)。
- 它可以显相为 \(r(\cos\theta+i\sin\theta)\)。

如果没有 ESU 身份，它只是一串被反复复制的符号显相。  
如果有 ESU 身份，它就成为一个可以被调用的公式 being。

## 与 LaTeX 的关系

本项目不是要替代 LaTeX。

LaTeX 的强项是显相：

```text
分式如何排版
上下标如何显示
矩阵如何排列
inline / display 如何控制但 LaTeX 不天然知道：

```
这个公式是谁它属于什么 class它的 subclass 是什么它的 token 各自承担什么角色它的 orientation 是什么它与其他公式是否属于同一个 being 的不同 view
```

所以：

> LaTeX 把公式写漂亮。  
> ESU 把公式叫成一个 being。

## 当前状态

本仓库目前处于 **concept-frozen / 概念冻结** 状态。

它还不是工程项目、插件、软件包或完整开源实现。当前目的只是保存概念架构，并为未来可能的发展留下一个清晰入口。

## 完整概念稿

完整概念稿见：

ESU Formula Dictionary Concept Note

## 一句话说明

没有 ID 的公式⇒只能反复重写显相\text{没有 ID 的公式} \Rightarrow \text{只能反复重写显相}没有 ID 的公式⇒只能反复重写显相 有 ESU 的公式⇒可以调用公式 being\text{有 ESU 的公式} \Rightarrow \text{可以调用公式 being}有 ESU 的公式⇒可以调用公式 being

或者说：

> 没有 ESU，公式只是可复制的显相。  
> 有了 ESU，公式成为可调用的 being。  
> EOF

```