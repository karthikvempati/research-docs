AI Agent Harness - Presentation Guide | Internal working notes
AI Agent Harness
Complete presentation notes, narrative, architecture, examples, and
speaker guidance
Core thesis: We do not have a model capability gap. We have a harness gap.
This guide turns the full discussion into a presentation-ready story. It is deliberately structured as a
narrative rather than a catalog of AI terms: start with what a model actually does, show why context
matters, introduce skills and agents, expose the enterprise gap, and then reveal the AI Agent
Harness as the system that makes the pieces reliable, governable, reusable, observable, and
automatable.
Presentation goal
Do not sell another coding agent. Show how an enterprise can put a disciplined operating system
around increasingly powerful models and agents, while preserving organization-specific
knowledge, controls, workflows, and verification.
1. The Story You Are Telling
The audience should leave with one mental model: models are powerful prediction engines; context
steers them; skills package reusable capabilities; agents choose and execute capabilities in loops; and
the harness provides the enterprise system around those agents.
 Model: the reasoning/generation engine.
 Prompting: immediate instructions that steer behavior.
 Context engineering: deliberately assembling the information needed for the current task.
 Skill: a reusable, bounded capability or procedure.
 Agent: a goal-directed decision loop that can select skills/tools, inspect results, and continue.
 Harness: the surrounding architecture that supplies context, knowledge, tools, permissions,
policies, orchestration, verification, observability, state, and learning.
The transition
Everything already exists in fragments. The opportunity is not to invent one more primitive. It is
to put a method around the madness.
AI Agent Harness - Presentation Guide | Internal working notes
2. Opening: What a Model Actually Is
Start simple. Avoid saying the model is 'dumb.' That unnecessarily weakens the technology you are
about to build upon. The more accurate framing is that the base model is powerful but narrow: by
itself it has no durable organizational memory, no inherent business goal, no authority, and no
guaranteed ability to act.
Say it like this: At the bottom of everything is the model. A language model has learned
statistical patterns from very large amounts of text and other training data. At inference time, its
fundamental operation is predicting what token should come next given the context it currently
has. That sounds simple, but at scale it produces extremely powerful reasoning and generation
behavior. The important limitation is this: the model only knows what is represented in its
training and the context we give it now. It does not automatically know our business, our current
systems, our policies, or what actions it is authorized to take.
Then connect prompt engineering to prediction:
Say it like this: Prompt engineering is our first way of steering that prediction. We provide
instructions, constraints, examples, roles, and desired output so the model is more likely to
produce the behavior we want.
Do not over-explain
Say the next-token point once. Let it land. Then move to context. Repeating it makes the opening
feel defensive instead of insightful.
3. Context Engineering: Use the Mouse Story
This is your best simple example because the word 'mouse' is valid under multiple contexts. Each
answer can be reasonable and still be wrong for the user's actual intent.
Story
Say it like this: Imagine I have an assistant and I say, 'Go get me a mouse.' The assistant comes
back with a computer mouse. That is a completely reasonable interpretation. Then I say, 'I work
in a biology lab.' Now the assistant says, 'Why didn't you tell me that?' and comes back with a
laboratory mouse. Again, reasonable. Then I tell the assistant, 'I don't want to experiment on it. I
want a pet.' Now the assistant goes to a pet store and gets me a pet mouse. The task never
changed: get me a mouse. The context changed, and therefore the correct outcome changed.
Land the concept immediately:
Say it like this: That is context engineering. The model will fill missing information with
assumptions. Context engineering is the discipline of deliberately assembling the relevant
information, constraints, relationships, history, policies, and task state so the model does not
have to guess what we already know.
AI Agent Harness - Presentation Guide | Internal working notes
Enterprise context can include
 User identity, role, entitlements, and intent.
 Business definitions and domain terminology.
 Relevant source documents, policies, procedures, and prior decisions.
 Application, API, database, code, and schema context.
 Current workflow state and previous agent actions.
 Relationships between business entities.
 Constraints: what must happen, what must never happen, and what requires approval.
Key line
The quality of an agent is bounded not only by the intelligence of the model, but by the quality of
the context available at the moment of decision.
4. Skills: Package Reusable Business Capabilities
Introduce skills before agents. This makes the agent concept much easier to understand.
Say it like this: Instead of putting every instruction into one giant prompt, we package reusable
capabilities as skills. A skill is a bounded piece of know-how the system can invoke when needed.
Product-owner example
 JIRA ticket skill: knows how to create or update a ticket and populate the basic project fields.
 Story-description skill: turns the business request into a useful implementation-oriented
