# CNN Face Recognition Attendance Prototype

An academic prototype that detects faces, matches them to enrolled participant profiles, and records attendance from uploaded photographs.

## How it works

- MTCNN detects and aligns faces.
- A pretrained FaceNet model converts each face into an embedding.
- The embedding is compared with participant profiles using cosine similarity.
- Matches below the 0.70 threshold are flagged for review.
- Attendance is recorded in a CSV file.

The notebook also contains experiments with a CNN trained from scratch and fine-tuned MobileNetV3.

## Run in Google Colab

1. Open the notebook in Colab.
2. Run the cells in order.
3. Upload a ZIP containing folders labelled `P01` to `P05`.
4. Create participant profiles, then run `run_face_attendance_bot()` to upload a photo and log attendance.

## Evaluation

On an internal holdout of 60 photographs, the system detected 59 faces and correctly matched all 59. One P05 image produced no face detection. It also matched three fresh photos for P01, P02, and P03. A group-photo check matched one face to P03 and flagged two low-similarity faces for review.

These results are limited to a small dataset and do not establish performance across different people or capture conditions.

## Data privacy

Participant photographs, face profiles, consent records, and attendance logs are not included in this repository. Use only images collected with participants’ consent.
