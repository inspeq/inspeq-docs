We use this default configuration to tag the results of metrics evaluations. Which you can override while calling the inspeq eval methods. 

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
            "Irrelevant Answer",
            "Marginally Relevant Answer",
            "Relevant Answer"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.7,
            1
          ]
        },
        "answer_fluency_config": {
          "threshold": 0.5,
          "custom_labels": [
            "PASS",
            "FAIL"
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
            "Negative",
            "Neutral",
            "Positive"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.7,
            1
          ]
        },
        "factual_consistency_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Hallucinated",
            "Inconsistent",
            "Consistent"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.7,
            1
          ]
        },
        "word_count_limit_config": {
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
          "threshold": 0.75,
          "custom_labels": [
            "Coherent",
            "Incoherent"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "bias_config":{
          "threshold": 0.5,
          "custom_labels": [
            "Unbiased", 
            "Biased"
          ],
          "label_thresholds": [
            0, 
            1
          ]
        },
        "grammatical_correctness_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Incorrect",
            "Partially Correct",
            "Correct"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.7,
            1
          ]
        },
        "conceptual_similarity_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Dissimilar",
            "Somewhat similar",
            "Similar"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.7,
            1
          ]
        },
        "readability_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Sophisticated",
            "Moderate",
            "Easy"
          ],
          "label_thresholds": [
            0,
            0.3,
            0.6,
            1
          ]
        },
        "clarity_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Not Clear",
            "Partially Clear",
            "Clear"
          ],
          "label_thresholds": [
            0,
            0.5,
            0.74,
            1
          ]
        },
        "narrative_continuity_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Non Continuous",
            "Continuous"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "model_refusal_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Detected",
            "Not Detected"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "data_leakage_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Not Detected",
            "Detected"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "creativity_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Not Creative",
            "Creative"
          ],
          "label_thresholds": [
            0,
            0.5,
            1
          ]
        },
        "diversity_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Redundant",
            "Non Redundant"
          ],
          "label_thresholds": [
            0,
            0.41,
            1
          ]
        },
        "insecure_output_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Not Detected",
            "Detected"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "prompt_injection_config": {
          "threshold": 0.61,
          "custom_labels": [
            "Detected",
            "Not Detected"
          ],
          "label_thresholds": [
            0,
            0.61,
            1
          ]
        },
        "compression_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "Compact Summary",
            "Loose Summary"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "density_score_config": {
          "threshold": 0.2,
          "custom_labels": [
            "Verbose Summarization",
            "Concise Summarization"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "fuzzy_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "Well Aligned Summarization",
            "Misaligned Summarization"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "rouge_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "High Overlap",
            "Low Overlap"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "bleu_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "Highly Conforming",
            "Poorly Conforming"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "meteor_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "Semantically Accurate",
            "Semantically Drifting"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "bert_score_config": {
          "threshold": 0.8,
          "custom_labels": [
            "Linguistically Congruent",
            "Linguistically Incongruent"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "cosine_similarity_score_config": {
          "threshold": 0.2,
          "custom_labels": [
            "Contextual Synchrony",
            "Contextual Divergence"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "euclidean_distance_score_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Detected",
            "Not Detected"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "toxicity_config":{
          "threshold":0.5,
          "custom_labels": [
            "Not Detected",
            "Detected"
          ]
        },
        "invisible_text_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Not Detected",
            "Detected"
          ],
          "label_thresholds": [
            0,
            1
          ]
        },
        "get_sentence_embedding_score_config": {
          "threshold": 0.5,
          "custom_labels": [
            "Detected",
            "Not Detected"
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

