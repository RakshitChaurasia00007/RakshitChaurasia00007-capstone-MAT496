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

[DONE] =>  Step 4 will involve building the user interface and example demonstration, including creating the Markdown dashboard function to display the results with the confidence levels and verification status, adding an input cell for user questions, implementing the graph invocation with progress tracking, and running a complete example query to showcase the entire 3-expert workflow.

[DONE] =>  Step 5 will involve documentation, and final polish, including writing the complete README.md with project overview and alignment with course content,  adding source citations and safety warnings, testing the entire workflow end-to-end in Google Colab, and final code cleanup with comments.


## Flow of the Project 

Environment setup & dependencies
Install LangGraph, LangChain, OpenAI, Tavily, Wikipedia libraries and configure API keys (OpenAI, Tavily) for LLM and web search functionality.​

User input handling & question preprocessing
Accept automotive questions through notebook interface and prepare the initial query for processing by the expert system.​

Pydantic data models (structured schemas)
Define CarExpert, ExpertResponse, SearchQuery, and VerificationState models to ensure consistent, validated responses across all expert nodes.​

Prompt design and refinement
Create specialized system prompts for each expert: Primary Mechanic (detailed answers), Verification Specialist (cross-checking), and Conflict Resolver (final authority).​

Expert 1 node: Primary Mechanic (information provider)
First agent searches web using Tavily, processes automotive context, and generates initial comprehensive answer with safety warnings and confidence ratings.​

Expert 2 node: Verification Specialist (cross-checker)
Second agent performs independent web search with verification-focused queries, cross-checks Expert 1's response, identifies factual errors or safety concerns, and lists issues found.​

Expert 3 node: Conflict Resolver (final authority)
Third agent reviews both previous experts' responses, resolves conflicts, integrates best information, adds critical missing details, and produces final authoritative answer with complete source citations.​

State management & transitions
LangGraph VerificationState passes car question, search context, and expert responses sequentially through the three-expert workflow using defined edges.​

LangGraph workflow integration (state, nodes, flow)
Build StateGraph with three expert nodes connected by sequential edges (START → Expert1 → Expert2 → Expert3 → END), compile the graph, and execute the verification pipeline.​

Dashboard generation & Markdown display
Format all three expert responses with confidence levels, verification status, issues found, and sources into a clean, color-coded Markdown dashboard with safety warnings.​

Testing, validation & final documentation
Run end-to-end tests with multiple automotive queries, refine prompts for accuracy, validate output quality, and complete README with project overview and usage instructions.​

This workflow shows the complete journey from setup to final verified automotive guidance, demonstrating how your 3-expert system collaborates using LangGraph's multi-agent architecture.


## VIDEO LINK & COCLUSION of The CAPSTONE Project
https://drive.google.com/file/d/1wrj4DmgVUCndH8kYa-T15fnO09DFLcAN/view?usp=sharing



## Conclusion
When I planned this Capstone Project, I set out to build a complete AI-powered automotive knowledge system that uses the LangGraph to coordinate the three specialized expert agents in a verification workflow—combining web search, structured output generation, multi-agent collaboration, and the safety-focused answer generation.​

After completing that the project, I believe I have fully achieved the goals I had set out in my plan.​

I followed each planned step systematically throughout my whole CAPSTONE PROJECT: From the environment setup and dependency installation, to designing the Pydantic models for structured responses, creating specialized prompts for each expert role, implementing the three-expert verification nodes (Primary Mechanic, Verification Specialist, Conflict Resolver), integrating Tavily web search for the real-time automotive information retrieval, building the LangGraph StateGraph workflow with sequential edges, and the finally creating a clean Markdown dashboard to display the  verified results with confidence levels and the  source citations.​

The final system successfully takes any of the automotive question, then processes it through the three independent expert agents who each search the web and reason over the retrieved context, identifies the conflicts or inaccuracies between the expert responses, resolves those conflicts intelligently, and then produces a comprehensive, verified answer with the complete source citations and safety warnings all displayed in an easy-to-understand format.​

I am satisfied with the outcome because this project covers all the core concepts taught in MAT496 by Mr. Ajit Sir: Prompting (specialized system instructions for each expert), Structured Output (Pydantic models with validation), Semantic Search (Tavily web retrieval), RAG-like behavior (context-based answer generation), Tool Calling (experts invoking search functions), and LangGraph (state management, nodes, workflow compilation).​

Beyond the course requirements, I extended the project with a unique creative element—the 3-expert verification system inspired by real-world automotive diagnostic workflows where multiple mechanics cross-check each other's assessments to ensure the safety-critical accuracy.​

This multi-agent approach demonstrates how LangGraph enables sophisticated workflows where the specialized agents collaborate autonomously to produce the more reliable outputs than any single LLM could have ever achieve alone.​

Overall, this project was a genuinely valuable learning for my experience that showed me how the concepts from this course can be applied to solve the  real-world problems where information accuracy and safety matters a lot. I would like to Thanks Mr. Ajit Sir for helping me learn each and every componet of this course and for solving each and every doubt regarding my whole CAPSTONE project.
 Thank you SIR I Enjoyed The LLM COURSE A LOT !​

