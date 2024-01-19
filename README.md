# Web Scraping and Text Summarization Pipeline
The Web Scraping and Text Summarization Pipeline automates the process of gathering insights from a web page and condensing them into brief, meaningful summaries. Comprising two primary steps, the pipeline effortlessly extracts pertinent information from a specified web source and then utilizes advanced text summarization techniques to distill the essence of the content into concise summaries.

![Pipeline](https://github.com/2002nishthajain/Text-Summarization-Wikepedia-Page/assets/79302868/f8618d60-d564-4a56-bae6-ab3b0ba34719)

This streamlined approach empowers users to efficiently access key information without navigating through extensive web content. The README provides a brief overview of the project's structure and purpose for user reference.
This project comprises a robust pipeline for web scraping, text summarization, and subsequent evaluation of generated summaries. The process is organized into three main sections:

## Web Scraping

In this stage, the BeautifulSoup library is utilized for web scraping, and the requests library is employed to retrieve text from a specified URL. The content is then parsed using HTML parsing, and relevant data, including headings and paragraphs, is extracted for further analysis.

## Text Summarization

The text summarization phase involves utilizing the Vertex AI TextGenerationModel. The model is initialized and loaded with pre-trained parameters, generating concise summaries based on provided prompts and content extracted during web scraping.

## Evaluation

The project evaluates the quality of generated summaries using two methods: Rouge Score and Cosine Similarity. The Rouge Score assesses precision, recall, and F1-score, while Cosine Similarity measures the similarity between the generated summaries and the original content.

## Requirements

- `beautifulsoup4`
- `requests`
- `google-cloud-aiplatform` (for Vertex AI integration)
- `vertexai` (for Vertex AI TextGenerationModel)
- `rouge-score`
- `scikit-learn`

Note: The project does not support Google Colab as a dependency; it is designed to be run in a standard Python environment. Ensure that the specified libraries are installed in your Python environment before running the code.

## Problems Faced

### Web Scraping:
1. **Approach Selection:** Choosing the appropriate approach for web scraping posed a challenge. Deciding whether to scrape using HTML tags for structural integrity or extracting raw content required careful consideration.

2. **Data Structural Integrity:** Maintaining the structural integrity of the website's data was crucial for accurate summarization.

### Text Summarization:
1. **Input Size Limit:** Ensuring that the data input size remains within the limit was a key consideration. While the content stayed within the limit, potential challenges arise if chunking becomes necessary.

2. **API Call Quota:** The API calls for summarization exceeded the request quota per minute. A loop was utilized, leading to a risk of exceeding the 60 calls per minute quota. The time library was employed to regulate the calls and prevent quota violations.

3. **Evaluation Metric Selection:** Choosing the right evaluation metrics for assessing the quality of summaries proved to be a challenging task.

This README provides an overview of the project's structure, dependencies, and challenges faced during its development. For detailed code implementation, please refer to the respective sections in the source files.
