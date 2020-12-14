# Procedural-Venice

Node handbook 

This part provides the basic descriptions for important nodes and their parameters.

1. Building generator

Controls the total number of floors, resample the footprint outline to decide the distribution of floors and windows, and provides basic information for adding accessories. The parameters are divided into three parts.

* Building options: Converts the footprint to a rough building shape.

| Parameter  | Overview |
| ------------- | ------------- |
|Number of floors|	Decides the number of floors. The max value is 10.|
|Default height	|Controls the default height for each floor. If there is no overriding height for specific floors, it will be used as the floor height. |
|Default resample	|Resamples the edges of the footprint by inner points and adjusts the width for every window unit. If there is no overriding resample value for specific floors, it will be used as the resample value.|

* Window options: Sets the concrete position of window units.

|Parameter	| Overview|
| ------------- | ------------- |
|Default position|	The vertical distance from the window bottom to the floor. If there is no overriding value for specific floors, it will be used as default.|
|Default window height|	Default height of the window placeholders. This value may differ from the actual height of the window models.|
|Default window width|	Default width of the window placeholders. This value may differ from the actual width of the window models.|

* Details: Applies overriding control over specific floors.

|Parameter	|Overview|
| ------------- | ------------- |
|Floor index	|The floor needs to be modified.|
|Height	Rewrites |the height of the floors.|
|Resample length	|Rewrites the resample value of the floors.|
|Window options - Position	|Rewrites the window position of the floors.|
|Window options - Height	|Rewrites the window height of the floors.|
|Window options - Width	|Rewrites the window width of the floors.|

2. Roof generator
Constructs a hip/gable/flat roof by the given type and distributes tiles automatically. For the hip/gable roof, only external corners will be covered by tiles. 

|Parameter	|Overview|
| ------------- | ------------- |
|Expansion	|Expands the footprint of the roof from the base footprints. |
|Roof type	|Switches among hip/gable/flat roof types. |
Notice that it may take a while to generate a single hip or gable roof because of the boolean operation on tiles.
3. Fence generator
Creates a fence on the given polyline. This node is automatically called while generating the flat roof.

|Parameter	|Overview|
| ------------- | ------------- |
|Resample|	Controls the subdivision level of the pillars. Smaller value gives preciser controls over the pillar shapes. |
|Length|	Controls the length of the pillars.|
|Common pillars|	Controls the curve and thickness of the common pillars that are on the middle of polyline segments.|
|Special pillars|	Controls the shapes of special pillars that are on the ends of polyline segments.|
|Fence|	Controls the shapes of fence.|

4. Ledge generator
Creates continuous or separated ledges on the given polyline. 

|Parameter|	Overview|
| ------------- | ------------- |
|Type|	Switches between continuous ledges and separated ledges.|
|Length|	Controls the length of ledges in vertical direction.|
|Extrusion|	Controls the length of ledges in horizontal direction.|
|Carve|	Cuts the ledges from the give ratios. Only works for separated ledges.|
|Fence|	Controls the shapes of fence.|

5. Ledge decoration generator
Creates uniformly distributed decorations under the roof. Most of the parameters can be found in fence generators.
6. Window generator
Creates a window by assembling the arch, shutters, glasses, and fence. It works if users only choose some of the components. The parameters are divided into three parts.
* Arch options: generates inflected ogee arch / two pointed trefoil / round trefoil / round trefoliated / pointed trefoil / pointed trefoil / two centered ogee arch / iris arch.

|Parameter|	Overview|
| ------------- | ------------- |
|Arch type	|Switches among 7 arch types.|
|Sample segments	|Controls the number of points that are used to fit the each arc of the arch. Bigger value makes the arch smoother. |
|Expansion	|Controls the distance between inner shape and outer shape. |
|Fill mode	|Switches between “Fill” mode and “Hollow” mode.|
|Wire mode	|Switches between “Wire” mode and “Face” mode.|
 

* Window options: Sets the concrete position of window units.

|Parameter	       |Overview       |
| --------------- | ------------- |
|Height	          |Controls the height of the main body of windows.|
|Separation ratio	|Controls the position of sliding windows.|
|Shutter options	 |Adjusts the rotation angles of the shutters and the distribution of leaves.|

* Fence options: most of the parameters can be find in fence generators.

