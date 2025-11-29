# PEM Electrolyzer — Web MPC + ANN (repo files)

This package provides the web-side implementation for HE-NMPC:
- warm-start ANN (browser TF.js)
- surrogate ANN used by the fast MPC
- MQTT integration with Arduino (broker.hivemq.com) and MATLAB topics

## File map
- index.html — UI shell
- styles.css — styling
- app.js — MQTT, UI, charts, wiring
- henmpc-controller.js — upper-layer warm-start
- mpc-controller.js — lower-layer surrogate-driven MPC
- kenya-data.js — realistic data sources / NASA API templates
- models/ — (not included) place TF.js converted models here:
  - /models/surrogate/model.json
  - /models/warmstart/model.json

## Converting models (from Python/PyTorch/TensorFlow)
If your ANNs were trained in Python/TensorFlow:
1. Save a `tf.keras` model.
2. Use `tensorflowjs_converter`:
