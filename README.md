# AgenticHarnessLearning
Agentic Harness Architecture — hands-on with a ticket-booking agent
This notebook builds an agent harness from scratch, one layer at a time, using a single running example: book a flight for a traveler.

A harness is everything around the model — context assembly, tools, the control loop, policy enforcement, verification, memory, and tracing. The model is one box; the harness is the other eight.

Inputs → Context assembler → Model → Policy enforcement point → Tool layer (sandbox) ─┐
            ▲                                                                           │ observation
            └───────────────────────────────────────────────────────────────────────────┘
         Memory ⇄ Context assembler        Verifier ⇄ Tool layer        Control loop decides the phase
How to use this notebook

Run cells top to bottom. Every cell adds one harness layer and ends with a short "What the harness just did" note.
It runs without any API key using a MockModel that behaves like a well-trained agent. Set MODEL_PROVIDER to anthropic or openai and paste a key (or store it in Colab Secrets) to run the same harness on a real model.
All world state lives in flat files under data/ — open them in the Colab file browser to watch the agent's effects.
Exercises at the end let you break the harness and watch each layer catch the failure.