description.
 Acceptance-criteria skill: creates testable acceptance criteria, including expected and
unacceptable outcomes.
 Product-vision skill: supplies product intent, customer outcome, priorities, and relevant business
constraints.
Important terminology correction: an agent is not merely 'a set of skills.' An agent has access to skills
and chooses when and how to use them.
5. Agents: From One-Shot Generation to Goal-Directed Work
Say it like this: Now we add an agent. The agent has a goal. It has access to a set of skills and
tools. It can decide what to use, execute a step, inspect the result, and determine what should
happen next. That decision-and-action loop is what makes it agentic.
A simple conceptual loop is: Goal -> Understand current state -> Select skill/tool -> Act -> Observe
result -> Evaluate -> Continue, repair, escalate, or stop.
AI Agent Harness - Presentation Guide | Internal working notes
Product Owner Agent
A Product Owner Agent might use the product-vision skill to understand the desired outcome,
retrieve business context, use the story-description skill, create acceptance criteria, invoke the JIRA
tool, and then validate that the resulting ticket satisfies required standards.
Boundary
Skills are reusable capabilities. Tools are interfaces to systems. The agent is the decision loop. The
harness is the system that controls and supports the loop.
6. The Problem: Powerful Pieces, Scattered System
Say it like this: This is where we are today. We have strong models. We have prompts. We have
skills. We have agents. We can connect tools. All of these are useful and they already improve
productivity. But they are scattered. Without a common process and architecture, every team
independently solves context, permissions, validation, observability, retries, and integration. We
have powerful primitives, but no consistent operating system around them.
This is the pivot into the proposal.
Say it like this: What I am proposing is a method to this madness: an AI Agent Harness. Not
another model. Not another generic agent. A layer above and around the agent that turns these
primitives into a reliable enterprise system.
Core thesis
As frontier models and generic agents improve, differentiated enterprise value moves toward the
harness: proprietary context, business knowledge, workflows, controls, verification, integration,
and learning.
7. The AI Agent Harness - Complete Architecture
Present the harness as a set of cooperating subsystems. Do not imply that every component must be
a separate product or service. These are architectural responsibilities.
7.1 Context Engine
The context engine determines what the agent needs to know for this task and assembles it at
runtime. It should retrieve the minimum sufficient context rather than indiscriminately dumping
information into the model.
 Task and conversation context.
 User/role/authorization context.
 Relevant documents and enterprise knowledge.
 Code, schemas, APIs, data contracts, and system metadata.
AI Agent Harness - Presentation Guide | Internal working notes
 Workflow state and prior actions.
 Business ontology and relationships.
 Policies and operating instructions.
 Token-budgeting, ranking, freshness, provenance, and conflict handling.
Say it like this: The context engine is not just search. Its job is to construct the right working set
of knowledge for the current decision.
7.2 Enterprise Knowledge Base and Graph Ontology
This is where your knowledge-graph concept belongs. The graph is not competing with agents. It
supplies structured organizational understanding that agents can consume.
Say it like this: Documents tell us facts. Ontology tells us how the business fits together. For
example: a donor is related to accounts; an account may fund grants; a grant goes to a charity;
contributions fund accounts; restrictions may apply across those relationships. If the agent
understands those relationships, it reasons with the business model instead of treating every
document as disconnected text.
 Business entities and canonical definitions.
 Relationships and cardinality between entities.
 Ownership and lifecycle relationships.
 Policies and restrictions attached to entities.
 Links from structured entities to source systems and evidence.
 Potential combination of graph retrieval with document/vector retrieval.
Visual to generate
Draw Donor -> Account -> Grant -> Charity, with Contribution -> Account and policy/restriction
nodes connected to the appropriate entities. Place the Context Engine above it, retrieving a task-
specific subgraph.
7.3 Tool and Skill Layer
Tools let the agent interact with the enterprise. Skills teach it reusable procedures for using those
capabilities correctly.
 JIRA and work-management systems.
 Confluence and enterprise documentation.
 Databases and approved query interfaces.
 Internal and external APIs.
 Source-code repositories and CI/CD systems.
 Search and retrieval services.
 Messaging/event systems.
 Deterministic functions and enterprise services.
