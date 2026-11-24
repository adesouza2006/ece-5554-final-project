# Basketball Shot and Form Classification

This class project will classify each basketball shot using two judgments: whether the ball went in and whether the shooter used good form.

| Shot outcome | Form | Classification |
| --- | --- | --- |
| Make | Good | Good make |
| Make | Poor | Bad make |
| Miss | Good | Good miss |
| Miss | Poor | Bad miss |

## Planned pipeline

1. Use YOLO to detect the basketball and hoop in video frames. Track the ball across frames and use its trajectory relative to the hoop to decide whether each attempt was a make or a miss.
2. Use RTMPose to estimate the shooter's body keypoints around the release. Define a form rubric and use it to classify each attempt as good or poor form.
3. Match the outcome and form assessments by shot attempt and assign one of the four labels above.

## Repository layout

| Path | Purpose |
| --- | --- |
| `src/shot_tracking/` | YOLO detection, ball tracking, and make or miss decisions |
| `src/form_analysis/` | RTMPose keypoints and form assessment |
| `src/classification/` | Combine outcome and form into the final shot label |
| `configs/` | Model and pipeline settings |
| `data/raw/` | Local input videos |
| `data/annotations/` | Reference labels for shot outcome and form |
| `docs/` | Form rubric and annotation guidance |
| `tests/` | Future tests for tracking, form assessment, and label mapping |

Record one outcome label and one form label per annotated attempt so each part of the pipeline can be evaluated independently.
