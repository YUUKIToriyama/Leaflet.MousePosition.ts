# Leaflet.MousePosition.ts

This repo intends to be a modern replacement of [Leaflet.MousePosition](https://github.com/ardhi/Leaflet.MousePosition) plugin

## Usage

```bash
npm i leaflet.mouseposition.ts
```

```typescript
import { MousePosition } from "leaflet.mouseposition.ts";

const mousePosition = newMousePosition({
	position: "topright",
});
mousePosition.addTo(map);

map.on({
	click: (event) => {
		const location = event.latlng;
		mousePosition.update(location);
	},
});
```

## Customize

You can customize appearance of plugin by writting JSX.

![custom element](https://i.imgur.com/cUrHwwC.png)

```typescript
import React from "react";
import {
	MousePosition,
	MousePositionControlProps,
} from "leaflet.mouseposition.ts";

const customElement: React.FunctionComponent<MousePositionControlProps> = (
	props
) => {
	return (
		<table>
			<tr>
				<td>Latitude</td>
				<td>{props.latlng.lat}</td>
			</tr>
			<tr>
				<td>Longitude</td>
				<td>{props.latlng.lng}</td>
			</tr>
		</table>
	);
};

const mousePosition = new MousePosition({
	position: "topright",
	customElement: customElement,
});
mousePosition.addTo(map);
```
