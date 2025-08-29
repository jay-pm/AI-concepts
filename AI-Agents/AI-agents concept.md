**Whats an AI agent?**
  An AI model capable of reasoning, planning, and acting on a set of actions by interacting with its environment.

**Formal definition:** An agent is a system that leverages an AI model to interact with its environment to achieve a user-defined objective. It combines reasoning, planning, and the execution of actions (often via external tools) to fulfill tasks.

AI agent have two main parts: 
1. The brain: The AI model that handles reasoning and planning. It decides which actions to take based on the situation.
2. The body: Representing everything the agent is able to do, through tools.

These systems are agentic, because they have agency, which means they can interact with the real world, using these capabilities and tools.

The engineering divide the work: the AI team will build the brain (model), the integration team will develop the tools, and the systems team will create the orchestration layer.

Criteria for using AI agents:
1. require complex decision making
2. require heavy reliance on unstructured data
3. Have difficult to maintain rules
4. require adaptive problem solving

Build Vs Buy:  

Off-the-Shelf Tools  
Tackling a specific domain or use-case (e.g. AI-assisted coding)  
Mature, well-tested solution already exists in market  
Want to minimize maintenance overhead  

Low-Code/No-Code Platforms:  
Need some customization but not complete control  
Workflows are moderately complex but follow common patterns  
Want business users to modify the agent without engineering help  
Need to integrate with existing systems quickly

Agent Frameworks (Build):  
Use case involves proprietary systems  
Handling sensitive data  
Agent is core to competitive advantage  
No existing solution meets specialized requirements  
Need complete control overagent's behavior and evolution  

**The Agentic Trinity: Model, Tools, and Orchestration**  
An AI agent is made of three components: Model, Tools, and Orchestration layer  
The Model—it understands language, reasons through a given problem, and outlines steps to solve it.  
Tools—they connect the agent to the outside world, accessing data, performing actions, and making things happen.  
Orchestration layer—it coordinates everything, keeping the agent moving forward towards its goal. Let’s zoom in on orchestration. We defined the orchestration layer as a continuous loop that controls how an agent processes information, remembers information, and makes decisions.  
The orchestration layer maintains memory, state, reasoning, and planning.  
While there are different architectures by which this happens, a useful framework for understanding orchestration is the **Thought-Action-Observation** cycle.  


**The TAO cycle:**  
TAO (Thought-Action-Observation) cycle is the agent's problem-solving method - a continuous cycle where each observation informs the next thought.  
Thought: The model decides the next step based on the user prompt.  
Action: The agent takes an action, by calling the tools at their disposal.  
Observation: The model reflects on the response from the tool. Feeding into the next set of thoughts and actions  


