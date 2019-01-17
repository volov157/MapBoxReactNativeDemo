## <MapboxGL.RasterLayer />
### 

### props
| Prop | Type | Default | Required | Description |
| ---- | :--: | :-----: | :------: | :----------: |
| id | `string` | `none` | `false` | A string that uniquely identifies the source in the style to which it is added. |
| sourceID | `string` | `MapboxGL.StyleSource.DefaultSourceID` | `false` | The source from which to obtain the data to style. If the source has not yet been added to the current style, the behavior is undefined. |
| sourceLayerID | `string` | `none` | `false` | Identifier of the layer within the source identified by the sourceID property from which the receiver obtains the data to style. |
| aboveLayerID | `string` | `none` | `false` | Inserts a layer above aboveLayerID. |
| belowLayerID | `string` | `none` | `false` | Inserts a layer below belowLayerID |
| layerIndex | `number` | `none` | `false` | Inserts a layer at a specified index |
| filter | `array` | `none` | `false` | Filter only the features in the source layer that satisfy a condition that you define |
| minZoomLevel | `number` | `none` | `false` | The minimum zoom level at which the layer gets parsed and appears. |
| maxZoomLevel | `number` | `none` | `false` | The maximum zoom level at which the layer gets parsed and appears. |
| style | `union` | `none` | `false` | Customizable style attributes |


### styles

* <a href="#name">visibility</a><br/>
* <a href="#name-1">rasterOpacity</a><br/>
* <a href="#name-2">rasterHueRotate</a><br/>
* <a href="#name-3">rasterBrightnessMin</a><br/>
* <a href="#name-4">rasterBrightnessMax</a><br/>
* <a href="#name-5">rasterSaturation</a><br/>
* <a href="#name-6">rasterContrast</a><br/>
* <a href="#name-7">rasterFadeDuration</a><br/>

___

#### Name
`visibility`

#### Description
Whether this layer is displayed.

#### Type
`enum`
#### Default Value
`visible`

#### Supported Values
**visible** - The layer is shown.<br />
**none** - The layer is not shown.<br />



___

#### Name
`rasterOpacity`

#### Description
The opacity at which the image will be drawn.

#### Type
`number`
#### Default Value
`1`

#### Minimum
`0`


#### Maximum
`1`

#### Supported Style Functions
`camera`

___

#### Name
`rasterHueRotate`

#### Description
Rotates hues around the color wheel.

#### Type
`number`
#### Default Value
`0`

#### Units
`degrees`


#### Supported Style Functions
`camera`

___

#### Name
`rasterBrightnessMin`

#### Description
Increase or reduce the brightness of the image. The value is the minimum brightness.

#### Type
`number`
#### Default Value
`0`

#### Minimum
`0`


#### Maximum
`1`

#### Supported Style Functions
`camera`

___

#### Name
`rasterBrightnessMax`

#### Description
Increase or reduce the brightness of the image. The value is the maximum brightness.

#### Type
`number`
#### Default Value
`1`

#### Minimum
`0`


#### Maximum
`1`

#### Supported Style Functions
`camera`

___

#### Name
`rasterSaturation`

#### Description
Increase or reduce the saturation of the image.

#### Type
`number`
#### Default Value
`0`

#### Minimum
`-1`


#### Maximum
`1`

#### Supported Style Functions
`camera`

___

#### Name
`rasterContrast`

#### Description
Increase or reduce the contrast of the image.

#### Type
`number`
#### Default Value
`0`

#### Minimum
`-1`


#### Maximum
`1`

#### Supported Style Functions
`camera`

___

#### Name
`rasterFadeDuration`

#### Description
Fade duration when a new tile is added.

#### Type
`number`
#### Default Value
`300`

#### Units
`milliseconds`

#### Minimum
`0`


#### Supported Style Functions
`camera`

