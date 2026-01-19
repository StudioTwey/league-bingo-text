# League Bingo Text Data

This repository contains the bingo.json data file used for league bingo games.

## Structure

The JSON file contains three main sections:

### 1. Generic Keys
Generic keys are always included in the bingo board by default (unless excluded via the `excludeDefault` flag in inclusive keys).

```json
"generic": ["item1", "item2", ...]
```

### 2. Exclusive Keys
Exclusive categories where only one category can be selected at a time.

```json
"exclusive": {
  "categoryName": ["item1", "item2", ...]
}
```

### 3. Inclusive Keys
Inclusive categories that can be combined together. Each category now supports an `excludeDefault` flag.

```json
"inclusive": {
  "categoryName": {
    "items": ["item1", "item2", ...],
    "excludeDefault": false
  }
}
```

#### excludeDefault Flag
- When `excludeDefault` is `false` (default): Generic keys are included along with this category's items
- When `excludeDefault` is `true`: Generic keys are excluded when this category is selected

This allows individual inclusive categories to control whether generic keys should be included in the board.

## Validation

Validate JSON structure at: https://jsonlint.com/
