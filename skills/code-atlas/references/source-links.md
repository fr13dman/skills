# Source evidence and links

## Excerpts

Read the file at the inspected revision before quoting. Capture current line numbers with a numbered file read, such as `nl -ba path/to/file`, or a repository tool that returns line numbers. Use language-tagged code fences. Put a clickable file or symbol reference immediately before each excerpt. Keep quotations exact; place explanation outside the fence. Mark gaps as omitted rather than silently joining unrelated lines. Redact any secrets encountered and state that redaction occurred.

Prefer a small number of meaningful snippets covering the entry point, central business operation, and persistence or output. Each excerpt should answer a question about the use case. Link additional handoffs without quoting trivial forwarding functions.

## Parameters and request/response examples

For each important handoff, include the callee's actual signature with meaningful parameter names/types/defaults and its actual call site where available. Explain parameter values using the concrete use case. When a parameter is a request or context object, identify the relevant fields; when a dependency is injected, show its construction/wiring or link to it. Explain return values, awaited work, generators, mutations, and emitted events explicitly.

Keep verbatim code separate from an illustrative invocation. For example, after quoting the real `get_order(order_id, principal)` signature and handler call, show a clearly labeled example mapping: `order_id = "example-order-7"`, `principal = an authenticated user context`. Do not substitute these literals into a quoted repository snippet or fabricate properties on the principal.

For each of the three or more use cases, show the request and response where applicable. Derive methods, paths, status codes, field names, and errors from handlers, models, serializers, and tests. Label the example's provenance: recorded, test fixture, or illustrative static trace. Omit irrelevant fields with an explicit note instead of implying that a partial payload is complete. Show a streaming sequence as named events with relevant payloads; do not wrap it as a single JSON response. For non-HTTP code, show the corresponding invocation/event and return value, state change, or side effect.

Use safe invented example data only in labeled illustrative examples, never as measured or fetched facts. Do not include credentials, personal data, real cookies, or live tokens. If an output depends on external data unavailable during inspection, show the supported output shape and explain which values remain unknown.

## Remote source

Use the actual repository provider and a verified revision. Prefer commit-pinned links when the provider supports them. For GitHub, the form is `https://github.com/OWNER/REPO/blob/COMMIT/path/to/file#L42`; use this only after verifying the owner, repository, commit, path, and line. Use the provider's own supported line-link syntax for other hosts; do not guess. Never include credentials from remote configuration in a URL.

If local edits change the quoted source, use a local link and disclose that it reflects working-tree changes. Do not attach a remote commit link to code absent from that commit. If only a branch link is available, identify it as a moving reference.

## Local source

Use the environment's supported clickable absolute file-link format, with a single line anchor if supported. Prefer `[handler.ts](/absolute/path/handler.ts:42)` for editor links where available. Use `sandbox:` links for downloadable artifacts when required by the environment. If line anchors are unsupported, provide the clickable file plus the exact symbol and line number in prose. Never imply that an unclickable path is a working link.

## Evidence boundaries

Maintain a small internal record of each component and important edge, its implementing file or symbol, and whether it is observed or inferred. Include source evidence in the component table and walkthrough. State unknowns directly, including missing services, generated code, inaccessible modules, or deployment configuration. An import proves a dependency; it does not by itself prove a runtime call.
