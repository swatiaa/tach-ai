# tach-ai
You can install it using npm install tach-ai 
Usage example : 
// Install first: npm install tach-ai
import { createClient } from 'tach-ai';

const client = createClient();

const stream = await client.chat.completions.create({
  model: 'MiniMaxAI/MiniMax-M2',
  messages: [{ role: 'user', content: 'Explain AI in 3 sentences' }],
  stream: true
});

for await (const chunk of stream) {
  const text = chunk.choices[0]?.delta?.content;
  if (text) process.stdout.write(text); // Live preview
}
or in ex.js
