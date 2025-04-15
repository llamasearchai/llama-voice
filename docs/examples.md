# Examples

This page provides examples of using Llama Voice for various tasks.

## Basic Usage

```python

from llama_voice import Client

# Initialize client
client = Client()

# Use the client
result = client.process("example input")
print(result)
```

## Advanced Usage

```python
from llama_voice import Client
import asyncio

# Initialize client with custom configuration
client = Client(
    config={
        "timeout": 60,
        "max_retries": 3,
        "log_level": "debug"
    }
)

# Process multiple inputs concurrently
async def process_batch(inputs):
    tasks = [client.process_async(inp) for inp in inputs]
    return await asyncio.gather(*tasks)

# Run async processing
inputs = ["input1", "input2", "input3", "input4"]
results = asyncio.run(process_batch(inputs))

# Print results
for i, result in enumerate(results):
    print(f"Result {i+1}: {result}")
```

For more examples, check out the [examples directory](https://github.com/llamasearchai/llama-voice/tree/main/examples) in the GitHub repository.
