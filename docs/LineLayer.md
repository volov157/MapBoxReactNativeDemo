## <MapboxGL.LineLayer />
### LineLayer is a style layer that renders one or more stroked polylines on the map.

### props
| Prop | Type | Default | Required | Description |
| ---- | :--: | :-----: | :------: | :----------: |
| id | `string` | `none` | `false` | A string that uniquely identifies the source in the style to which it is added. |
| sourceID | `string` | `MapboxGL.StyleSource.DefaultSourceID` | `false` | The source from which to obtain the data to style.<br/>If the source has not yet been added to the current style, the behavior is undefined. |
| sourceLayerID | `string` | `none` | `false` | Identifier of the layer within the source identified by the sourceID property from which the receiver obtains the data to style. |
| aboveLayerID | `string` | `none` | `false` | Inserts a layer above aboveLayerID. |
| belowLayerID | `string` | `none` | `false` | Inserts a layer below belowLayerID |
| layerIndex | `number` | `none` | `false` | Inserts a layer at a specified index |
| filter | `array` | `none` | `false` | Filter only the features in the source layer that satisfy a condition that you define |
| minZoomLevel | `number` | `none` | `false` | The minimum zoom level at which the layer gets parsed and appears. |
| maxZoomLevel | `number` | `none` | `false` | The maximum zoom level at which the layer gets parsed and appears. |
| style | `union` | `none` | `false` | Customizable style attributes |


### styles

* <a href="#name">lineCap</a><br/>
* <a href="#name-1">lineJoin</a><br/>
* <a href="#name-2">lineMiterLimit</a><br/>
* <a href="#name-3">lineRoundLimit</a><br/>
* <a href="#name-4">visibility</a><br/>
* <a href="#name-5">lineOpacity</a><br/>
* <a href="#name-6">lineColor</a><br/>
* <a href="#name-7">lineTranslate</a><br/>
* <a href="#name-8">lineTranslateAnchor</a><br/>
* <a href="#name-9">lineWidth</a><br/>
* <a href="#name-10">lineGapWidth</a><br/>
* <a href="#name-11">lineOffset</a><br/>
* <a href="#name-12">lineBlur</a><br/>
* <a href="#name-13">lineDasharray</a><br/>
* <a href="#name-14">linePattern</a><br/>

___

#### Name
`lineCap`

#### Description
The display of line endings.

#### Type
`enum`
#### Default Value
`butt`

#### Supported Values
**butt** - A cap with a squared-off end which is drawn to the exact endpoint of the line.<br />
**round** - A cap with a rounded end which is drawn beyond the endpoint of the line at a radius of one-half of the line's width and centered on the endpoint of the line.<br />
**square** - A cap with a squared-off end which is drawn beyond the endpoint of the line at a distance of one-half of the line's width.<br />


#### Supported Style Functions
`camera`

___

#### Name
`lineJoin`

#### Description
The display of lines when joining.

#### Type
`enum`
#### Default Value
`miter`

#### Supported Values
**bevel** - A join with a squared-off end which is drawn beyond the endpoint of the line at a distance of one-half of the line's width.<br />
**round** - A join with a rounded end which is drawn beyond the endpoint of the line at a radius of one-half of the line's width and centered on the endpoint of the line.<br />
**miter** - A join with a sharp, angled corner which is drawn with the outer sides beyond the endpoint of the path until they meet.<br />


#### Supported Style Functions
`camera`

___

#### Name
`lineMiterLimit`

#### Description
Used to automatically convert miter joins to bevel joins for sharp angles.

#### Type
`number`
#### Default Value
`2`


#### Supported Style Functions
`camera`

___

#### Name
`lineRoundLimit`

#### Description
Used to automatically convert round joins to miter joins for shallow angles.

#### Type
`number`
#### Default Value
`1.05`


#### Supported Style Functions
`camera`

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
`lineOpacity`

#### Description
The opacity at which the line will be drawn.

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
`lineColor`

#### Description
The color with which the line will be drawn.

#### Type
`color`
#### Default Value
`#000000`


#### Disabled By
`linePattern`

#### Supported Style Functions
`camera, source, composite`

___

#### Name
`lineTranslate`

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
`lineTranslateAnchor`

#### Description
Controls the frame of reference for `lineTranslate`.

#### Type
`enum`
#### Default Value
`map`

#### Supported Values
**map** - The line is translated relative to the map.<br />
**viewport** - The line is translated relative to the viewport.<br />


#### Requires
`lineTranslate`

#### Supported Style Functions
`camera`

___

#### Name
`lineWidth`

#### Description
Stroke thickness.

#### Type
`number`
#### Default Value
`1`

#### Units
`pixels`

#### Minimum
`0`


#### Supported Style Functions
`camera`

___

#### Name
`lineGapWidth`

#### Description
Draws a line casing outside of a line's actual path. Value indicates the width of the inner gap.

#### Type
`number`
#### Default Value
`0`

#### Units
`pixels`

#### Minimum
`0`


#### Supported Style Functions
`camera, source, composite`

___

#### Name
`lineOffset`

#### Description
The line's offset. For linear features, a positive value offsets the line to the right, relative to the direction of the line, and a negative value to the left. For polygon features, a positive value results in an inset, and a negative value results in an outset.

#### Type
`number`
#### Default Value
`0`

#### Units
`pixels`


#### Supported Style Functions
`camera, source, composite`

___

#### Name
`lineBlur`

#### Description
Blur applied to the line, in pixels.

#### Type
`number`
#### Default Value
`0`

#### Units
`pixels`

#### Minimum
`0`


#### Supported Style Functions
`camera, source, composite`

___

#### Name
`lineDasharray`

#### Description
Specifies the lengths of the alternating dashes and gaps that form the dash pattern. The lengths are later scaled by the line width. To convert a dash length to pixels, multiply the length by the current line width.

#### Type
`array<number>`

#### Units
`line widths`

#### Minimum
`0`


#### Disabled By
`linePattern`

#### Supported Style Functions
`camera`

___

#### Name
`linePattern`

#### Description
Name of image in sprite to use for drawing image lines. For seamless patterns, image width must be a factor of two (2, 4, 8, ..., 512).

#### Type
`string`


#### Supported Style Functions
`camera`

