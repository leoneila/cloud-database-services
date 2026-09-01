# Lab 2: Build Enterprise AI Agents with Oracle Private Agent Factory

## Introduction

In this lab, you will explore **Oracle AI Database Private Agent Factory**, a no-code environment for building, deploying, and managing AI agents grounded in enterprise data.

You will begin by accessing Private Agent Factory and creating a **Knowledge AI Agent** grounded in workshop documentation. You will then create a **Deep Data Research Agent** for more comprehensive research-oriented responses. Finally, you will use **Agent Builder** to create a custom AI agent that connects to the managed MCP Server configured in Lab 1.

This lab demonstrates how Oracle AI Database Private Agent Factory can combine enterprise knowledge, AI models, agent workflows, and Model Context Protocol (MCP) tools while keeping enterprise data and database access governed.

**Estimated Time:** 20 minutes

### Objectives

In this lab, you will:

- Access Oracle AI Database Private Agent Factory.
- Create a Knowledge AI Agent grounded in enterprise documentation.
- Create a Deep Data Research Agent for research-oriented questions.
- Create a custom AI agent using Agent Builder.
- Connect a custom agent to the managed MCP Server configured in Lab 1.
- Test grounded responses using natural language.

### Prerequisites

Before starting this lab, verify that the following resources are available:

- Access to the Oracle AI Database Private Agent Factory workshop environment.
- The workshop user credentials provided to you.
- The enterprise documents provided for this workshop.
- Access to the AI and embedding models configured for the workshop.
- The OCI Database Tools MCP Server configured in **Lab 1: Configure MCP Server for Oracle AI Database**.
- The MCP Server authentication information required by the workshop.

> **Note:** The database, AI models, network access, IAM configuration, and supporting resources required for this workshop are provided as part of the workshop environment unless otherwise specified.

## Task 1: Access Oracle AI Database Private Agent Factory.

In this task, you will access Oracle AI Database Private Agent Factory and familiarize yourself with the capabilities that you will use throughout this lab.

1. Open the **Oracle AI Database Private Agent Factory** URL provided for the workshop.

   > **Note:** Your instructor or workshop environment provides the URL and credentials required to access Private Agent Factory.

2. Sign in using the credentials provided for the workshop.

3. After signing in, verify that the Private Agent Factory home page is displayed.

   <!-- ![Private Agent Factory home page](./images/private-agent-factory-home.png) -->

4. Review the available Private Agent Factory capabilities.

   Depending on the workshop environment and installed version, you will use capabilities for:

   - Creating and managing **Knowledge Agents**.
   - Creating **Deep Data Research Agents**.
   - Managing enterprise **Data Sources**.
   - Building custom agent workflows with **Agent Builder**.
   - Configuring external **MCP Servers**.
   - Testing agents and workflows in **Playground**.

5. Locate the area used to manage **Data Sources**.

6. Verify that you can access the area used to create agents.

7. Locate **Agent Builder**.

8. Locate **MCP Servers**.

   You will use these capabilities later in this lab to build a custom agent that can interact with Oracle AI Database through the MCP Server created in Lab 1.

> **Note:** The exact placement of navigation items can vary slightly depending on the Private Agent Factory release used by the workshop.

You are now ready to create your first enterprise AI agent.

## Task 2: Create a Knowledge AI Agent

In this task, you will create a Knowledge AI Agent grounded in enterprise documentation.

A Knowledge Agent uses enterprise content as a knowledge source so that responses can be grounded in information provided by your organization rather than relying only on the language model's general knowledge.

### Prepare the Knowledge Source

1. In Private Agent Factory, navigate to **Data Sources**.

2. Click the option to create a new data source.

3. Select the file-based data source option.

4. Enter a name for the data source.

   For example:

   ```text
   Workshop Enterprise Knowledge
   ```

5. Enter a description.

   For example:

   ```text
   Enterprise documentation used by the workshop Knowledge Agent
   ```

6. Upload the enterprise documentation provided for this workshop.

   <!-- ![Upload workshop documentation](./images/upload-knowledge-documents.png) -->

7. Review the selected documents and start the data-source processing operation.

8. Wait for Private Agent Factory to process the uploaded content.

   During processing, Private Agent Factory prepares the content so that it can be used as a source of knowledge by an AI agent.

9. Verify that the data source is ready before continuing.

   > **Important:** Do not continue until processing of the workshop documents has completed successfully.

### Create the Knowledge Agent

10. Navigate to the area used to create and manage agents.

