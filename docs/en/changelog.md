# Changelog

## v1.2.0

31 July 2026

- **Sliders can now be created from a property's right-click menu**, without copying a data path first ([details](sliders.md#how-to-add-a-slider))
- Verified on **Blender 5.2.0 LTS**. The addon still supports Blender 4.2 and later
- Fixed Repair not restoring drivers that target the first element of an array, such as `location[0]`

***

## v1.1.0

4 April 2026

- **Blender 4.2 and later are now supported** (previously 5.0 only)
- Added **Linked Driver**: one slider can drive several properties, each with its own output range ([details](linked-driver.md))
- Shape Key targets now also accept **curve and surface objects**
- Fixed issues in the batch shape key add and in the keymap list

***

## v1.0.1

25 March 2026

- Added **batch slider creation from shape keys**: select several shape keys and turn them into sliders at once
- Raised the maximum number of columns per container to **8**
- Fixed the Quick View mark toggling twice when mirrored and non-mirrored sliders were selected together
