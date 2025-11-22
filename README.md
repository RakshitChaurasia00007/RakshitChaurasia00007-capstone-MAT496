# Capstone Project - MAT496

 # Car Knowledge Assistant with 3-Expert Verification System using LangGraph



 ## Overview of The whole CAPSTONE PROJECT

### Well! Our Car Knowledge Assistant uses am AI-powered Web Search and a unique 3-expert verification system to answer automotive questions with the verified and reliable information.​

When you just ask any question about the car maintenance, repairs, features, or even just troubleshooting:

Expert 1 => (Primary Mechanic) : Searches across the web and provides an initial detailed answer​.

Expert 2 => (Verification Specialist) : Cross-checks all the information for accuracy and then identifies any errors​.

Expert 3 => (Conflict Resolver) : Reviews both the experts, resolves conflicts, and then delivers the final authoritative answer​.

My main focus was to make the overall system ,ust get built using the LangGraph for the multi-agent workflow orchestration, Tavily web search for real-time automotive information retrieval, and structured output with Pydantic models for the consistent, safety-focused responses.​

Results for the programme are displayed in a clean dashboard showing the confidence levels, verification status, issues found, and the source citations ensuring you get the trustworthy car maintenance guidance. This programme is highly recommended to every CAR Enthusiast. 


## Reason for picking up this specific project & also Explaining how this project is aligned with the Course Content.

### I wanted to build something practical that solves a real life problem I've experienced finding reliable car maintenance information online often means sifting through conflicting advice, outdated forum posts, and unreliable sources.​ Hence below is the idea which has risen 

The 3-expert verification system idea came from how mechanics actually work in real life : one diagnoses, another double-checks, and then a senior mechanic who makes the final call. I thought, "Why not let's replicate this whole senario of the safety-critical workflow using AI?"​​

This project let me explore how multiple AI agents that can collaborate on a single problem, each with specialized roles something which I found fascinating after learning about LangGraph's multi-agent capabilities.​


## Well! Now How This Project Aligns with Our LLM Course Content ?

This project directly applies every major concept from MAT496:

1. LangGraph (State, Nodes, Graph)

I have built a StateGraph with 3 agent nodes (Expert 1, 2, 3) connected by edges in a sequential workflow​​.

Used VerificationState to pass information between the agents (search results, responses, confidence levels)​​.

2. Prompting

Each expert has a custom system prompts defining their role, responsibilities, and output format​.

Expert 1 focuses on giving the detailed answers, Expert 2 focuses on the verification part & at last Expert 3 focuses on conflict resolution​.

3. Structured Output

Implemented Pydantic models (ExpertResponse, CarExpert) with with_structured_output() to ensure consistent, parseable responses​.

4. Tool Calling & Web Search

Integrated Tavily web search as the tool that agents invoke to retrieve real-time automotive information​.

Each expert calls the search tool with different queries (initial research vs. verification)​.

5. RAG-like Behavior

Agents search the web for automotive documentation, retrieve context, and generate answers based on that retrieved information​.

6. LangSmith Debugging 

The structured workflow makes it easy to trace which expert made what decision and why​.

The creativity comes from the multi-agent verification pattern—instead of a single LLM response, three specialized agents collaborate to ensure accuracy and the safety, which is critical part for the car maintenance advice. 

Hence, this is how our project aligns with the concepts of MAT- 496 course. 

## Well ! What are the Plans which I have for completing my whole Project ? 

I plan to execute the working of my project by using the below steps.

[DONE] =>  Step 1 will involve setting up the development environment and notebook structure, including installing required libraries such as (LangGraph, LangChain, Tavily, OpenAI), then configuring API keys for OpenAI and Tavily, after that we will be importing the dependencies, and initializing the LLM and the search tools.

[DONE] =>  Step 2 will involve implementing the 3-expert verification system using LangGraph, including defining Pydantic models for the expert responses and state management, creating specialized instruction prompts for each expert (Primary Mechanic, Verification Specialist, Conflict Resolver), building the three expert functions, and wiring the StateGraph with the nodes and edges to create the sequential workflow.

[DONE] =>  Step 3 will involve integrating web search and retrieval tools, including implementing the Tavily search function to fetch the automotive information, adding Wikipedia loader for the additional context if needed, and then ensuring each expert can call search tools with different verification-focused queries.

[TODO] =>  Step 4 will involve building the user interface and example demonstration, including creating the Markdown dashboard function to display the results with the confidence levels and verification status, adding an input cell for user questions, implementing the graph invocation with progress tracking, and running a complete example query to showcase the entire 3-expert workflow.

[TODO] =>  Step 5 will involve documentation, and final polish, including writing the complete README.md with project overview and alignment with course content,  adding source citations and safety warnings, testing the entire workflow end-to-end in Google Colab, and final code cleanup with comments.