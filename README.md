timeseries_benchmark/
│
├── pt/                              # Pretraining pipeline
│   ├── pretrain.py
│   ├── trainer_pt.py
│   ├── config_pt.yaml
│   └── losses_pt.py
│
├── ft/                              # Finetuning pipeline
│   ├── finetune.py
│   ├── trainer_ft.py
│   ├── config_ft.yaml
│   └── losses_ft.py
│
├── eval/                            # Evaluation / benchmarking
│   ├── evaluate.py
│   ├── metrics.py
│   ├── benchmark_runner.py
│   └── reporting.py
│
├── models/
│   ├── backbone/                    # Shared backbone (used in PT + FT)
│   │   ├── model.py
│   │   ├── encoder.py
│   │   ├── temporal_block.py
│   │   └── attention_layer.py
│   │
│   ├── heads/                       # Task-specific heads (used in FT)
│   │   ├── anomaly_head.py
│   │   ├── regression_head.py
│   │   ├── classification_head.py
│   │   └── forecasting_head.py
│   │
│   └── model_factory.py             # Assembles backbone + head
│
├── tasks/                           # Task-level abstractions
│   ├── anomaly_detection/
│   │   ├── dataset.py
│   │   ├── trainer.py
│   │   └── evaluator.py
│   │
│   ├── regression/
│   │   ├── dataset.py
│   │   ├── trainer.py
│   │   └── evaluator.py
│   │
│   ├── classification/
│   │   ├── dataset.py
│   │   ├── trainer.py
│   │   └── evaluator.py
│   │
│   └── forecasting/
│       ├── dataset.py
│       ├── trainer.py
│       └── evaluator.py
│
├── data/
│   ├── raw/                         # Raw datasets
│   │   ├── dataset_a.csv
│   │   └── dataset_b.csv
│   │
│   ├── processed/                   # Preprocessed tensors
│   │   ├── dataset_a.pt
│   │   └── dataset_b.pt
│   │
│   ├── preprocessing/
│   │   ├── scaler.py
│   │   ├── windowing.py
│   │   └── augmentation.py
│   │
│   └── dataloaders.py
│
├── logging/
│   ├── logger.py
│   ├── experiment_tracker.py
│   └── wandb_logger.py
│
├── configs/
│   ├── model_config.yaml
│   ├── data_config.yaml
│   ├── anomaly_config.yaml
│   ├── regression_config.yaml
│   └── classification_config.yaml
│
├── utils/
│   ├── seed.py
│   ├── checkpoint.py
│   ├── device.py
│   └── registry.py
│
├── scripts/
│   ├── run_pt.sh
│   ├── run_ft.sh
│   └── run_eval.sh
│
└── README.md