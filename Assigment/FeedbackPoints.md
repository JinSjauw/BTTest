# Feedback Points — Ordered by Estimated Effort

---

## Low Effort

| # | Category | Point | Notes |
|---|----------|-------|-------|
| 1 | Documentation | **Open the node editor**: Make the way to open the editor more obvious. | Tooltip, menu item label, or welcome dialog. |
| 2 | Documentation | **Empty tree state**: Explicitly show the tree is empty and a new one must be created (or start with a default). | Placeholder text on the canvas. |
| 3 | Documentation | **Hierarchy direction**: Explicitly document/visualise the tree execution direction (left-to-right, top-to-bottom). | Add an arrow or label to the canvas background. |
| 4 | Documentation | **Sequence & Selector explanation**: Much clearer documentation/tooltips for composite nodes. | Update tooltip text. |
| 5 | Documentation | **Desired behaviour example**: Make the intended AI behaviour (Patrol → Idle → Attack loop) more obviously achievable. | Add an example tree screenshot or diagram to the assignment doc. |
| 6 | Documentation | **Update assignment/docs**: Assume users try things before reading docs — make critical info prominent. | Callout boxes, bold warnings at the top. |
| 7 | Node Behaviour | **Time units**: All wait/duration nodes should explicitly show time units (seconds, etc.). | Append `(s)` to field labels. |
| 8 | Node Behaviour | **Clear condition/action naming**: Make conditionals and action nodes distinctly recognisable. | Prefix or colour-code: `[C]` / `[A]` in the node palette. |
| 9 | Node Behaviour | **Enemy detect targets**: Should be implemented as an **Action** node, not a conditional. | Re-classify in MethodID and move to Action category. |
| 10 | Editor UI | **Node visual hierarchy**: Display a "big title" (node name) with smaller text showing the concrete type. | Adjust font sizes in the node view. |
| 11 | Blackboard | **Empty variable name handling**: When a variable has no name, display `"NO NAME"` as a placeholder. | Fallback string in the dropdown UI. |
| 12 | Blackboard | **Shared variable fields/dropdown**: Ensure SharedVar dropdowns are intuitive and clearly labelled. | Add header text like "Select blackboard variable…". |
| 13 | Node Palette | **Search menu tooltips**: Show a small tooltip for each node in the search menu, including what fields (Blackboard keys, parameters, etc.) the node uses. | Extend the existing search UI with a tooltip panel. |

---

## Medium Effort

| # | Category | Point | Notes |
|---|----------|-------|-------|
| 15 | Editor UI | **Root node repositioning**: Allow the Root node to be moved (not fixed). | Remove the fixed-position constraint on the root node. |
| 16 | Editor UI | **Sticky notes / comment nodes**: Ability to create notes and place arbitrary text on the canvas. | New node type: a resizable text box with no execution logic. |
| 17 | Node Palette | **Palette friction reduction**: Improve discoverability and ease of adding nodes from the palette. | Categorised palette, favourites, or a docked sidebar. |
| 18 | Node Palette | **Parameter dropdown clarity**: Example: MoveTo node should have a dropdown clearly separating Transform vs Vector targets. | Grouped `<optgroup>` or labelled sections in field dropdowns. |
| 19 | Node Fields | **Multi-type field support with type grouping**: Nodes accepting Vector3 or Transform should have both types grouped and separated in the dropdown, with a visual badge on the node signature beforehand. | Extend field serialisation to support multi-type, tagging nodes with `[MultiType]` attribute. |
| 20 | Node Palette | **Auto-blackboard variable generation**: When a node is created, automatically generate any required Blackboard variable. | Hook into node creation — check required fields, create missing BB entries. |
| 21 | Node Palette | **Auto-creation of Blackboard variables**: If a node requires a Blackboard variable that doesn't exist, generate it automatically (with a default name or prompt). | Similar to #20 but triggered at field-assignment time. |
| 22 | Node Behaviour | **Enemy_StopMovement and WaitSeconds nodes**: Ensure they exist and are discoverable. | Verify MethodID entries, add to palette, document. |
| 23 | Debugging | **Runtime tree connection**: Provide clearer explanation of how to connect/runtime-assign a behaviour tree to an enemy/AI. | Add docs/tooltips for the runner component. |
| 24 | Blackboard | **Dock the blackboard next to the inspector**: Make the blackboard window dockable (e.g. next to the Inspector) or otherwise more accessible during tree editing. | Dockable editor window, or a sidebar panel in the tree editor. |
| 25 | Blackboard | **Variable categories/collections**: Allow visually separating blackboard variables into categories or collections, while keeping them under one semantic list. | Group headers, folders, or colour-coded sections in the blackboard view. |

---

## High Effort

| # | Category | Point | Notes |
|---|----------|-------|-------|
| 26 | Core Editor | **Undo/Redo log**: Implement full undo/redo with visible logging/history. | Requires a command-pattern architecture, transaction stack, and a history panel UI. |

---

## Positive (Keep as-is)

- Composite nodes correctly implemented.
- Unreal Blueprint users (without BT experience) can get a viable Patrol-Idle-Attack loop working.
- Runtime debugging actively used and helpful.