AI Agent Harness - Presentation Guide | Internal working notes
Say it like this: The question is not whether an agent technically can call a tool. The harness
decides which tools exist, which agent can use them, under what identity, with what scope, and
under what approval conditions.
7.4 Identity, Authorization, and Least Privilege
Every action must have an attributable identity and an enforceable authorization boundary. This is
separate from prompting.
 Who initiated the task?
 Which agent/service identity is executing?
 What data is it allowed to read?
 What actions can it perform?
 Which actions require explicit human approval?
 How are credentials scoped, rotated, and audited?
Critical distinction
Instruction: 'Do not write to production.' Guardrail: the agent literally does not possess a
production write permission. Prompt instructions influence behavior; permissions enforce
boundaries.
7.5 Guardrails and Policy Enforcement
Guardrails are controls that constrain behavior before, during, and after execution.
 Read-only versus write capabilities.
 Allowed/blocked systems, APIs, operations, and data classes.
 Data-loss and sensitive-information controls.
 Action limits and transaction boundaries.
 Approval requirements for consequential actions.
 Rate, spend, and resource limits.
 Policy checks before tool execution.
7.6 Persistent Instructions: AGENTS.md / Operating Context
Use AGENTS.md as an example implementation, not as the architecture itself. The responsibility is a
persistent instruction layer that prevents teams from repeating stable operating rules in every
prompt.
Say it like this: Think of AGENTS.md as durable operating context: coding conventions,
repository instructions, business rules, expected workflow, tool usage, review expectations, and
constraints that should travel with the agent every time it works in that environment.
Keep enforcement separate: instructions tell the agent what good behavior looks like; guardrails and
permissions prevent prohibited behavior.
AI Agent Harness - Presentation Guide | Internal working notes
7.7 Planning and Orchestration
Complex work needs explicit coordination. Some tasks are sequential, some parallel, some
conditional, and some require loops or human approvals.
 Task decomposition.
 Dependencies and parallel execution.
 Agent-to-agent handoffs.
 Branching based on outcomes.
 Retry and recovery paths.
 Timeouts and bounded execution.
 Human approval nodes.
 Event-triggered workflows.
Graph orchestration can be one mechanism inside the harness, but the harness is broader than
workflow graphs.
7.8 State and Memory
Agents need controlled state across steps and, where appropriate, across tasks.
 Current workflow state.
 Artifacts produced so far.
 Tool outputs and decision metadata.
 Short-lived working memory.
 Approved durable organizational memory.
 Clear separation between authoritative system-of-record data and model memory.
7.9 Gates: Deterministic Quality and Policy Checks
Say it like this: The agent should not be the final judge of its own work. After it produces an
output, we run gates.
 Schema and structural validation.
 Required-field checks.
 Unit/integration/security tests.
 Policy and compliance checks.
 Data-quality checks.
 Business-rule validation.
 Grounding/citation checks where applicable.
 Thresholds that determine pass, repair, human review, or rejection.
Prefer deterministic gates whenever a rule can be expressed deterministically. Use model-based
evaluation for ambiguity and judgment, not for things a normal program can verify exactly.
7.10 Review, Repair, and Bounded Evaluation Loops
This is the loop you were trying to articulate. Give it a name: gated review-and-repair loop.
Say it like this: The agent performs the task. Gates evaluate the output. If a deterministic gate
fails, we know exactly what violated the contract. For judgment-oriented checks, a review agent
AI Agent Harness - Presentation Guide | Internal working notes
or human reviewer can identify the problem and produce structured feedback. That feedback
goes back to the worker agent for repair. We repeat only within a bounded retry budget. If it still
fails, we escalate rather than looping forever.
 Worker agent creates output.
 Deterministic gates validate hard requirements.
 Reviewer evaluates semantic/quality requirements.
 Failures are converted into actionable repair feedback.
 Worker retries with failure context.
 Retry count, cost, and time are bounded.
 Persistent failure routes to a human or safe failure state.
Key line
A reliable agent is not one that never fails. It is a system that detects failure, contains it, repairs
when possible, and escalates when necessary.
7.11 Observability, Auditability, and Provenance
Observability should answer not merely 'did it fail?' but 'what happened and can we reconstruct it?'
 Task/trace ID and initiating identity.
 Model and model/version used.
 Prompt/instruction versions.
 Context sources retrieved and their versions/freshness.
 Tool calls, parameters, results, and latency.
 Gate outcomes and reviewer feedback.
 Agent handoffs and retry loops.
 Final decision/action and approval evidence.
 Token usage, model cost, latency, and failure category.
