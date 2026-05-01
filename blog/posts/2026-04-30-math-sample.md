# Markdown with math

This is a sample post written in Markdown. Inline math like
$y_t = \rho y_{t-1} + \varepsilon_t$ renders with KaTeX.

Display math:

$$
\mathbb{E}_t\left[ M_{t+1} R_{t+1} \right] = 1
$$

A short list:

- Markdown headings, **bold**, *italic*, and `inline code` work.
- Code fences:

```python
def npv(cashflows, r):
    return sum(c / (1 + r) ** t for t, c in enumerate(cashflows))
```

A blockquote:

> "All models are wrong, but some are useful."

A table:

| Model | $R^2$ |
|-------|-------|
| AR(1) | 0.42  |
| AR(2) | 0.45  |

That's it — drop a `.md` file in `blog/posts/` and link to it from the index.
