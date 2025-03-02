# PlacesSearch - A QGIS Plugin

## Overview

PlacesSearch is a QGIS plugin that allows users to fetch places data from the Google Maps API based on a selected polygon area and save the results as a Shapefile. The plugin integrates seamlessly into QGIS, enabling users to search for points of interest (e.g., hospitals, schools) within a specified geographic boundary.

## Features

- Search for places using Google Places API
- Specify search keywords (e.g., "Hospital", "School", "Aged Care Service", "Nursing Home")
- Select a polygon layer to define the search area
- Automatically converts the CRS to EPSG:4326 if needed
- Saves results as a Shapefile
- Loads results into the QGIS project automatically

## Installation

### Prerequisites

- QGIS 3.x installed on your system
- A valid Google Places API Key with Places API enabled

### Installation Steps

1. **Download the Plugin**

   - Clone the repository or download the ZIP file.

   ```sh
   git clone https://github.com/Wang-Yanni/PlacesSearch.git
   ```

   - Extract the ZIP file if downloaded manually.

2. **Install in QGIS**

   - Copy the `places_search` folder to the QGIS plugins directory:
     - Windows: `C:\Users\<username>\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins`
     - Linux: `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/`

3. **Enable the Plugin**

   - Open QGIS.
   - Go to `Plugins` > `Manage and Install Plugins`.
   - Search for `PlacesSearch` and enable it.

## Usage

1. Open QGIS and load a polygon layer (must be in EPSG:4326 or will be converted).
2. Click on the **Search Places** button in the toolbar.
3. Enter your **Google API Key**.
4. Specify **search keywords** (comma-separated).
5. Select the **polygon layer** defining the search area.
6. Choose the **output path** for the Shapefile.
7. Click **Run Search** to fetch places.
8. The results will be saved and loaded into QGIS as a new layer.

## Configuration

### Google API Key

You need a Google Places API Key to fetch places. You can obtain a key from: [Google Cloud Console](https://console.cloud.google.com/apis/credentials)

Make sure the following API services are enabled:

- **Places API**
- **Geocoding API** (optional for additional features)

## Code Structure

```
places_search/
├── __init__.py  # Plugin initialization
├── places_search.py  # Main plugin logic
├── places_search_dialog.py  # Dialog UI logic
├── places_search_dialog_base.py  # Generated UI code
├── places_search_dialog_base.ui  # Qt Designer UI file
├── metadata.txt  # Plugin metadata
└── icon.png  # Plugin icon
```

## Troubleshooting

- **No places found**: Increase the search radius or check the API key.
- **Invalid CRS error**: Ensure your polygon layer is in EPSG:4326.
- **Google API quota exceeded**: Check your Google Cloud API usage.

## License

This plugin is licensed under the **MIT License**.

## Author

- **Yanni Wang**
- Email: [yanni.wang2000@outlook.com](mailto\:yanni.wang2000@outlook.com)

