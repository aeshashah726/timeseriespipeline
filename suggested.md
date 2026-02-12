```
ts-benchmark-pipeline/
├── data/                        # [Source: Data]
│   ├── raw/                     # Original time series datasets
│   └── processed/               # Preprocessed tensors ready for loading
│
├── logs/                        # [Source: Logplots]
│   ├── pretrain_runs/           # Checkpoints and logs from PT
│   ├── finetune_runs/           # Checkpoints and logs from FT
│   └── visualizations/          # Generated plots (loss curves, embeddings)
│
├── src/
│   ├── models/                  # [Source: Model]
│   │   ├── __init__.py
│   │   ├── backbone/            # Core architectures (The "tr" or Transformer)
│   │   │   ├── transformer.py
│   │   │   └── resnet.py
│   │   ├── layers/              # [Source: layers / attention-layer.py]
│   │   │   ├── attention.py
│   │   │   └── embeddings.py
│   │   └── heads.py             # Specific heads for tasks (Classification, Reg)
│   │
│   ├── data_loaders/            # [Source: Preprocessen]
│   │   ├── __init__.py
│   │   ├── dataset.py           # PyTorch/TF Dataset classes
│   │   └── augmentations.py     # Data augmentation for pretraining
│   │
│   ├── pretrain/                # [Source: PT]
│   │   ├── __init__.py
│   │   ├── engine.py            # The pretraining loop
│   │   └── objectives.py        # Loss functions (Masked modeling, Contrastive)
│   │
│   ├── finetune/                # [Source: FT]
│   │   ├── __init__.py
│   │   ├── engine.py            # The finetuning loop
│   │   └── adapters.py          # Adapter layers if freezing backbone
│   │
│   ├── tasks/                   # Task-specific logic
│   │   ├── __init__.py
│   │   ├── anomaly.py           # [Source: Anomaly]
│   │   ├── regression.py        # [Source: Reguemin]
│   │   └── classification.py    # (Implicitly needed for many benchmarks)
│   │
│   ├── evaluation/              # [Source: Eval]
│   │   ├── __init__.py
│   │   ├── metrics.py           # MSE, MAE, F1-Score, Precision/Recall
│   │   └── benchmark.py         # Script to run full eval suite
│   │
│   └── utils/
│       ├── logger.py            # [Source: logoptions]
│       └── plotting.py          # Tools to generate the "Logplots"
│
├── configs/                     # YAML files to control experiment parameters
│   ├── pretrain_config.yaml     # Hyperparams for PT
│   ├── finetune_anomaly.yaml    # Hyperparams for FT on Anomaly
│   └── finetune_regression.yaml # Hyperparams for FT on Regression
│
├── run_pipeline.py              # Main entry point CLI
├── requirements.txt
└── README.md
```
