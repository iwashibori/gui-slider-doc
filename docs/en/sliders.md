# Sliders / Joystick

## Slider

A slider is a 1D controller that drives a single target.

!!! note
    The target type of a slider cannot be changed after creation.

### Target Types

#### Shape Key

Controls a **Shape Key value** on a mesh object.

#### Custom Property

Controls a **custom property** on a bone.

- Only bone custom properties are supported
- If the specified custom property does not exist, it is **created automatically**

#### Data Path

Controls **any Blender property** by data path. This is the most flexible target type.

Right-click a property in Blender and use **Copy Full Data Path**, then paste that path into the field. Numeric properties (float / int / bool) are supported.

!!! warning
    String properties, and properties whose right-click menu does not show **Add Driver**, are not supported.

### Add from a Property Right-Click Menu

For a numeric property, you can create a slider directly from its right-click menu instead of copying and pasting its data path.

1. Make sure an armature with a GUI Slider panel is in the current View Layer.
2. Right-click the property you want to control.
3. Choose **Add New GUI Slider**.
4. Select the destination container, optionally enter a slider name, then click **OK**.

Enable **Open Detail Settings** to open the regular Add Slider dialog with the target property already filled in. Use this when you want to set the range or appearance in detail before creating the slider.

To add another property that follows an existing slider, choose **Add Linked GUI Slider** from the same right-click menu. Select the existing slider and its output range to add the property as a Linked Driver.

!!! note "When the commands appear"
    These commands appear only for properties whose standard Blender right-click menu provides **Add Driver**. **Add Linked GUI Slider** also requires at least one existing GUI Slider in the current View Layer.

### Mirror

#### Shape Key Mirror

Automatically creates a mirrored pair based on L/R suffixes. One track is split into halves; on screen, R appears on the left side and L on the right side.

- Example: `smile.L` ↔ `smile.R`

#### Custom Property Mirror

Pairs targets by the `.L` / `.R` suffix in the target bone name.

- Example: `c_hand_ik.l` → mirrored target `c_hand_ik.r` (the property name stays the same)
- If the property name itself also has an L/R suffix, it is mirrored automatically as well

!!! warning
    Mirror is only available for **Shape Key** and **Custom Property**. It cannot be used with Data Path or Joystick.
    Supported suffixes: `.L/.R`, `_L/_R`, `-L/-R` (case-insensitive)

### Appearance

- **Handle Shape:** Circle / Arrow / Square / Diamond
- **Height:** L / M / S
- **Track Style:**

![Capsule / Line styles](../images/line_capsule.gif)

| Style | Description |
|-------|-------------|
| **Capsule** | A rounded capsule-shaped rail |
| **Line** | A thin rail. The handle becomes a tall rectangular shape |

### Keying Excluded

When **Keying Excluded** is ON, the slider bone name switches to the `GEO-` prefix. The handle shape changes to a special double-line icon so it can be distinguished visually.

With this setting enabled, the slider is excluded only from these keying sets:

- Entire Character
- Entire Character (Selected Bones Only)

!!! warning
    If Auto Key is ON, those keying sets will still insert keyframes as usual. To exclude them completely, enable **Preferences > Animation > Only Insert Available** in Blender.

### Reordering

You can manage the display order of sliders from the list in the N panel.

1. Select a slider in the list (linked with bone selection in the 3D View)
2. Move it with the **UP / DOWN** buttons
3. Confirm the new order with **Apply Order**

!!! note
    The `Relocate Slider` button appears beside each column's slider list and is used to move a slider to another column or container. If the list becomes out of sync after Undo / Redo, use **Reload** to resync it.

---

## Joystick

![Joystick](../images/joystick.gif)

A joystick is a circular 2D controller. You can assign a different target to each of the four directions: up, down, left, and right.

- The outer circle defines the movement limit of the handle
- Drag the inner handle to operate it
- Each of the four directions can have its own target

### Per-Direction Target Settings

You can set a target type for each direction (Up / Down / Right / Left). Each direction has its own Range Min / Max and its own independent value range, but the **default value is always 0**.

!!! warning
    Joystick does not support Mirror or Keying Excluded.
