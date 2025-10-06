**Prompt engineering** is about crafting clear and concise instructions/prompts that guide the behavior of a language model (LLM) efficiently to produce the desired output.

**Message Roles:**  
Every message has one of three roles:  
 - System message : guides model behavior
 - User message: prompt from the user
 - Assistant message: response to the user prompt

**Control Parameters:**  
**temparature** controls the response/answer's randomness. 2 for highest randomness, 1 for No randomness  
**max_tokens** controls the response length

**Key principles**  
- Use appropriate action verbs
  - Use verbs like write, explain, evaluate instead of think, feel, try etc.
- Provide detailed and precise instructions
  - Provide specific, descriptive and detailed instruction regarding context, output length, format and style and audience.
  - Apply limit on words, sentences or paragraphs.
  - You can do it via max_tokens (output can't pass it and the response might lead to imcomplete or cut) or directly in prompt (output may bypass it but the response will be complete)
- Use well-structured delimited prompts
  - Use delimiters (e.g., triple backticks, parentheses, brackets) to structure prompts clearly, especially when including input data for tasks like text summarization. This technique helps the model identify and process the input correctly. Mention which delimiters are used.
  - Embedd variables into prompts using Python's f-strings, allowing for dynamic prompt creation.
 
**Type of Prompts**  
- Zero-shot prompting :
    - Providing a prompt without any example
    - model generates response based on it's knowledge
    - ideal for quick and uncomplicated tasks
- One-shot prompting :
    - provide the model a single example
    - useful for consistent formatting or style
- Few-shot prompting (more than one example)
    - provide more than one example
    - powerful for contextual tasks
