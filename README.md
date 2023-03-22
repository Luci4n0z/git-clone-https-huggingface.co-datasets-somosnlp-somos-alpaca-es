---
dataset_info:
  features:
  - name: text
    dtype: 'null'
  - name: inputs
    struct:
    - name: 1-instruction
      dtype: string
    - name: 2-input
      dtype: string
    - name: 3-output
      dtype: string
  - name: prediction
    dtype: 'null'
  - name: prediction_agent
    dtype: 'null'
  - name: annotation
    dtype: 'null'
  - name: annotation_agent
    dtype: 'null'
  - name: vectors
    struct:
    - name: input
      sequence: float64
    - name: instruction
      sequence: float64
    - name: output
      sequence: float64
  - name: multi_label
    dtype: bool
  - name: explanation
    dtype: 'null'
  - name: id
    dtype: string
  - name: metadata
    dtype: 'null'
  - name: status
    dtype: string
  - name: event_timestamp
    dtype: timestamp[us]
  - name: metrics
    dtype: 'null'
  splits:
  - name: train
    num_bytes: 984065676
    num_examples: 52002
  download_size: 652741327
  dataset_size: 984065676
---
# Dataset Card for "somos-alpaca-es"

[More Information needed](https://github.com/huggingface/datasets/blob/main/CONTRIBUTING.md#how-to-contribute-to-the-dataset-cards)