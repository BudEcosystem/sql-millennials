
## Introducing Text-to-SQL Translation Model - Millennials. 🎉

Welcome to our Text-to-SQL Translation Model repository! Our model is specifically fine-tuned for text-to-SQL tasks, aiming to revolutionize how systems understand and translate natural language instructions into SQL queries. We have 2 models [sql-millennials-7b](https://huggingface.co/budecosystem/sql-millennials-7b) and [sql-millennials-13b](https://huggingface.co/budecosystem/sql-millennials-13b) built on Mistral 7B and CodeLLaMa 13B respectively. Our model has been meticulously fine-tuned with a curated dataset comprising 100k SQL query generation instructions, ensuring quality and precision.

## Features

* Specialized in converting natural language text to SQL queries.
* Fine-tuned on a diverse set of 100k SQL query generation instructions.
* Easy to integrate and use for generating SQL queries on the fly.

## Generate responses

Now that your model is fine-tuned, you're ready to generate responses, you can easily generate SQL queries from natural language instructions. To do this, you'll be using our generate.py script, which allows for quick inference and can fetch models directly from the Hugging Face model hub.
Here's a quick guide on how to use it:

The script runs inference using the pre-trained model from the Hugging Face model hub and prints the generated SQL query.


```python
import torch
from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("budecosystem/sql-millennials-13b")
model = AutoModelForCausalLM.from_pretrained("budecosystem/sql-millennials-13b")

prompt = "A chat between a curious user and an artificial intelligence assistant. The assistant gives helpful, detailed, and polite answers to the user's questions.
USER: Create SQL query for the given table schema and question ASSISTANT:"

inputs = tokenizer(prompt, return_tensors="pt")
sample = model.generate(**inputs, max_length=128)
print(tokenizer.decode(sample[0]))

```
The script runs inference using the pre-trained model from the Hugging Face model hub and prints the generated SQL query.



## Why millennials?

1. Automated Database Management for Businesses

Scenario: Small to medium-sized enterprises (SMEs) often lack dedicated IT teams to handle database queries, making it challenging to retrieve specific data quickly for analysis and decision-making.

Use Case: Your text-to-SQL model can be integrated into a company's internal systems, allowing staff without technical SQL knowledge to retrieve data. They can input natural language requests, such as "Get a list of all transactions above $10,000 in the last quarter," and the system, powered by your model, would convert this into a corresponding SQL query to retrieve the data.

2. Automating Data Analytics Processes
Scenario: Data analysts and business professionals often face bottlenecks in generating insights due to the complexities of SQL query formulation, especially when immediate or repetitive data retrieval and analysis are required.

Use Case: Your text-to-SQL model serves as a transformative intermediary in this scenario. By integrating the model into their data analytics systems, organizations enable professionals to input data requests in natural language. For instance, an analyst could input, "Show the trend of online sales growth over the past five years," and the system would instantly convert this request into a SQL query, retrieve the data, and even integrate it into visualization tools for immediate insight generation. This functionality not only accelerates the analytical processes but also democratizes data-driven insights across different organizational departments, allowing even non-technical staff to leverage the power of real-time data analytics without deep knowledge of SQL.

3. Enhancing CMS Interfaces
Scenario: Content Management Systems (CMS) are often non-intuitive for non-technical content managers when it comes to complex data retrieval or database management.

Use Case: CMS providers can leverage your model to enhance their system's backend interface. Content managers can use natural language to request specific data, like "Find all blog posts in May 2023 with more than 500 views," and the model will generate the appropriate SQL to retrieve the information. This feature makes database management more accessible, efficient, and user-friendly.

4. Customer Support Optimization
Scenario: Customer support centers often need to retrieve client or product information stored in databases while resolving tickets or inquiries, requiring basic knowledge of SQL.

Use Case: Your model can be integrated into support ticketing systems, enabling support personnel to type requests in natural language, such as "Show all open tickets from customers in New York filed this month," and immediately receive the data needed to expedite their resolution process, improving customer service efficiency and response time.

5. Data Journalism and Research
Scenario: Journalists and researchers frequently rely on complex databases to gather insights and data points necessary for their work but may lack the technical know-how of SQL.

Use Case: By integrating your text-to-SQL model into research software or journalistic tools, professionals can query databases using natural language. For example, a journalist might input, "Retrieve the average household income in Texas in 2022," and your model would facilitate immediate access to this data, allowing for more efficient research and data-driven storytelling.


Contributing
We welcome contributions to help improve the model or address issues. Please feel free to submit pull requests or open issues to discuss changes or improvements.


### Acknowledgments

We'd like to thank the open-source community and the researchers whose foundational work laid the path to this  model.
