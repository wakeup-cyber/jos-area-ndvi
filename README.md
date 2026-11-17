# Jos NDVI, February 2025

<img width="593" height="577" alt="ndvi_map" src="https://github.com/user-attachments/assets/e1452f7d-8003-4dd8-9249-5e5b9662be22" />


I'm a physics graduate teaching myself Python and satellite data. I picked the
Jos area because it's my immediate environment.

I took a Sentinel-2 image from 2 Feb 2025 (dry season), used bands B04 and
B08, and computed NDVI in Python with Rasterio and NumPy. I saved it as a
GeoTIFF and opened it in QGIS.

The first map had flat blobs that looked odd. I clicked on one and the value
was exactly 0. Real NDVI doesn't do that, so I counted: 506 pixels were 0, and
502 of them had both bands at 0. I masked those 502 as no-data and saved a
clean file. When I put the map over OpenStreetMap, the holes landed on ponds
and lakes. My guess is that water was masked before the data reached me, but
I haven't confirmed that.

Other patches stayed dark red. One read -0.27 and another -0.41. Negative
values usually mean water, but I haven't checked each patch yet, so I'm not
calling them ponds.

The rest is mostly brown, which makes sense for the dry season. There are
green blocks in the south-west that look like farmland and a green strip in
the north-east that looks like a stream valley.

Next i'll do cloud masking, a wet-season image, and any ground check.I
want to compare the same month from another year and then map water bodies
with NDWI.

Use 'Jos_NDVI_clean.tif'. 'Jos_NDVI_Output.tif' is my first version with the fake
zeros.  The notebook is 'josmap.ipynb'
