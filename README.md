# ESU Formula Dictionary

**ESU Formula Dictionary** is a concept framework for treating mathematical formulas as **formula beings**, rather than only LaTeX expressions or copied symbolic appearances.

Core idea:

> LaTeX defines formula appearance.  
> ESU defines formula being.

In this framework, a mathematical formula is not only a string to be rendered. It has an essential persona:

\[
ESU = (E, s, u)
\]

where:

- **E** defines the formula identity, token authority, meaning orientation, scale, and role boundaries.
- **s** defines the structural invariants and subclass pattern.
- **u** defines the class or mathematical species of the formula.

The visible form of a formula is handled separately through:

\[
view_c(\phi, r)
\]

where:

- **φ** defines the current state or instance parameters.
- **r** defines the layout mode, such as inline, display, graph, or block form.
- **c-view** defines the manifestation view, such as LaTeX, Cartesian, polar, rectangular, SVG, Python, Word, or Obsidian.

## Why this matters

Many formulas have stable structure and meaning, but no stable being-ID.

For example:

\[
re^{i\theta}
\]

is repeatedly written, copied, and pasted as a visible expression. Yet it already has a stable structure and class:

- It is a complex phase / polar complex form.
- It has a radius-magnitude component \(r\).
- It has a phase-angle component \(\theta\).
- It can appear as \(a+ib\), \(r(t)e^{i(\omega t+\phi_0)}\), \(r(\cos\theta+i\sin\theta)\), or other views.

Without an ESU identity, the formula remains only a repeated appearance.  
With an ESU identity, it becomes a callable formula being.

## Key distinction

This project does **not** attempt to replace LaTeX.

Instead:

- LaTeX remains a powerful rendering system.
- ESU provides the semantic source layer.
- Exporters or plugins may compile ESU formula beings into LaTeX, Word, Obsidian, SVG, Python, MathML, or other formats.

In short:

> ESU is the semantic source.  
> Renderers are manifestation backends.

## Concept Note

The first concept note is available here:

[ESU Formula Dictionary Concept Note](docs/ESU_Formula_Dictionary_Concept_Note.md)

## Current status

This project is currently in **concept-frozen** status.

It is not yet an engineering project, package, plugin, or full open-source implementation. The purpose of this repository is to preserve the conceptual architecture and provide a seed for possible future development.

## Possible future directions

Future work may include:

- A small ESU formula persona dictionary
- Formula beings such as `ComplexPhase`, `Parabola`, `E-surface`, `Derivative`, `Integral`, `Wave`, and `Matrix`
- A LaTeX exporter
- An Obsidian / Markdown exporter
- A Python / symbolic-math exporter
- A graph or SVG view exporter
- A formal comparison with LaTeX, MathML, OpenMath, and symbolic computation systems

## Working principle

\[
\text{Formula without ID} \Rightarrow \text{rewritten appearance}
\]

\[
\text{Formula with ESU} \Rightarrow \text{callable being}
\]

Or simply:

> Without ESU, a formula is a copyable appearance.  
> With ESU, a formula becomes a callable being.

## License

License to be decided.

## Chinese README

A Chinese introduction is available here:

[Readme-ESU_fx persona-zh-CN.md](Readme-ESU_fx%20persona-zh-CN.md)
