# Crowdsourcing SRL

This folder contains the data collected for:

  A Novel Workflow for Accurately and Efficiently CrowdsourcingPredicate Senses and Argument Labels
  Youxuan Jiang, Huaiyu Zhu, Jonathan K. Kummerfeld, Yunyao Li, Walter Lasecki
  Findings of EMNLP, 2020

This data is primarily of value for analysing the behaviour of our annotators.
For gold SRL data, see the complete CoNLL 2009 dataset.

## predicates-full.txt and arguments-full.txt

These are the complete contents of the `final_task_results` table for the word
sense disambiguation task (predicates) and the argument labeling task
(arguments). They were extracted using the following commands:

```
SELECT * FROM final_task_results WHERE dataset = "WSD_large_scale"
SELECT * FROM final_task_results WHERE dataset = "SRL_large_scale"
```

The columns are:

- `id`, A unique ID for this row
- `sen_id`, The sentence ID
- `va_id`, 
- `ori_gold`, The original gold label
- `final_gold`, A modified gold label based on errors found during our work
- `pred`, The predicted label
- `ex_condition`, The experimental condition
- `worker_decision`, Where in the workflow the label was finalised
- `final_label`, The final label chosen
- `dataset`, Always 'WSD_large_scale'

## srl-db.sql

This is the complete database of experimental results.

+--------------------+
| Tables_in_crowdsrl |
+--------------------+
| argument           |
| final_task_results |
| frame              |
| gold_argument      |
| gold_verb          |
| result             |
| select_result      |
| sentence           |
| task               |
| task_type          |
| verb               |
+--------------------+
