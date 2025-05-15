## Naive Context Protocol
This is a single-page spec for solving the context problem for large language models.

### Why?
I realize this is a competing standard to Model Context Protocol,
But after spending many hours implementing simple MCP servers and following the development of the protocol,
I think MCP sucks, so I started making NCP everything, I believe, MCP should've been.

Feedback & contribution welcome.

Goals:
- Simple to implement
- Use existing standards and best practices
- Hostable on a basic HTTP server
- Community driven

![Standard](https://imgs.xkcd.com/comics/standards_2x.png)


### Spec
- Use OpenAPI for tool discovery (by default hosted on `/.well-known/ncp-tools.json` but can be configured on the client)
- Use JSON Schema for tool definition (With OpenAPI)
- Use HTTP for tool calling
- Use OpenAPI for defining Authorization

`ncp-tools.json` is an OpenAPI specification for the tools that are available on this server 
and how to call them.

#### Resources
Within the `ncp-tools.json`, use OpenAPI tags to define:
- `resource_list` to annotate the endpoint for listing resources
- `resource_read` to annotate the endpoint for fetching the resource

#### Prompts
Within the `ncp-tools.json` use OpenAPI tags to define:
- `prompt_list` to annotate the endpoint for listing prompts
- `prompt_read` to annotate the endpoint for fetching the prompt

### Contribution
Please create a pull request.

Tasks:
- [ ] Add examples to the spec
- [ ] Make an example server (hosted)
- [ ] Make an MCP server that uses NCP behind the scene to make adoption easier
- [ ] Expand on the Authorization
- [ ] Create a reference implenetation (if needed)
- [ ] Define the input & output for resource endpoints
- [ ] Define the input & output for the prompt endpoints


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
