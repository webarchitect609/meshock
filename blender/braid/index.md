# Braid

## 1. Create vertex in the center of the world

- select the default cube
- edit mode, vertex select mode
- select everything
- merge at center

![](01-merge-at-center.png)

## 2. Make line out of the vertex

- set front viewpoint(NumPad `1`)
- enable snap to increment

  ![](02-enable-snap-to-increment.png)

- extrude the vertex as shown below

  ![](03-extrude-vertex.png)

- set side viewpoint(NumPad `3`)
- move vertices as shown below

![](04-move-vertices-like-S.png)

## 3. Duplicate it and mirror by all axis

- set front viewport(NumPad `1`)
- exit Edit mode(`Tab`)
- duplicate(`Shift + D, Enter`)
- mirror in Y plane(`Ctrl + M, Shift + Y, Enter`)
- show last operation menu and select missing Y(`F9`, click on Y)

![](05-duplicate-and-mirror.png)

- select two meshes
- join them(`Ctrl + J`)

![](05-1-join.png)

## 4. Connect duplicates in the point of touch

- enter Edit mode(`Tab`)
- turn on X-ray(`Alt + Z`)
- select the middle point, where two lines touch each other
- mergre by distance(`M`, click By Distance)
- turn off X-ray(`Alt + Z`)

![](06-connect.png)

## 5. Duplicate and move Z on 1/3 twice

- exit Edit mode
- add Array modifier:
    - Count: 3
    - Relative offset: checked
    - factor X and Y: 0
    - factor Z: 0.333333

![](07-duplicate-and-move-twice.png)

- apply modifier(mouse over modifier, `Ctrl + A`)

## 6. Cut off uneven part and connect to the other end

- enter Edit mode(`Tab`)
- select uneven part as shown

![](08-select-uneven.png)

- rip one line(`Alt + V, Enter`)
- rip another(`Alt + V`, don't confirm)
- move down Z to complete(`Z`, move, confirm)
- select all(`A`)
- merge by distance(`M`, By Distance)

![](09-even-result.png)

## 7. Make desireable length

- exit Edit mode(`Tab`)
- turn off Snap
- add Array modifier:
    - count: at your taste
    - factor X = Y = 0
    - factor Z = 1
    - merge: true
- if you like it, apply the modifier(mouse over modifier, `Ctrl + A`)

![](10-array-mod.png)

## 8. Set origin at the top

- enter edit mode(`Tab`)
- vertices select mode
- select top center vertex
- snap 3D Cursor there(`Shift + S`, Cursor to Selected)
- leave edit mode(`Tab`)
- Set Origin to 3D Cursor(`Right Click`, Set Origin, Origin to 3D Cursor)

![](11-set-origin.png)

## 9. Convert to Curve and set Bevel

- convert to Curve(`Right Click`, Convert To, Curve)

![](12-convert-to-curve.png)

- go to Object Data Props, Geometry, Bevel, Round
- set Depth to 1mm or at your taste

![](13-curve-round-bevel.png)

- shade smooth(`Right Click`, Shade smooth)
- add Subdivision modifier(`Ctrl + 1`)

![](14-subdivide.png)

## 10. Spread strands from top end for more natural look

- enter Edit mode, Vertices
- enable Proportional Editing(`O`)
- select top three points
- scale on X(`S, X`)
- scroll so Proportional Editing affects full length of the braid
- get similar to shown below and confirm operation

![](15-spread-on-x.png)

## 11. Make strands thicker at the top and thinner at the bottom

- leave Edit Mode(`Tab`)
- make sure Proportional Editing is disabled(`O`)
- add Bezier Curve(`Shift + A`, then Curve, Bezier)
- rotate X 90°(`R, X, 90, Enter`)
- move it aside(`G, X`, move) and scale(`S`) for your comfort, apply only scale and rotation(`Ctrl + A`, Scale)

![](16-add-bezier-curve.png)

- go to braid's object data and set Bezier as a Taper Object

![](17-set-taper-object.png)

- select Bezier and enter Edit mode
- make sure Proportional Editing is disabled
- now you can move ends of Bezier along Z, which will mean width of braid's strands at different length

![](18-taper-effect.png)

## 12. Fix curve direction, if needed

- if a strand looks in opposite way: thin at the top, but thick at the bottom, fix it
- select braid and enter Edit mode
- select whole the problematic curve
- then switch direction(`Right click`, Switch direction)
- leave Edit mode

![](20-taper-effect-right.png)

## 13. Make braid follow the path

- make sure 3D Cursor is at braid's origin
- add Path Curve(`Shift + A`, Curve, Path)
- add Curve modifier to braid
  - select Path as Curve object(braid moves to the -X)
  - deform axis: X

![](21-curve-modifier.png)

- set Origin of Path at the end, which inside braid(braid moves back to the +X)

![](22-after-path-set-origin.png)

- using 3D Cursor move Path, so it's Origin and braid's one will be at the same point

![](23-path-and-braid-origins.png)

- rotate Path 90° around Y(`R, Y, 90, Enter`)
- turn on X-ray(`Alt + Z`)
- enter Edit mode
- set Pivot point to 3D Cursor
- select all and scale along Z, so length of Path will be equal to braid

![](24-scale-path.png)

- turn off X-ray

Now you can edit Path as you like, subdivide it if needed. The braid will follow the path.

![](25-edit-path.png)

![](26-braid-follows-path.png)
