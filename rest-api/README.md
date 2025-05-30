
# TrustGraph REST API Notebooks

TrustGraph provides an API gateway which serves HTTP on port `8088` which exposes many internal services to REST APIs.

> [!NOTE]
> TrustGraph must be running prior to using the REST API. Follow the [Getting Started Guide](https://trustgraph.ai/docs/getstarted) or the deployment instructions in the [Configuration UI](https://config-ui.demo.trustgraph.ai/) to launch TrustGraph with either Docker, Podman, Minikube, or Google Cloud.

## Notebooks

- [agent.ipynb](agent.ipynb) - Demonstrates a client of the agent API.
  Invokes an agent interaction to get a response.
- [embeddings.ipynb](embeddings.ipynb) - Invokes the embedding API,
  acquiring a vector embedding of a piece of text.
- [graph-rag.ipynb](graph-rag.ipynb) - invokes the Graph RAG API, responding
  to a question using the knowledge graph.
- [graph-visualization.ipynb](graph-visualization.ipynb) - fetches
  triples from the triple store and produces a graph visualisation.
- [graph-visualization-2.ipynb](graph-visualization-2.ipynb) - fetches
  triples from the triple store and produces a graph visualisation.
- [llm.ipynb](llm.ipynb) - invokes the text-completion service which calls
  a simple LLM endpoint
- [load-document.ipynb](load-document.ipynb) - loads a PDF document into
  the processing pipeline.  This example adds extra metadata which is
  associated with knowledge extracted from the document.
- [load-text.ipynb](load-text.ipynb) - loads a text document into
  the processing pipeline.  This example adds extra metadata which is
  associated with knowledge extracted from the document.
- [prompt.ipynb](prompt.ipynb) - invokes the prompt service.  The prompt
  service invokes an LLM using templates which are managed by the prompt
  service.  This allows prompt templates to be tailored without changing
  components which invoke the prompt service.  This example invokes a
  prompt which returns text.
- [prompt2.ipynb](prompt2.ipynb) - Another prompt service example, this one
  invokes a template which returns validated, structured data.
- [triples-query.ipynb](triples-query.ipynb) - uses the triple store API
  to fetch triples from the triple store.

## API mechanisms

### Authentication

There is currently no authentication.  The API gateway should not be exposed
to the internet.  In the future an authentication token mechanism will be
introduced

### Methods

All APIs accept a POST method.

### Status codes

All APIs return a 200 status code for success.  Other status codes e.g.
400 and 500 are used for request errors and internal failures.

### Error handling

With the except of the document load / text load calls, errors are
reported with a JSON response.

```
{
    "error": "Error message here...
}
```

