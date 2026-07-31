# GUI Slider User Manual

GUI Slider is an add-on that lets you place slider- and joystick-style controllers directly in the viewport to control Shape Keys, bone custom properties, and Data Paths.

---

## Supported Versions

GUI Slider supports **Blender 4.2 and later**. It has been verified with **Blender 5.2.0 LTS**, including add-on registration, container and slider creation, and driver generation.

---

## Basic Workflow

1. Select the armature you want to add controllers to
    - If the armature's scale is not 1, the sliders will not display at the correct size.
2. Switch to **Pose Mode**
3. Open **N Panel > GUI tab**
4. Press **Add Container** to create a container
    - Use **Slider Container** if you want a row of sliders
    - Use **Joystick Container** if you want to group four-direction controls
5. Press **Add Slider** to add a slider or joystick inside the container
6. Choose a target type
    - **Shape Key**
    - **Custom Property**
    - **Data Path**
7. Set the target object or bone and the property name
8. Adjust the range and appearance as needed
9. Move the controller in the viewport and confirm that the value changes correctly

!!! tip "A quicker entry point"
    Once a container exists, steps 5 onwards can be skipped: **right-click the property** you want to drive and choose **Add New GUI Slider** to create a slider for it on the spot. See [How to Add a Slider](sliders.md#how-to-add-a-slider) for details.

!!! tip "Base Scale"
    For **non-human-sized** models (small characters, giant mechs, etc.), set **Base Scale** from the panel menu (▼) to match your model's size. When creating a container, the scale value will be reflected in the input field.

    - **1.0** = human-sized scale
    - Quick View display scale is auto-compensated
    - The setting is stored per armature

---

## When To Use What

- **Slider**: Use it when you want to control a single value
- **Joystick**: Use it when you want to assign different targets to Up, Down, Left, and Right. Useful for driving four-direction facial Shape Keys such as eyebrows or mouth shapes with one controller.
- **Dual Controller**: Use it when you want to add a secondary helper controller to an existing bone

---

## Recommended First Steps

1. Create one **Slider Container**
2. Add a single slider that targets a **Shape Key**
3. Confirm it works, then add mirroring or columns if needed
4. Once the number of controls grows, switch to **Quick View**

!!! info "Quick View"
    Quick View lets you gather scattered containers at the front of the viewport and view them as a single overview. Regardless of where you are in the viewport, it always shows the same layout. Even when you have many containers, many columns, or containers placed in different locations, you can efficiently adjust parameters in one place.
