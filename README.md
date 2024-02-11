# Helsinki's 3D city model for Blender

This repo contains a simple template for Blender to start working with the City of Helsinki's city models.

**TLDR**: To obtain the city model data as OBJ's, get data as map tiles from https://kartta.hel.fi/link/dqR2SJ  OR https://3d.hel.ninja/data/mesh/Helsinki3D-MESH_2017_OBJ_2km-250m_ZIP/ - unzip, import an OBJ's of one LOD (16 is good to start with), that's it! \o/

More information about the city model: hel.fi/3d



## Demo data

Template uses following 2017 OBJ map tiles:
- Helsinki_678492x2  LODxx
- espoo_491677x2



## Blender version

4.0.1

## Units and axis

Scene uses meter as unit, north is +Y and east +X.

## Local origin <> city coordinate system

Blender scene origo is at Helsinki's "official" zero point of the city model datasets (since 2016). It's just an arbitrary point on south-west side of Helsinki, so that the whole city area is in the positive X/Y-axis. The location is in [EPSG:3879 GK25](https://epsg.io/3879) at X-easting 25490000 and Y-northing 6668000.

You'll find this origo object in "Coordinates" collection, please take a look at custom properties of the origo.

City of Espoo local origo is also included.

## Camera

Viewport clipping is set from 2 to 50000 meters.

## Rendering

Template uses Cycles GPU compute as default.

## Lighting

Sun-system has WGS84 location set. https://docs.blender.org/manual/en/4.0/addons/lighting/sun_position.html?utm_source=blender-4.0.1


## Helsinki OBJ tileset info

Helsinki's photogrammetry model (2015, 2017) is created with Bentley ContextCapture, and it's OBJ tiling and file naming syntax is common for CC exports.

2017 OBJ map tile folder name syntax:
- **680500**a1 - map sheet number
- 680500  **a1** - sub-tile of the map tile.
- Sub-tiles use hilbert curve tiling system. Todo: screenshot here.

File naming scheme:
- **Tile_+047_+049**_L16_000 - Sub-tile name
- Tile_+047_+049_**L16**_000 - LOD number, higher is more detailed
- Tile_+047_+049_L16_**000** - Sub-sub-tile numbering

### Importing multiple OBJ's to Blender

To import OBJ's from multiple sub-folders, use "recursion" parameter "one level", and search "L16*obj" to get all LOD16 tiles listed:

![image](https://github.com/kinotus/hki-3d-blender/assets/150700/b73b2400-3926-48ce-b1c5-c37d6b32348e)

Helsinki OBJ-tiles use Z up and Y forward-axis:

![image](https://github.com/kinotus/hki-3d-blender/assets/150700/9738e5a5-6275-44f5-84f2-5f1b22b440c1)

Correctly imported models are in the positive axis like this:

![image](https://github.com/kinotus/hki-3d-blender/assets/150700/3ac9a9d4-990e-45fb-9d61-5b931bd3e287)


# TODO

- Include terrain, city districts, camera templates etc...
- What do you need? Commit a pull request or add an issue.
- 
