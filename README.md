# User-study-dataset
A user study dataset of generative search (Bing Chat). 

The detail about the user study is introduced in the paper:
*Yidong Liang, Zhijing Wu, Fan Zhang, Dandan Song and Heyan Huang. 2025. [How Users Interact with Generative Information Retrieval Systems: A Study of User Behavior and Search Experience](https://dl.acm.org/doi/10.1145/3726302.3729998). In SIGIR'25.*

Please cite our SIGIR'25 paper if you use this data. Thanks!


## Data Description
### `task.csv`

| Field	| Type	| Description |
| ------ | ------ | ------ |
| task_id | #24 indexs | Index used to distinguish tasks |
| task_content | text | Text description of the task |
| type | text | Tasks are divided into three types: Factual, Mis-Factual and Exploratory |
---

### `task_query_image.tsv`


| Field	| Type	| Description |
| ------ | ------ | ------ |
| user | #40 indexs | Index used to distinguish users |
| task_id | #24 indexs | Index used to distinguish tasks |
| query_id | index | inner-id of the search query |
| query | text |the query text |
| response | text| Bing Chat's response |
| pre_familiar | 1(low)~5(high) | user perceived task familiarity |
| pre_difficulty | 1(low)~5(high) | user perceived task difficulty |
| satisfactory | 1(low)~5(high) | user’s satisfaction feedback on a search session | 
| success_self| 1(low)~5(high) | user’s success feedback on a search session | 
| credibility | 1(low)~5(high) | user’s feedback on responses reliability |
| click | [json] | Information related to the user's click operation, including the URL, the link id, rank, and type  |
| cumulative_sat | 1(low)~5(high) | User's cumulative satisfaction for the current query |
---

**click JSON schema:**
```json
{
  "url": "string",
  "link_id": "integer",
  "rank": "integer",(Optional, only present when clicking on sup links)
  "text": "string",(Optional, only present when clicking on text links)
  "type": "learn/sup/text-link"
}

