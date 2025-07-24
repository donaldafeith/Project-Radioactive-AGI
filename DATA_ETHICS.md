# Data Ethics and Transparency Statement

In accordance with the principles laid out in the `CODE_OF_ETHICS.md`, this document provides a transparent overview of the datasets used to train the specialized expert models in this project. The foundation of any AI is its data, and a commitment to ethical development requires a thorough and honest assessment of that data, including its potential for societal bias.

---

## Datasets Used

### 1. Reasoning Expert

-   **Dataset:** `Open-Orca/OpenOrca`
-   **Description:** A large-scale, high-quality dataset of instruction-response pairs, created by augmenting the FLAN-v2 dataset with GPT-4 responses. It is designed to improve the reasoning and instruction-following capabilities of language models.
-   **Potential Biases:**
    -   **Source Bias:** The data originates from other large language models (FLAN, GPT-4), meaning it may inherit and amplify any biases present in those parent models. This can include subtle western-centric viewpoints, cultural assumptions, and other biases present in the massive web scrapes used to train them.
    -   **Factual Hallucinations:** While curated, the data may contain factual inaccuracies or "hallucinations" from the teacher models, which could be learned by the fine-tuned expert.
-   **Mitigation Strategies:**
    -   **Targeted Use:** The model is intended for reasoning and problem-solving tasks, not as a source of factual truth. Its outputs should be verified.
    -   **Sample Selection:** For this project, only a small fraction of the massive dataset is used for fine-tuning, which reduces the surface area of potential bias, but does not eliminate it.
    -   **Ongoing Evaluation:** The model's performance must be continually evaluated for signs of harmful or biased reasoning patterns.

### 2. Coding Expert

-   **Dataset:** `codeparrot/codeparrot-clean-valid`
-   **Description:** A dataset containing a large corpus of Python code, intended for training code generation models. The "clean" version has been filtered to remove personally identifiable information (PII).
-   **Potential Biases:**
    -   **Code Quality Bias:** The dataset contains code of varying quality. The model may learn to reproduce common bugs, inefficient algorithms, or poor coding practices.
    -   **License Contamination:** Although the dataset is filtered, there is a risk of it containing code snippets with restrictive licenses that are not immediately apparent.
    -   **Security Vulnerabilities:** The model may learn to generate code with security vulnerabilities if such patterns are present in the training data.
-   **Mitigation Strategies:**
    -   **Code as a Tool:** The generated code should be treated as a suggestion or a starting point, not as production-ready, infallible code. All output must be reviewed, tested, and validated by a human developer.
    -   **Security Audits:** Any code intended for a real-world application must undergo rigorous security auditing.
    -   **Focus on Patterns:** The goal is for the model to learn the syntax and structure of code, not to memorize specific implementations.

### 3. Vision Expert

-   **Dataset:** `rafaelpadilla/coco-2017` (based on COCO - Common Objects in Context)
-   **Description:** A large-scale object detection, segmentation, and captioning dataset. It contains images of everyday scenes with labeled objects.
-   **Potential Biases:**
    -   **Geographic and Cultural Bias:** The images in COCO are heavily skewed towards North American and European scenes, objects, and activities. The model may be less accurate at identifying objects or contexts from other parts of the world.
    -   **Demographic Bias:** The people depicted in the dataset may not be representative of global diversity, potentially leading to poorer performance in identifying or describing people from under-represented demographic groups.
    -   **Labeling Bias:** The labels themselves are created by human annotators and can reflect their own biases or cultural understanding of the objects and scenes depicted.
-   **Mitigation Strategies:**
    -   **Awareness of Limitations:** I must acknowledge that the model's "vision" is based on a biased and incomplete view of the world. It should not be used for sensitive tasks like facial recognition or demographic classification.
    -   **Domain-Specific Fine-Tuning:** For any practical application, the vision model would need to be further fine-tuned on a more specific and representative dataset for the target domain.
    -   **Focus on Physics:** As outlined in `build.md`, the primary goal for this expert is to learn "intuitive physics" and object affordances, rather than social or cultural contexts.

---

This document serves as my personal starting point. The ethical practice of data curation is a continuous process of auditing, reflection, and improvement. Because of that... This doc will continue to grow and evolve with the AGI project nicknamed "Radioactive". Because it is my will and vision to show every company that you don't need billions of dollars to build AGI. Radioactive is proof of this.


