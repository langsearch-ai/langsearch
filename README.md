![image](https://github.com/user-attachments/assets/724c7b2b-26e6-4697-8498-3a2c020daef9)

# LangSearch - Free Search API, Free Rerank API, The World Engine For AGI.

<img width="1510" alt="image" src="https://github.com/user-attachments/assets/88a1ee52-c951-4081-a664-91df975f84fe" />

# Overview
[LangSearch](https://langsearch.com) offers two Free APIs: the Web Search API and the Semantic Rerank API, designed to connect your LLM applications to the world, and access clean, accurate, high-quality context.

For individuals and small teams, we offer free access as we build AGI together.

# Core APIs
## [Free Web Search API ->](https://docs.langsearch.com/api/web-search-api)
Get enhanced search details from billions of web documents, including news, images, videos, and more.

- Hybrid search combining keywords and vectors for enhanced accuracy.
- Long-text summaries from raw content, with support for markdown formatting for improved readability.
- Perfect for individuals and small teams, offering free access as we build AGI together.

## [Free Semantic Rerank API ->](https://docs.langsearch.com/api/semantic-rerank-api)
Improve the accuracy of your search results with semantic reranking.
- Boosts any existing keyword or vector search system without requiring significant changes to your infrastructure.
- Provides a powerful semantic layer to refine results, ensuring higher relevance.

# Core Products
## [LangSearch Database](https://docs.langsearch.com/product/langsearch-database)

A Hybrid Search Database for the Next Generation of Search.

![image](https://github.com/user-attachments/assets/723780de-ec61-4fb5-ae65-0b69f47a78dd)

LangSearch Database is a cutting-edge hybrid search database designed to provide highly relevant and accurate search results by combining the strengths of traditional keyword-based search and advanced vector-based search. It is optimized for AI-driven applications, ensuring that search systems not only return the most relevant results but also understand context and intent. Whether you're dealing with large-scale data or fine-tuning your search experience, LangSearchDB delivers powerful, high-performance search capabilities.
LangSearch Database serves as the backbone for various search applications, including the Web Search API, providing seamless access to billions of web documents, images, videos, and more. It integrates both keyword and semantic search technologies to give users access to high-quality, contextually accurate information.

[See More Features..](https://docs.langsearch.com/product/langsearch-database)

## [LangSearch Reranker](https://docs.langsearch.com/product/langsearch-reranker)

Intelligent Ranking for Enhanced Search Results.

![image](https://github.com/user-attachments/assets/ca489f7c-e76b-47d5-ae41-20b594469284)

LangSearch Reranker is a powerful text-semantic-based ranking model designed to improve the accuracy of search results in search applications and retrieval-augmented generation (RAG) applications. By leveraging deep learning technologies and the Transformer architecture, LangSearch Reranker performs secondary optimization of the initial ranking results, enhancing relevance and overall user experience. Whether you’re using keyword search, vector search, or hybrid search, LangSearch Reranker helps deliver highly relevant results with precise ranking.

[See More Features..](https://docs.langsearch.com/product/langsearch-reranker)

# Quick Start
## Get API key

First, create an account and grab a free API key.

[https://langsearch.com/api-keys](https://langsearch.com/api-keys)

## Try Web Search API

### cURL
```bash
curl --location 'https://api.langsearch.com/v1/web-search' \
--header 'Authorization: Bearer YOUR-API-KEY' \
--header 'Content-Type: application/json' \
--data '{
    "query": "tell me the highlights from Apple 2024 ESG report",
    "freshness": "noLimit",
    "summary": true,
    "count": 10
}'
```

### Python
```python
import requests
import json

url = "https://api.langsearch.com/v1/web-search"

payload = json.dumps({
  "query": "tell me the highlights from Apple's 2024 ESG report",
  "freshness": "noLimit",
  "summary": True,
  "livecrawl": True,
  "count": 10
})
headers = {
  'Authorization': 'Bearer YOUR-API-KEY',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```

## Try Semantic Rerank API

### cURL
```bash
curl --location 'https://api.langsearch.com/v1/rerank' \
--header 'Authorization: Bearer YOUR-API-KEY' \
--header 'Content-Type: application/json' \
--data '{
    "model": "langsearch-reranker-v1",
    "query": "Tell me the key points of Alibaba 2024 ESG report",
    "top_n": 2,
    "return_documents": true,
    "documents": [
        "Alibaba Group released the 2024 Environmental, Social, and Governance (ESG) report, detailing the progress made in various ESG areas over the past year. The report shows that Alibaba has steadily advanced its carbon reduction efforts, with the group'\''s net carbon emissions and carbon intensity of the value chain continuing to decrease. The group also continues to leverage digital technologies and platform capabilities to support accessible development, healthcare, aging-friendly services, and small and micro enterprises. Alibaba Group'\''s CEO, Wu Yongming, stated in the report: '\''The core of ESG is about becoming a better company. Over the past 25 years, the actions related to ESG have formed the foundation of Alibaba, which is just as important as the commercial value we create. While the group is focused on the dual business strategies of '\''user-first'\'' and '\''AI-driven,'\'' we also remain committed to ESG as one of Alibaba'\''s cornerstone strategies. Alibaba has made solid progress in reducing carbon emissions.'\''",
        "The core of ESG is about becoming a better company. This year marks the 25th anniversary of Alibaba. Over the past 25 years, Alibaba has adhered to its mission of '\''making it easy to do business everywhere,'\'' supporting the prosperity of domestic e-commerce; maintaining an open ecosystem, with the Magic搭 community opening over 3,800 open-source models; assisting in rural revitalization, having sent 29 rural special envoys to 27 counties; promoting platform carbon reduction, pioneering a Scope 3+ carbon reduction plan; and engaging in employee welfare, with the '\''Everyone 3 Hours'\'' initiative making small but meaningful changes... These actions form the foundation of Alibaba, which is just as important as creating commercial value. I hope that every Alibaba employee will learn to make difficult but correct choices, maintaining foresight, goodwill, and pragmatism. A better Alibaba is worth our collective efforts. Alibaba'\''s mission, unchanged for over 20 years, is to make it easy to do business in the world. Today, this mission takes on new significance in this era."
    ]
}'
```

### Python
```python
import requests
import json

url = "https://api.langsearch.com/v1/rerank"

payload = json.dumps({
  "model": "langsearch-reranker-v1",
  "query": "Tell me the key points of Alibaba 2024 ESG report",
  "top_n": 2,
  "return_documents": True,
  "documents": [
    "Alibaba Group released the 2024 Environmental, Social, and Governance (ESG) report, detailing the progress made in various ESG areas over the past year. The report shows that Alibaba has steadily advanced its carbon reduction efforts, with the group's net carbon emissions and carbon intensity of the value chain continuing to decrease. The group also continues to leverage digital technologies and platform capabilities to support accessible development, healthcare, aging-friendly services, and small and micro enterprises. Alibaba Group's CEO, Wu Yongming, stated in the report: 'The core of ESG is about becoming a better company. Over the past 25 years, the actions related to ESG have formed the foundation of Alibaba, which is just as important as the commercial value we create. While the group is focused on the dual business strategies of 'user-first' and 'AI-driven,' we also remain committed to ESG as one of Alibaba's cornerstone strategies. Alibaba has made solid progress in reducing carbon emissions.'",
    "The core of ESG is about becoming a better company. This year marks the 25th anniversary of Alibaba. Over the past 25 years, Alibaba has adhered to its mission of 'making it easy to do business everywhere,' supporting the prosperity of domestic e-commerce; maintaining an open ecosystem, with the Magic搭 community opening over 3,800 open-source models; assisting in rural revitalization, having sent 29 rural special envoys to 27 counties; promoting platform carbon reduction, pioneering a Scope 3+ carbon reduction plan; and engaging in employee welfare, with the 'Everyone 3 Hours' initiative making small but meaningful changes... These actions form the foundation of Alibaba, which is just as important as creating commercial value. I hope that every Alibaba employee will learn to make difficult but correct choices, maintaining foresight, goodwill, and pragmatism. A better Alibaba is worth our collective efforts. Alibaba's mission, unchanged for over 20 years, is to make it easy to do business in the world. Today, this mission takes on new significance in this era."
  ]
})
headers = {
  'Authorization': 'Bearer YOUR-API-KEY',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```

# Why LangSearch?
LangSearch leverages a hybrid search database that combines the power of keyword and vector searches, using advanced LangSearch Reranker model to further enhance result accuracy. Whether you’re enhancing web search or optimizing reranking, LangSearch provides the tools to ensure your search systems yield more accurate, meaningful results.
