# Changelog

## v1.2.0

Released 31 July 2026

### Create sliders from a property right-click menu

You can now right-click the property you want to drive and create a slider on the spot, with no need to copy and paste a data path.

- **Add New GUI Slider** — creates a new slider that drives that property
- **Add Linked GUI Slider** — attaches the property to an existing slider as a Linked Driver

The data path is captured by Blender itself, so nested properties such as those inside a material node tree resolve correctly. Enable **Open Detail Settings** to continue into the regular Add Slider dialog with the target already filled in.

See [How to Add a Slider](sliders.md#how-to-add-a-slider) and [Linked Driver](linked-driver.md) for details.

!!! note "When the commands appear"
    They appear only for properties whose standard Blender right-click menu provides **Add Driver**.

### Array indices are detected automatically

For Data Path targets, the index is now read from a trailing subscript such as `location[2]`. The **Data Type** (Scalar / Vector) and **Array Index** fields are therefore no longer needed and have been removed from the dialogs.

A related bug, where an index of 0 was incorrectly treated as "auto", is also fixed.

### Right-click dialog improvements

- Added a **select button** to the right of the container list. Pressing it makes the chosen container active in the viewport, which helps when the names alone are ambiguous
- The **slider name is now required**. Leaving it blank previously produced a silently auto-numbered name; it now shows a warning instead
- Fixed the dialog restoring the previous slider name and the **Open Detail Settings** state every time it was opened
- Fixed the container row starting further left than the other fields

### Compatibility

Verified on **Blender 5.2.0 LTS**. None of the Python API changes in 5.1 or 5.2 affect this addon. The addon still supports **Blender 4.2 and later**.

***

## v1.1.0

Released 4 April 2026

### Blender 4.2 and later supported

Previously 5.0-only, the addon now runs on **Blender 4.2 and later**. Compatibility wrappers were added for bone visibility control and for action FCurve access, both of which changed between versions.

Icon availability differences between Blender versions were also fixed, such as `STRIP_COLOR` missing in 4.2 and the colour icon boundary starting at 4.4.

### Linked Driver

A single slider can now drive **several properties at once**. Attaching another property to an existing slider (the primary) makes it follow that slider's motion. Each linked property has its own output range, so the same slider movement can produce different amounts of change.

Click the 🔗 button in the N-panel slider list to open the **Manage Linked Drivers** dialog, where entries can be added, edited and removed together. If a target already has a driver, a warning appears and it is only overwritten when explicitly allowed.

See [Linked Driver](linked-driver.md) for details.

### Shape keys on curve and surface objects

Shape Key targets now accept shape keys on **curve and surface objects** in addition to meshes.

### Other fixes

- Dual Controller bone collections are now created only when they are actually needed
- Fixed clearing the target object having no effect in the batch shape key add
- Fixed the keymap list in Preferences breaking when several keymaps share a name
- Clarified the Base Scale help text
