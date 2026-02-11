# Vendor onboarding: add or update vendors.yaml

Edit **only** the file `config-template/vendors.yaml`.

## Task

**Either onboard a new vendor or update an existing one:**

1. **If a vendor with the same `name` already exists** in the `vendors:` list: **update that entry in place** with the data below. Do not duplicate it.
2. **If no vendor with this name exists**: **add** a new entry to the `vendors:` list.
3. Do **not** change any other vendors. Keep the exact same YAML structure for all entries.

## Vendor entry structure

Each entry under `vendors:` must have:

- `name` (string)
- `with_proxy` (boolean: true/false)
- `http_method` (string: GET or POST)
- `request`:
  - `url` (string)
  - `queries` (list of `{ key: "...", value: "..." }`; can be empty)
- `tracking`:
  - `url` (string)
  - `queries` (list of `{ key: "...", value: "..." }`; can be empty)

Optional keys per vendor: `user_agent`, `content_type`.

## Vendor data (from GitHub issue)

The following JSON is the vendor to add or update (match by `name`). Convert it to YAML. If an entry with this `name` exists, replace it; otherwise append a new entry.

```json
{{VENDOR_JSON}}
```

The file must remain valid YAML and all other entries must be unchanged.
