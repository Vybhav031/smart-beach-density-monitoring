# Smart Beach — Beach Density & Hazard Monitoring

**Built for Bruce County (Kincardine, ON) · Jun–Dec 2024 · Deployed in production**

Real-time AI system that monitors crowd density and rip-current risk at Station Beach, giving beachgoers and county authorities live heatmaps and hazard alerts.

## The problem

Station Beach had no way to monitor crowding or warn visitors about rip currents in real time. Lifeguard coverage is limited; incidents were reactive, not prevented.

## What I built

- **Real-time object detection** of beachgoers using YOLOv8, Faster R-CNN, and Detectron2, tuned for difficult outdoor conditions (glare, occlusion, variable weather)
- **Rip-current prediction** improved by integrating third-party data: offshore buoy readings and coastal weather databases
- **Live interface** rendering density heatmaps and hazard alerts for both the public and county staff
- **Cloud deployment** for scalable real-time processing

## How it works

```
Camera feed ──► Object detection ──► Density aggregation ──► Heatmap + alerts ──► Web interface
                (YOLOv8 / Detectron2)                              ▲
                                                                   │
Offshore buoy + coastal weather data ──► Rip-current prediction ───┘
```

## Stack

Python · PyTorch · TensorFlow · OpenCV · cloud infrastructure

## Results

- Deployed live for Bruce County during the 2024 beach season, used by beachgoers and county authorities
- Reliable person detection maintained under glare, occlusion, and variable weather conditions

## What I'd do differently

- Add automated model monitoring to catch accuracy drift as conditions change through the season
- Set up a retraining pipeline using flagged edge cases (low light, crowded scenes) instead of manual review
- Build in evaluation metrics dashboards from day one rather than assessing performance ad hoc

## Related files

- `beach_density_detection.ipynb` — detection and density mapping notebook
- `docs/final_report.pdf` — full project report
