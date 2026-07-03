# Hindfoot Alignment Comparator

A browser-based point-and-click tool for comparing radiographic hindfoot alignment angle with a smartphone-based posterior heel alignment angle.

This project is designed to start as a fully manual measurement tool and eventually grow into a structured data collection, cloud storage, and machine learning platform for automated hindfoot alignment assessment.

## Project Goal

The goal is to determine whether a standardized smartphone posterior heel photograph can approximate hindfoot alignment measured on a hindfoot alignment radiograph.

The app allows users to:

- Upload a hindfoot alignment radiograph
- Upload a posterior standing heel photo
- Manually click defined landmarks on each image
- Calculate the radiographic hindfoot alignment angle
- Calculate the photo-based heel alignment angle
- Compare the two measurements
- Export marked images, CSV results, and JSON landmark labels for future model training

## Current Version

**Version:** `0.1.0-manual`

This version is fully manual. No machine learning or automated landmark detection is currently used.

The current goal is to make a reliable manual measurement and labeling workflow before adding automation.

## Measurement Workflow

### Radiograph Measurement

The user clicks four points on the hindfoot alignment radiograph:

1. Proximal tibial axis point
2. Distal tibial axis point
3. Tibial axis / joint-line intersection point
4. Most inferior calcaneus point

The app calculates the angle between:

- The tibial anatomic axis line
- The line from the joint/intersection point to the inferior calcaneus point

### Clinical Photo Measurement

The user clicks four points on the posterior standing heel photo:

1. Proximal leg/Achilles midline point
2. Distal leg/Achilles midline point
3. Heel-axis proximal point near the posterior ankle
4. Inferior/posterior heel center point

The app calculates the angle between:

- The posterior leg/Achilles axis
- The posterior heel axis

## Outputs

The app can export:

- Marked radiograph image
- Marked clinical photo image
- CSV comparison file
- JSON landmark labels
- Full case JSON file

The JSON exports are intended to make each manual measurement usable as training data for future machine learning models.

## Dataset-First Philosophy

This app is intentionally built as a **dataset-first tool**.

Every manual measurement should preserve:

- Case ID
- Image type
- Image dimensions
- Side
- Landmark coordinates
- Calculated angle
- Timestamp
- Notes
- Measurement source

The key idea is:

```text
Manual measurement tool now
→ Structured landmark dataset
→ Reliability and validation study
→ Assisted computer vision
→ Machine learning model
→ Semi-automated clinical/research tool
