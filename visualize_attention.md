# Setup

Note: this currently only works with ACT Policies.

Clone the github repo, checkout the branch with a local fix (to load the local dataset) and install the dependencies.


```bash
git pull https://github.com/ilonajulczuk/physical-AI-interpretability.git
git checkout visualize_attention
pip install -e .
```

Example command to run the attention

```bash

export EPISODE_NUM=29

python examples/visualise_original_data_attention.py --dataset-repo-id lerobot/svla_so101_pickplace --episode-id $EPISODE_NUM --policy-path /home/jovyan/hackathon-example-policies/notebooks/outputs/train/2025-09-19/21-34-15_act --output-dir ./output/attention_analysis_results
```


## Troubleshooting

The script couldn't find the libary `src`:

Example error output:
```bash
Traceback (most recent call last):
  File "/Users/justynailczuk/Projects/physical-AI-interpretability/examples/visualise_original_data_attention.py", line 23, in <module>
    from src.attention_maps import ACTPolicyWithAttention
ModuleNotFoundError: No module named 'src'
```

Run before the script:
```bash
export PYTHONPATH=.
```