Say it like this: If an automated grant decision is questioned later, I should be able to
reconstruct the execution: what context was supplied, what tools were called, which checks
passed or failed, what was repaired, who approved it, and what final action occurred.
Memorable line
If we cannot reconstruct a consequential agent decision, we do not yet have an enterprise system;
we have a demo.
7.12 Human-in-the-Loop
Human involvement should be intentional, risk-based, and placed at explicit control points rather
than added as a vague fallback.
 Approval before high-impact actions.
 Review when confidence/evidence is insufficient.
AI Agent Harness - Presentation Guide | Internal working notes
 Escalation after bounded repair failures.
 Override with reason capture.
 Feedback that can improve future skills, policies, and evaluations.
7.13 Evaluation Framework
Runtime gates protect individual executions. Evaluation measures whether the overall agent system
is actually improving and remains fit for purpose.
 Golden datasets and representative task suites.
 Task success and business outcome metrics.
 Accuracy/quality by scenario.
 Regression tests for prompt, skill, workflow, and model changes.
 Safety/policy failure rates.
 Human override and escalation rates.
 Cost and latency per successful task.
 Model/skill/context-strategy comparisons.
7.14 Model Routing
Do not assume every task needs the same model. The harness can choose based on complexity, risk,
latency, cost, privacy, modality, or required capability.
Say it like this: The model becomes a replaceable execution engine. The enterprise intelligence
stays in the harness.
 Small/fast model for classification and extraction.
 Stronger reasoning model for ambiguous planning or review.
 Specialized/local models for privacy or domain-specific workloads.
 Fallback models when the preferred provider is unavailable.
 Routing policy based on measured evaluations rather than brand preference.
7.15 Multi-Agent Coordination
When multiple agents participate, define contracts between them rather than allowing an
uncontrolled conversation.
 Explicit responsibilities.
 Typed handoff artifacts.
 Shared versus isolated context.
 Ownership of final decisions.
 Conflict resolution.
 Loop/retry limits.
 Traceability across handoffs.
7.16 Eventing and Triggers
Enterprise agents should not depend only on a human typing a prompt. Work may begin from
events.
AI Agent Harness - Presentation Guide | Internal working notes
 New JIRA issue.
 Code pull request.
 Grant/application submission.
 Database or business-state change.
 Scheduled process.
 Message or document arrival.
 Monitoring alert.
7.17 Versioning, Configuration, and Release Management
Prompts, skills, policies, ontology, workflows, evaluators, and routing rules are production artifacts.
Treat them like software.
 Version-controlled definitions.
 Development/test/production promotion.
 Change approval.
 Canary or controlled rollout.
 Rollback.
 Traceability from an execution to the exact configuration used.
7.18 Cost, Latency, and Resource Governance
Efficiency belongs inside the architecture, not as an afterthought.
 Token/context budgets.
 Maximum loop/retry budgets.
 Model-selection economics.
 Cache and retrieval strategies.
 Parallel versus sequential execution tradeoffs.
 Per-workflow cost/latency SLOs.
 Cost per successful business outcome.
7.19 Learning and Continuous Improvement
The harness should capture outcomes and feed evidence back into engineering. Do not let the model
autonomously rewrite production policies. Learning should be governed.
 Collect failure categories and human corrections.
 Identify recurring missing context.
 Improve skills and retrieval rules.
 Expand evaluation datasets.
 Refine gates and policies.
 Measure before and after changes.
 Promote improvements through normal release controls.
