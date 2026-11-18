# Design Tokens

Source of truth: `tokens.css` (CSS custom properties). This is a generic base kit, to be replaced or adapted to the client's design system.

## Colors
| Token | Value | Usage |
|-------|-------|-------|
| `--color-primary` / `-hover` | #1d4ed8 / #1e40af | Primary actions, links, selected state |
| `--color-secondary` | #374151 | Navigation bar, secondary surfaces |
| `--color-bg` / `--color-bg-subtle` | #ffffff / #f3f4f6 | Page and subtle backgrounds |
| `--color-text` / `--color-text-muted` | #111827 / #4b5563 | Body text / secondary text |
| `--color-border` / `--color-border-subtle` | #9ca3af / #e5e7eb | Form control borders / separators |
| `--color-success`, `-warning`, `-danger`, `-info` (+ `-bg`) | see `tokens.css` | Status feedback (alerts, badges) |
| `--color-focus` | #f59e0b | Keyboard focus outline |

## Typography
| Token | Value | Usage |
|-------|-------|-------|
| `--font-family` | system UI stack | All text |
| `--font-size-sm` to `-2xl` | 0.875 / 1 / 1.25 / 1.5 / 2 rem | Help text, body, h3, h2, h1 |
| `--font-weight-regular` / `-medium` / `-bold` | 400 / 500 / 700 | Body, labels, headings |

## Spacing, radius, elevation, breakpoints
- Spacing: 4px scale (`--space-1` to `--space-12`).
- Radius: 4px, 8px, full. Shadows: `--shadow-sm`, `--shadow-md`.
- Breakpoints: 640 / 768 / 1024 px.

## Accessibility notes
Text and control colors target WCAG AA contrast on the base background. Interactive targets are at least 44px high. Focus is always visible. To be re-verified when the tokens are adapted.
