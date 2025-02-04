# Text2SqlViaLm
Enlisgh text to SQL code

Using language model: "Qwen2.5-Coder-32B-Instruct-Q8_0.gguf"

The following is a snippet of the jupyer code file.
Looks like this LM is correcting the "Gold Standard"!:

```
iter 19
llama_perf_context_print:        load time =    1612.26 ms
llama_perf_context_print: prompt eval time =     107.85 ms /    47 tokens (    2.29 ms per token,   435.77 tokens per second)
llama_perf_context_print:        eval time =    7011.53 ms /   109 runs   (   64.33 ms per token,    15.55 tokens per second)
llama_perf_context_print:       total time =    7269.09 ms /   156 tokens
<|im_start|>system
You are an text to SQL query translator. Users will ask you questions in English and you will generate a SQL query based on the provided SCHEMA.
SCHEMA:
CREATE TABLE table_30120560_1 (civil_parish VARCHAR, area__acres__ VARCHAR)<|im_end|>
<|im_start|>user
which cilvil parishes have areas of 405?<|im_end|>
<|im_start|>assistant
Based on the provided schema, the SQL query to find civil parishes with an area of 405 acres would be:

`sql
SELECT civil_parish
FROM table_30120560_1
WHERE area__acres__ = '405';
`

Note: The `area__acres__` column is of type `VARCHAR`, so the value '405' is enclosed in single quotes. If the column were of a numeric type, the quotes would not be necessary.
----------------------------------
Gold Standard:
 SELECT civil_parish FROM table_30120560_1 WHERE area__acres__ = 405
----------------------------------
Took 11.548148155212402 seconds.
====================================================================

998 Tue Feb  4 13:50:32 2025
```
