# Data Directory

## Overview
This directory contains documentation and configuration files related to the datasets used in the automated avian colony detection research. Due to privacy and organizational policies, raw imagery and geospatial data are not included in this public repository.

## Data Sources
- **Aerial Imagery**: High-resolution drone and fixed-camera imagery from colonial waterbird surveys
- **Ground Truth Annotations**: Manual "dotting" feature classes created by expert ornithologists
- **Geographic Coverage**: Gulf Coast region, Louisiana (specific locations redacted)
- **Temporal Range**: May-June 2025 survey season

## Data Characteristics
- **Image Resolution**: Varied based on survey altitude and equipment
- **File Formats**: .tiff mosaics, .shp feature classes, .gdb geodatabases
- **Coordinate System**: NAD83 / Louisiana South (EPSG:3452)
- **Total Dataset Size**: ~500GB processed imagery, 15,000+ individual annotations

## Processing Pipeline
1. **Image Acquisition**: Drone/fixed-camera surveys of waterbird colonies
2. **Mosaic Creation**: Stitching individual images into seamless mosaics
3. **Georeferencing**: Aligning mosaics to geographic coordinate systems
4. **Manual Annotation**: Expert identification and "dotting" of individual birds/nests
5. **Feature Extraction**: Converting annotations to machine learning training data

## Data Privacy & Access
Raw data remains property of The Water Institute of the Gulf and survey partners. Access restricted to:
- Authorized research personnel
- Collaborative partners under data sharing agreements
- Academic use with appropriate permissions

For data access inquiries, contact: The Water Institute of the Gulf