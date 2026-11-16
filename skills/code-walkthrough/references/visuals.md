# Architecture visuals

## Format selection

Prefer Excalidraw. Offer Excalidraw, Mermaid, or both once, with Excalidraw as the default. Honor an explicit user selection. Use available diagram tools when suitable; do not require an external account for a basic walkthrough.

Create an editable `.excalidraw` scene through a supported Excalidraw integration or a locally available Excalidraw library. Inspect the installed tool or library's current schema before programmatically constructing a scene. If neither is available, use the minimal scene shape below and verify import compatibility when an editor is accessible. Do not claim import or rendering verification based solely on JSON parsing.

```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "code-walkthrough",
  "elements": [],
  "appState": {"viewBackgroundColor": "#ffffff"},
  "files": {}
}
```

Populate elements with supported rectangles, text, and arrows. Generate unique stable IDs, finite coordinates, positive dimensions, explicit text sizing, arrow points, and all common element properties required by the available schema. Use valid bindings or intentionally unbound arrows; never dangling references. Keep connector endpoints outside text boxes. Do not fabricate a share URL or upload private code to a public diagram service.

If a rendering tool exists, render a preview and inspect it for overlap, clipped labels, arrow direction, and readable sizing. If rendering is unavailable, deliver the editable scene with a clearly identified alternate SVG preview or Mermaid view. Explain which output was structurally checked and which was visually inspected. A plain SVG with a hand-drawn appearance is not an Excalidraw export.

## Composition

- Build from verified component relationships, never a generic architecture template.
- Use a top-to-bottom overview for broad systems; keep no more than five nodes horizontally.
- Group by actual process or deployment boundaries, then by responsibility when useful.
- Identify external systems and storage clearly. Show only relevant infrastructure.
- Label each edge with its actual operation. Use dashed edges for inferred relationships and a distinct labeled style for asynchronous work.
- Use the same component names in the diagram, table, and walkthrough.
- Include brief source paths or symbol references where readable; keep detailed evidence in the companion table.
- Put dense execution detail in a separate use-case visual with numbered handoffs.
- Use color as a secondary cue and provide a short text alternative.

## Mermaid alternative

Use a compact flowchart for component relationships and a sequence diagram only when ordering, asynchronous handoffs, or branches are the useful information. Quote labels with punctuation. Avoid HTML labels, click directives, and per-diagram configuration. Do not produce a low-density diagram where a sentence is clearer.

## Deliverables

Include the rendered or alternate preview in the walkthrough and offer the editable file as an artifact. Save generated artifacts according to the environment's normal persistence rules. Do not modify the inspected repository merely to store diagrams unless the user requests it. If a format cannot be generated, state the concrete limitation and provide the best available visual while preserving the user's requested preference for a later conversion.
