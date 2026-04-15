---
name: rest-api-skill
description: Use this skill to perform REST operations to a given request URL.
---

# rest-api-skill
- this skill allows the agent to perform rest operations using the `curl` command-line tool.
- **Input**: Take the json format as input and perform rest operations using `curl` command. Take this as an example:
  **POST Requests**
    curl -X POST "https://httpbin.org/post" -H "accept: application/json" 
- 2. **Output**: Display the response in the chat window. 