AI Agent Harness - Presentation Guide | Internal working notes
8. One End-to-End Example: Automated Grant Processing
Use one example throughout the presentation. It will prevent the architecture from feeling
theoretical. The following is deliberately generic; use only business details appropriate for your
audience.
Flow
Stage What happens
1. Trigger A grant request enters the workflow.
2. Identity and task setup The harness establishes the initiating
user/process, task ID, permissions, and
applicable policy scope.
3. Context assembly The Context Engine retrieves the relevant grant
information, account context, charity
information, applicable restrictions/policies,
prior workflow state, and relationships from
the business ontology.
4. Planning The agent determines the required checks and
selects the appropriate skills.
5. Tool execution The agent invokes approved read-only APIs,
databases, documents, or business services as
needed.
6. Candidate decision/output The worker agent produces a recommendation,
classification, structured artifact, or next action.
7. Gates Deterministic business rules, required fields,
schemas, and policy checks execute.
8. Review A reviewer agent evaluates semantic reasoning
or quality dimensions that are not purely
deterministic.
9. Repair If a gate/reviewer finds a correctable issue,
structured feedback returns to the worker
agent.
10. Bounded retry The worker repairs and re-enters the gates.
Retry limits prevent infinite loops.
11. Human escalation High-risk, ambiguous, or repeatedly failing
cases route to an authorized human.
12. Action Only authorized actions are executed. Higher-
risk writes can require approval.
13. Trace Every context source, tool call, gate result,
review, retry, approval, and action is captured.
14. Learning Outcomes and human corrections feed
evaluation datasets and future controlled
improvements.
AI Agent Harness - Presentation Guide | Internal working notes
Say it like this: Notice what changed. The LLM is only one component. Reliability comes from
the system around it: context, knowledge, permissions, tools, gates, repair loops, human control,
and traceability.
9. The Architecture Diagram to Put on the Main Slide
Use a layered diagram rather than a giant spider diagram. This is the picture the audience should
remember.
BUSINESS OUTCOMES / ENTERPRISE WORKFLOWS
|
+---------------------------+
| AI AGENT HARNESS |
|---------------------------|
| Context Engine |
| Knowledge + Ontology |
| Skills + Tool Registry |
| Identity + Permissions |
| Guardrails + Policies |
| Planning + Orchestration |
| State + Memory |
| Gates + Review/Repair |
| Human Approval |
| Observability + Audit |
| Evaluation + Learning |
| Routing + Cost Controls |
+---------------------------+
|
+-------------+
| AGENT |
| decide/act |
| observe/loop|
+-------------+
/ \
SKILLS TOOLS
\ /
MODEL(S)
Diagram message
The model is at the bottom because it is an execution capability. The enterprise value accumulates
as you move upward: organization-specific context, controls, workflows, evidence, and business
outcomes.
10. Suggested Presentation Sequence
Slide Message
Slide 1 - The question AI models are getting better rapidly. What
remains uniquely valuable to the enterprise?
Slide 2 - Model Explain next-token prediction once. Powerful,
AI Agent Harness - Presentation Guide | Internal working notes
but narrow without enterprise context or
agency.
Slide 3 - Mouse story Demonstrate why the same request produces
different correct answers as context changes.
Slide 4 - Context engineering Define the discipline and show enterprise
context sources.
Slide 5 - Skills Show JIRA, acceptance criteria, story
description, product vision.
Slide 6 - Agent Show the goal-directed loop and clarify agent vs
skill vs tool.
Slide 7 - Today's problem Powerful primitives, scattered
implementations, repeated reinvention.
Slide 8 - Harness thesis Reveal the harness as the method around the
primitives.
Slide 9 - Harness architecture Show the complete layered architecture.
Slide 10 - Knowledge ontology Use Donor/Account/Grant/Charity/Contribution
relationships.
Slide 11 - Security and guardrails Contrast prompt instruction with enforced
permission.
Slide 12 - Gates and repair loop Worker -> gates -> reviewer -> repair ->
bounded retry -> escalation.
Slide 13 - Observability Show a trace/timeline that reconstructs one
execution.
Slide 14 - End-to-end workflow Walk the generic grant-processing example
through the harness.
Slide 15 - Enterprise outcome Reliability, reuse, governance, automation,
faster delivery, and measurable improvement.
Slide 16 - Closing The model will change. The harness preserves
enterprise intelligence and control.
11. How to Explain the Review Loop Without Getting Stuck
Say it like this: The worker agent creates an output. We do not simply trust it. First,
deterministic gates check everything that can be checked exactly. Then, where judgment is
required, a reviewer evaluates the output against a rubric. If something fails, the system
produces structured feedback and sends the work back for repair. The agent gets a limited
number of attempts. If it still cannot satisfy the gates, or if the task is high risk, the harness
escalates to a human. Every attempt is traced.
Then stop. Do not describe it as 'the agent loops through the agent.' Name the roles: worker, gate,
reviewer, repair, retry limit, escalation.
12. Important Distinctions to Keep Precise
Concept What it is What it is not
AI Agent Harness - Presentation Guide | Internal working notes
Prompt Immediate instruction/context
to steer a model.
A security boundary.
Skill Reusable bounded
procedure/capability.
The entire agent.
Tool Interface through which the
system reads or acts.
Business reasoning by itself.
Agent Goal-directed decision/action
loop using model, context,
skills, and tools.
Just a long prompt or a bundle
of skills.
Context Engine Runtime assembly of relevant
task knowledge.
Dumping the whole knowledge
base into the prompt.
Knowledge Graph/Ontology Structured entities, meaning,
and relationships.
A replacement for agents.
AGENTS.md One implementation of
persistent operating
instructions.
A hard permission control.
Guardrail Enforced constraint or policy
control.
Merely telling the model not to
do something.
Gate A validation checkpoint with
explicit pass/fail/route
behavior.
Generic observability.
Evaluation Systematic measurement of
quality over representative
tasks.
Only runtime validation.
Harness The operating architecture
around agents.
Another generic coding agent.
13. What Not to Claim
 Do not claim the model is 'dumb.' Say powerful but narrow and context-dependent.
 Do not claim an agent is simply a set of skills. It uses skills within a decision loop.
 Do not imply AGENTS.md enforces security. It supplies instructions; permissions enforce
