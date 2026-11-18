# Components Catalog

Implementation: `components.css` (prefix `ui-`). Live examples: `showcase.html`. Mockups may only use the components below.

| Component | CSS classes | Purpose | Variants / states | Usage rules | Accessibility notes |
|-----------|-------------|---------|-------------------|-------------|---------------------|
| Button | `ui-button`, `--secondary`, `--ghost`, `--danger`, `--sm` | Trigger an action | primary, secondary, ghost, danger, small, disabled | One primary button per view; danger only for destructive actions | Native `<button>`, 44px target, visible focus |
| Text input | `ui-input` | Short free text | default, invalid, disabled | Always with a label; help and error text below | `<label for>`, `aria-invalid`, `aria-describedby` |
| Select | `ui-select` | Choose one option from a list | default, invalid | Use for 4+ options; radios for fewer | Native `<select>` |
| Textarea | `ui-textarea` | Long free text | default, invalid | Vertical resize only | Label required |
| Checkbox / Radio | `ui-check` | Binary or single choice | checked, unchecked, disabled | Group radios with a legend | Native inputs, 44px target |
| Form field | `ui-field`, `ui-label`, `ui-help`, `ui-error` | Label + control + help/error | required (`ui-label--required`), error | Error text states how to fix | Error linked with `aria-describedby` |
| Card | `ui-card`, `ui-card__title` | Group related content | default | Title + content + optional single action | Use heading levels in order |
| Alert | `ui-alert--info/success/warning/danger` | Contextual message | info, success, warning, danger | `role="alert"` for errors/warnings, `role="status"` otherwise | Color never the only signal: include text |
| Badge | `ui-badge`, `--info/success/warning/danger` | Status label | neutral, info, success, warning, danger | Short text (1-2 words) | Text conveys the status |
| Table | `ui-table` | Tabular data | default | Caption and `scope` on headers | `<caption>`, `<th scope>` |
| Navbar | `ui-navbar`, `ui-navbar__brand` | Main navigation | default | Max ~6 entries | `<nav aria-label>` |
| Breadcrumb | `ui-breadcrumb` | Location in hierarchy | default | Current page last | `aria-label="Breadcrumb"` |
| Tabs | `ui-tabs`, `ui-tab` | Switch between related views | selected, unselected | 2-5 tabs | `role="tablist"`, `aria-selected` |
| Modal | `ui-modal-backdrop`, `ui-modal` | Focused task or confirmation | default | Use sparingly; always a close/cancel action | Focus trap and Esc to close to be implemented at build time |
| Layout helpers | `ui-container`, `ui-stack`, `ui-row`, `ui-grid` | Page structure and spacing | n/a | Responsive grid, no fixed widths | n/a |

## Known gaps (not in this base kit)
Date picker, file upload, stepper, pagination, toast, tooltip, charts. Flag them as open points if a sketch needs them.
