# Inspeq Performance Metrics: Benchmarking Strategies and Empirical Results
The accuracy of the metrics is a fundamental measure of Inspeq AI’s methodology performance, indicating the proportion of correct predictions or outputs made by the platform out of the total number of cases tested. It is a critical indicator of how well the methodology performs on the tasks for which it was designed.</br>
## Caveats and Considerations:
While accuracy is a valuable metric, it is essential to interpret it within the context of several important factors that can influence the results:

* <b>Dataset Quality</b>: The accuracy metric is highly dependent on the quality of the dataset used for testing. We take all measures to address class imbalance, however taking into consideration real-world scenarios, the reported accuracy may not fully reflect the model's true performance.<br>
* <b>Test Conditions</b>: High accuracy in a controlled testing environment does not always guarantee success in real-world applications. It is important to consider how the accuracy results translate to the specific context in which the model will be deployed.
* <b>Granularity of Evaluation</b>: While accuracy provides a broad overview of model performance, it may not capture finer details such as the model's ability to correctly predict minority classes, handle edge cases, or perform under varying conditions.



## Methodology or Evaluation and Benchmarking

1. <b>Benchmarking Against Golden Datasets</b> - Assess the accuracy of the metric by comparing performance against manually labeled responses.
2. <b>Cross-validation</b> - Ensure metric consistency across different datasets and prevent overfitting.
3. <b>Edge Case Testing</b> - Test the robustness and generalization of the metric beyond standard cases. Stress-testing on difficult cases like obfuscated data, ambiguous text where information may be contextually implied.
4. <b>Comparison Against GPT-4</b>- Compare results against GPT-4o prediction.


## Summary of benchmarking results

<table border="1" cellpadding="5" cellspacing="0">
    <thead>
        <tr>
            <th>S.No.</th>
            <th>Evaluation Metric</th>
            <th>F1 Score</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Answer Relevancy</td>
            <td>0.91</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Factual Consistency w.r.t Context</td>
            <td>0.95</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Conceptual Similarity</td>
            <td>0.97</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Response Tonality</td>
            <td>0.62</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Toxicity Detection</td>
            <td>0.83</td>
        </tr>
        <tr>
            <td>6</td>
            <td>Banned Topics*</td>
            <td>0.94</td>
        </tr>
        <tr>
            <td>7</td>
            <td>Invisible Text</td>
            <td>1</td>
        </tr>
        <tr>
            <td>8</td>
            <td>Code Detection*</td>
            <td>0.90</td>
        </tr>
        <tr>
            <td>9</td>
            <td>Data Leakage (PII)</td>
            <td>0.92</td>
        </tr>
        <tr>
            <td>10</td>
            <td>Insecure Output</td>
            <td>0.92</td>
        </tr>
        <tr>
            <td>11</td>
            <td>Prompt Injection Detection</td>
            <td>0.93</td>
        </tr>
        <tr>
            <td>12</td>
            <td>NSFW detection*</td>
            <td>0.95</td>
        </tr>
        <tr>
            <td>13</td>
            <td>Sensitive data leakage detection (beyond PII)*</td>
            <td>0.70</td>
        </tr>
        <tr>
            <td>14</td>
            <td>Coherence</td>
            <td>0.87</td>
        </tr>
        <tr>
            <td>15</td>
            <td>Bias</td>
            <td>0.86</td>
        </tr>
    </tbody>
</table>
</br>
*  Coming Soon