11. Select **Knowledge Agent**.

12. Click the option to create a new Knowledge Agent.

13. Enter the following information:

    | Field | Value |
    | --- | --- |
    | Name | `Enterprise Knowledge Agent` |
    | Description | `Answers questions using the workshop enterprise documentation` |

14. Select the data source created earlier:

    ```text
    Workshop Enterprise Knowledge
    ```

15. Select the language model configured for the workshop environment.

16. Review the remaining agent settings and retain the workshop defaults unless instructed otherwise.

17. Configure the agent instructions, if available.

    For example:

    ```text
    Answer questions using the provided enterprise documentation.
    Base your response on the available knowledge sources.
    If the requested information is not available in the source material,
    clearly state that the information could not be found.
    ```

18. Save the agent configuration.

19. Publish or prepare the Knowledge Agent as required by the Private Agent Factory interface.

20. Wait until the agent is ready.

### Test the Knowledge Agent

21. Open the Knowledge Agent in the chat or testing interface.

22. Enter a question that can be answered using the uploaded workshop documentation.

   > **Note:** Use a question appropriate for the enterprise documents supplied with the workshop.

23. Submit the question.

24. Review the response.

25. Verify that the answer is based on information contained in the uploaded documents.

26. If references or sources are displayed, review them and verify that the response points to the appropriate workshop documentation.

27. Ask a follow-up question related to the first response.

28. Verify that the Knowledge Agent continues to use the configured enterprise knowledge source when answering.

You have now created an AI agent grounded in private enterprise documentation.

## Task 3: Create a Deep Data Research AI Agent

In this task, you will create a **Deep Data Research Agent**.

A Deep Data Research Agent is designed for questions that require broader investigation and synthesis across available enterprise information. Instead of returning only a short retrieval-based response, the agent can perform a research-oriented workflow and produce a more comprehensive answer grounded in the configured data.

### Prepare the Research Data

1. Navigate to **Data Sources**.

2. Verify that the file data source used in Task 2 is available and ready.

3. If the workshop provides a separate set of research documents, create an additional file data source and upload those documents.

   For example:

   ```text
   Workshop Research Documents
   ```

4. Wait until processing of all required documents has completed successfully.

### Create the Deep Data Research Agent

5. Navigate to the area used to create agents.

6. Select **Deep Data Research Agent**.

7. Click the option to create a new Deep Data Research Agent.

8. Enter the following information:

   | Field | Value |
   | --- | --- |
   | Name | `Enterprise Research Agent` |
   | Description | `Performs research across workshop enterprise documentation` |

9. Select the file data source that contains the workshop research documents.

10. Select the language model provided for the workshop.

11. Select the embedding model provided for the workshop, if prompted.

12. Review the available preparation or research configuration.

13. Retain the values specified for the workshop environment unless instructed otherwise.

14. Configure the agent instructions.

    For example:

    ```text
    Research the available enterprise information before answering.
    Synthesize relevant information from the available sources.
    Include supporting references when available.
    Do not invent information that is not supported by the enterprise data.
    ```

15. Save the agent.

16. Publish or prepare the Deep Data Research Agent.

17. Wait until the agent and its associated knowledge resources are ready.

   > **Note:** Preparing a Deep Data Research Agent can take longer than creating a basic agent because the associated enterprise content must be prepared for research and retrieval.

### Test the Deep Data Research Agent

18. Open the agent in its chat or testing interface.

19. Enter a research-oriented question that requires information from multiple parts of the workshop documentation.

   > **Note:** Your instructor may provide a specific research question based on the workshop dataset.

20. Submit the question.

21. Wait for the research workflow to complete.

22. Review the generated response.

23. Verify that the response synthesizes information from the configured enterprise sources.

24. Review any citations, references, or supporting sources presented with the response.

25. Compare the experience with the Knowledge Agent created in Task 2.

The Knowledge Agent provides grounded question answering over enterprise knowledge, while the Deep Data Research Agent is designed for more comprehensive research and synthesis across available information.

You have now created two different enterprise AI agents using Private Agent Factory.

## Task 4: Create a Custom AI Agent with MCP Tool

In this task, you will use **Agent Builder** to create a custom AI agent that interacts with Oracle AI Database through the managed MCP Server configured in Lab 1.

Model Context Protocol provides a standardized interface through which an AI agent can discover and invoke approved tools. In this workshop, the MCP Server provides the governed connection between Private Agent Factory and Oracle AI Database.

The resulting flow is:

