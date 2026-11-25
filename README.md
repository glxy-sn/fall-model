# Fall detection model weights

Each version tag identifies a commit containing the SHA-256 manifest for its GitHub Release. Download the three checkpoints and `SHA256SUMS` from the same release. Verify them together with `shasum -a 256 -c SHA256SUMS`.

| Checkpoint | Role |
| --- | --- |
| yolo11m-pose.pt | Person detection and pose estimation |
| osnet_x0_25_msmt17.pt | Appearance embeddings for tracking |
| lstm_best.pt | Temporal fall classifier |

Version v1.0.0 uses the annotated_only_occlusion_v3 LSTM checkpoint. It scores 16 pose samples at 10 Hz with stride 2 and a decision threshold of 0.5.

For each new model version, update the manifest, commit it, create an annotated version tag, and attach the matching weights and manifest to a new release. Keep earlier releases available for reproducibility.
