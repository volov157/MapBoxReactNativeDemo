## <MapboxGL.FillLayer />
### FillLayer is a style layer that renders one or more filled (and optionally stroked) polygons on the map.

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
* <a href="#name-1">fillAntialias</a><br/>
* <a href="#name-2">fillOpacity</a><br/>
* <a href="#name-3">fillColor</a><br/>
* <a href="#name-4">fillOutlineColor</a><br/>
* <a href="#name-5">fillTranslate</a><br/>
* <a href="#name-6">fillTranslateAnchor</a><br/>
* <a href="#name-7">fillPattern</a><br/>

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
`fillAntialias`

#### Description
Whether or not the fill should be antialiased.

#### Type
`boolean`
#### Default Value
`true`


#### Supported Style Functions
`camera`

___

#### Name
`fillOpacity`

#### Description
The opacity of the entire fill layer. In contrast to the `fillColor`, this value will also affect the 1px stroke around the fill, if the stroke is used.

#### Type
`number`
#### Default Value
`1`

#### Minimum
`0`


#### Maximum
`1`

#### Supported Style Functions
`camera, source, composite`

___

#### Name
`fillColor`

#### Description
The color of the filled part of this layer. This color can be specified as `rgba` with an alpha component and the color's opacity will not affect the opacity of the 1px stroke, if it is used.

#### Type
`color`
#### Default Value
`#000000`


#### Disabled By
`fillPattern`

#### Supported Style Functions
`camera, source, composite`

___

#### Name
`fillOutlineColor`

#### Description
The outline color of the fill. Matches the value of `fillColor` if unspecified.

#### Type
`color`


#### Disabled By
`fillPattern`

#### Supported Style Functions
`camera, source, composite`

___

#### Name
`fillTranslate`

#### Description
The geometry's offset. Values are [x, y] where negatives indicate left and up, respectively.

#### Type
`array<number>`
#### Default Value
`[0,0]`

#### Units
`pixels`


#### Supported Style Functions
`camera`

___

#### Name
`fillTranslateAnchor`

#### Description
Controls the frame of reference for `fillTranslate`.

#### Type
`enum`
#### Default Value
`map`

#### Supported Values
**map** - The fill is translated relative to the map.<br />
**viewport** - The fill is translated relative to the viewport.<br />


#### Requires
`fillTranslate`

#### Supported Style Functions
`camera`

___

#### Name
`fillPattern`

#### Description
Name of image in sprite to use for drawing image fills. For seamless patterns, image width and height must be a factor of two (2, 4, 8, ..., 512).

#### Type
`string`


#### Supported Style Functions
`camera`