```text
User
  |
  v
Oracle AI Database Private Agent Factory
  |
  v
Custom AI Agent
  |
  v
MCP Tool
  |
  v
OCI Database Tools MCP Server
  |
  v
Oracle AI Database
```

### Add the MCP Server to Private Agent Factory

1. In Private Agent Factory, navigate to **MCP Servers**.

2. Click the option to add a new MCP Server.

3. Enter a name for the MCP Server connection.

   For example:

   ```text
   Oracle Database MCP
   ```

4. Enter the MCP Server URL obtained in **Lab 1: Configure MCP Server for Oracle AI Database**.

   > **Note:** Use the managed Database Tools MCP Server created in Lab 1. Do not configure an Autonomous Database MCP Server for this workshop.

5. Select the authentication method required by the MCP Server configuration created in Lab 1.

6. Provide the required authentication information.

   > **Important:** Treat access tokens, client secrets, and other authentication credentials as sensitive information. Do not enter credentials into agent prompts or other fields that do not require them.

7. Test the MCP Server connection.

8. Verify that Private Agent Factory can successfully communicate with the MCP Server.

9. Review the tools discovered from the MCP Server.

   The available tools are determined by the MCP toolset configured on the managed MCP Server in Lab 1.

   <!-- ![MCP Server tools](./images/mcp-server-tools.png) -->

10. Save the MCP Server configuration.

### Create a Custom Agent Flow

11. Navigate to **Agent Builder**.

12. Click **Create New Flow**.

13. Enter a name for the flow.

    For example:

    ```text
    Database MCP Agent
    ```

14. Enter a description.

    For example:

    ```text
    Custom AI agent that interacts with Oracle AI Database using MCP
    ```

15. Create the flow.

16. On the Agent Builder canvas, add the components required for the custom agent workflow.

    The workflow should contain components equivalent to:

    ```text
    Chat Input -> Prompt -> Agent -> Chat Output
                               ^
                               |
                           MCP Server
    ```

    <!-- ![Custom MCP agent flow](./images/custom-mcp-agent-flow.png) -->

### Configure the Agent

17. Select the **Agent** component.

18. Select the language model provided for the workshop environment.

19. Configure the agent instructions.

    For example:

    ```text
    You are an enterprise database assistant.

    Use the available MCP tools whenever information must be retrieved
    from Oracle AI Database.

    Base database-related answers on information returned by the MCP tools.
    Do not invent database records, values, or query results.

    Provide clear and concise responses to the user.
    ```

20. Save the Agent configuration.

### Add the MCP Tools

21. Add an **MCP Server** component to the workflow.

22. Select the MCP Server connection configured earlier:

    ```text
    Oracle Database MCP
    ```

23. Review the tools available from the MCP Server.

24. Select only the tools required by this custom agent.

    > **Note:** Limiting an agent to the tools required for its intended task reduces unnecessary capabilities and helps maintain a governed agent workflow.

25. Connect the MCP Server component to the **Tools** input of the Agent component.

26. Verify that the remaining workflow components are connected correctly.

27. Save the custom agent flow.

### Test the MCP Connection in Playground

28. Open the completed workflow in **Playground**.

29. Enter a prompt that asks the agent about its available database capabilities.

    For example:

    ```text
    What database tools do you have available?
    ```

30. Submit the prompt.

31. Verify that the agent recognizes the tools exposed through the MCP Server.

32. Enter a natural-language question that requires information from the Oracle AI Database.

    > **Note:** Use a question that corresponds to the sample database objects and data provided with the workshop.

33. Submit the question.

34. Observe the agent execution.

35. Verify that the agent invokes an appropriate MCP tool rather than attempting to answer the database-specific question using only the language model.

36. Review the response returned by the agent.

37. Verify that the answer is based on information returned from Oracle AI Database.

### Verify the Custom Agent

You have now created a custom AI agent that can interact with Oracle AI Database through the managed MCP Server.

The workflow separates the AI agent from direct database connectivity:

```text
Private Agent Factory
        |
        | MCP
        v
OCI Database Tools MCP Server
        |
        | Database Tools Connection
        v
Oracle AI Database
```

The custom agent uses only the database capabilities exposed through the MCP Server and made available to the workflow.

This architecture enables AI applications to use enterprise database capabilities through a standardized MCP interface while database access remains governed independently from the agent.

## Acknowledgements

**Authors** 

* Leo Alvarado, Vishal Patil, Tammy Bednar, Product Management, Oracle Database Cloud Services, Multicloud 

**Last Updated Date** - August, 2026

