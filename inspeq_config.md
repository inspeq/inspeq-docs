This is the default config file in **JSON** .

```json
{
 "global_communication_mode": "async",
 "auto_instrument_mode": 1,
 "evaluations": {
   "LLM": {
     "communication_mode": "sync",
     "auto_instrument_mode": 1,
     "configurations": {
       "answer_relevance_config": {
         "threshold": 0.5,
         "custom_labels": [
           "irrelevant",
           "relevant"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "response_tone_config": {
         "threshold": 0.5,
         "custom_labels": [
           "fluent",
           "not_fluent"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "factual_consistency_config": {
         "threshold": 0.5,
         "custom_labels": [
           "low_confidence",
           "high_confidence"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "word_limit_test_config": {
         "threshold": 0.5,
         "custom_labels": [
           "Failed",
           "Passed"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "do_not_use_keywords_config": {
         "threshold": 0.5,
         "custom_labels": [
           "Failed",
           "Passed"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "coherence_config": {
         "threshold": 0.5,
         "custom_labels": [
           "incoherent",
           "coherent"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "grammatical_correctness_config": {
         "threshold": 0.5,
         "custom_labels": [
           "incorrect",
           "correct"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "conceptual_similarity_config": {
         "threshold": 0.5,
         "custom_labels": [
           "similar",
           "not similar"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "readability_config": {
         "threshold": 0.5,
         "custom_labels": [
           "readable",
           "non readable"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "clarity_config": {
         "threshold": 0.5,
         "custom_labels": [
           "Not clear",
           "Clear"
         ],
         "label_thresholds": [
           0,
           0.5,
           1
         ]
       },
       "narrative_continuity_config": {
         "threshold": 0.5,
         "custom_labels": [
           "False",
           "True"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "model_refusal_config": {
         "threshold": 0.5,
         "custom_labels": [
           "False",
           "True"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "data_leakage_config": {
         "threshold": 0.5,
         "custom_labels": [
           "False",
           "True"
         ],
         "label_thresholds": [
           0,
           1
         ]
       }
     }
   },
   "RAGS": {
     "communication_mode": "sync",
     "auto_instrument_mode": 1,
     "configurations": {
       "retrieval_relevance_config": {
         "threshold": 0.5,
         "custom_labels": [
           "relevant",
           "irrelevant"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "response_coherence_config": {
         "threshold": 0.5,
         "custom_labels": [
           "coherent",
           "incoherent"
         ],
         "label_thresholds": [
           0
         ]
       }
     }
   },
   "SQL": {
     "communication_mode": "async",
     "auto_instrument_mode": 1,
     "configurations": {
       "query_performance_config": {
         "threshold": 0.5,
         "custom_labels": [
           "efficient",
           "inefficient"
         ],
         "label_thresholds": [
           0,
           1
         ]
       },
       "data_security_config": {
         "threshold": 0.5,
         "custom_labels": [
           "secure",
           "insecure"
         ],
         "label_thresholds": [
           0,
           1
         ]
       }
     }
   }
 }
}


```
