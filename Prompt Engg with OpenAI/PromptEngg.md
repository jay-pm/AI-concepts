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
- Use well-structured delimited prompts
   - Apply limit on words, sentences or paragraphs.
   - You can do it via max_tokens (output can't pass it and the response might lead to imcomplete or cut) or directly in prompt (output may bypass it but the response will be complete)