security.
 Do not make the knowledge graph sound like the orchestration graph. Ontology/knowledge
relationships and execution/workflow graphs are different concerns.
 Do not imply an LLM reviewer guarantees correctness. Combine deterministic checks, evidence,
review, human escalation, and evaluation.
 Do not make the harness 'everything in IT.' Keep its boundary around the lifecycle of intelligent
agent execution.
14. Closing Narrative
Say it like this: Models will keep getting better. Agents will keep getting better. The generic
ability to reason, code, plan, and call tools will increasingly become a commodity. Our durable
AI Agent Harness - Presentation Guide | Internal working notes
advantage is not wrapping another prompt around the newest model. It is capturing what the
generic model does not inherently possess: our business knowledge, our ontology, our context,
our systems, our permissions, our operating rules, our workflows, our verification standards,
and the evidence of how work was performed. That is the role of the AI Agent Harness.
Say it like this: The model provides intelligence. The agent provides agency. The harness
provides enterprise reliability.
Final slide line
MODEL = intelligence. AGENT = agency. HARNESS = enterprise control + context + reliability.
15. Visuals to Generate for the Demo
 Mouse context story: three panels - computer mouse, lab mouse, pet mouse - with progressively
richer context above each panel.
 Layered evolution: Model -> Prompt -> Context -> Skills/Tools -> Agent -> Harness -> Business
Workflow.
 Ontology diagram: Donor, Account, Contribution, Grant, Charity, Restrictions/Policies with
labeled relationships.
 Harness architecture: agent at center or inside a layered box, surrounded by context, knowledge,
tools, identity, guardrails, orchestration, gates, observability, evaluation, and human approval.
 Review/repair loop: Worker -> Deterministic Gates -> Reviewer -> Pass/Repair -> bounded retry ->
Human escalation.
 Observability trace: Context retrieval -> model call -> tool call -> gate -> review -> retry ->
approval -> final action, each with timestamps and provenance.
 End-to-end grant-processing flow showing where the harness intervenes at every stage.
 Model-routing visual: task enters router and goes to fast model, reasoning model,
specialized/local model, or reviewer model based on policy.
16. 60-Second Executive Summary
Say it like this: AI models are becoming extraordinarily capable, but enterprise automation
requires more than a capable model. Models need the right context, structured business
knowledge, controlled access to tools, reusable skills, permissions, guardrails, workflow
orchestration, verification, auditability, and human control. Today those capabilities are often
implemented independently and inconsistently. The AI Agent Harness provides a common
architecture around agents. It grounds them in enterprise context and ontology, controls what
they can do, validates what they produce, repairs failures through bounded loops, escalates when
necessary, and records the complete execution trail. The result is not another generic agent. It is
the enterprise system that makes powerful agents usable for real business work.
AI Agent Harness - Presentation Guide | Internal working notes
17. One-Sentence Definitions for Q&A
Model: A learned inference engine that generates outputs from the context it receives.
Context engineering: The deliberate construction of the information available to the model at the
moment of decision.
Skill: A reusable, bounded procedure or capability available to an agent.
Tool: An interface that lets an agent retrieve information or perform an action.
Agent: A goal-directed loop that decides, acts through skills/tools, observes results, and continues
until a stopping condition.
Knowledge ontology: The structured definition of business entities, meaning, and relationships.
Harness: The enterprise operating layer that supplies context, knowledge, controls, tools,
orchestration, verification, observability, and lifecycle management around agents.
Gate: A checkpoint that validates an output or action against an explicit requirement.
Review-and-repair loop: A bounded process that detects a failure, returns actionable feedback,
retries the work, and escalates if it cannot be repaired.
Observability: The ability to inspect the behavior and health of an execution.
Auditability: The ability to reconstruct and evidence what happened, using which context, policies,
tools, models, approvals, and versions.