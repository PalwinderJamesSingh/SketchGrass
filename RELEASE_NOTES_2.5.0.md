# SketchGrass 2.5.0

## Safer update preparation
- Save the current .sgproj definition before preparing an update.
- Save the active .skp model; prompt for a filename if the model is untitled.
- Cancelled or failed saves abort update preparation.
- Removed forced SketchUp process restart/quit, which could cause unstable or blank UI states.
- Stage the update and ask the user to close SketchUp normally, then reopen it.

## Unified version label
- Updated extension metadata and menu label to 2.5.0.
- Consolidated the visible version indicator to one v2.5.0 label.

## Validation
Ruby syntax, JavaScript syntax, and ZIP integrity checks passed. Not runtime-tested inside SketchUp 2023.