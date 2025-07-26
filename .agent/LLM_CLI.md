=== llm prompt* --help ===
Usage: llm prompt [OPTIONS] [PROMPT]

  Execute a prompt

  Documentation: https://llm.datasette.io/en/stable/usage.html

  Examples:

      llm 'Capital of France?'
      llm 'Capital of France?' -m gpt-4o
      llm 'Capital of France?' -s 'answer in Spanish'

  Multi-modal models can be called with attachments like this:

      llm 'Extract text from this image' -a image.jpg
      llm 'Describe' -a https://static.simonwillison.net/static/2024/pelicans.jpg
      cat image | llm 'describe image' -a -
      # With an explicit mimetype:
      cat image | llm 'describe image' --at - image/jpeg

  The -x/--extract option returns just the content of the first ``` fenced
  code block, if one is present. If none are present it returns the full
  response.

      llm 'JavaScript function for reversing a string' -x

Options:
  -s, --system TEXT               System prompt to use
  -m, --model TEXT                Model to use
  -d, --database FILE             Path to log database
  -q, --query TEXT                Use first model matching these strings
  -a, --attachment ATTACHMENT     Attachment path or URL or -
  --at, --attachment-type <TEXT TEXT>...
                                  Attachment with explicit mimetype,
                                  --at image.jpg image/jpeg
  -T, --tool TEXT                 Name of a tool to make available to the
                                  model
  --functions TEXT                Python code block or file path defining
                                  functions to register as tools
  --td, --tools-debug             Show full details of tool executions
  --ta, --tools-approve           Manually approve every tool execution
  --cl, --chain-limit INTEGER     How many chained tool responses to allow,
                                  default 5, set 0 for unlimited
  -o, --option <TEXT TEXT>...     key/value options for the model
  --schema TEXT                   JSON schema, filepath or ID
  --schema-multi TEXT             JSON schema to use for multiple results
  -f, --fragment TEXT             Fragment (alias, URL, hash or file path) to
                                  add to the prompt
  --sf, --system-fragment TEXT    Fragment to add to system prompt
  -t, --template TEXT             Template to use
  -p, --param <TEXT TEXT>...      Parameters for template
  --no-stream                     Do not stream output
  -n, --no-log                    Don't log to database
  --log                           Log prompt and response to the database
  -c, --continue                  Continue the most recent conversation.
  --cid, --conversation TEXT      Continue the conversation with the given ID.
  --key TEXT                      API key to use
  --save TEXT                     Save prompt with this template name
  --async                         Run prompt asynchronously
  -u, --usage                     Show token usage
  -x, --extract                   Extract first fenced code block
  --xl, --extract-last            Extract last fenced code block
  -h, --help                      Show this message and exit.

=== llm aliases --help ===
