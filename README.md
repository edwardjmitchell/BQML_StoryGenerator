# BQML_StoryGenerator
BQML Hackathon Entry

Story Engine: From World-Building to Narrative with BQML
A competition submission that empowers authors to automatically generate story plot points from their world-building data directly within Google BigQuery.

The Problem: The World-Builder's Bottleneck
Authors are often brilliant world-builders. They meticulously craft rich characters, vivid locations, and detailed timelines of events. This foundational data is the soul of the story.

However, the process of weaving these disparate elements into a compelling, cohesive narrative can be a separate and time-consuming challenge. The creative energy spent on world-building doesn't always translate directly into prose, leaving authors with a gap between their well-structured notes and a finished story.

The Solution: An AI Co-Author in Your Database
Story Engine bridges this gap. It's an automated narrative generation pipeline that empowers authors to remain in their creative zone of world-building. By simply populating tables with their characters and locations, authors can use the power of BigQuery and its built-in Large Language Models (LLMs) to handle the heavy lifting of initial narrative drafting.

Our system uses a single SQL query to:

Read all the world-building data.

Synthesize the data into a rich, contextual prompt.

Generate three core plot points: The Setup, The Conflict, and The Resolution.

Insert these generated plot points directly into a results table, ready for the author to review, edit, and expand upon.

The Journey: A Pivot from Phonics to Prose
Our initial goal was more modest: to generate simple, phonics-based readers for early literacy. We believed that by providing an LLM with a highly restricted vocabulary and simple character descriptions, we could create educational content.

We quickly discovered a fascinating limitation of modern LLMs. Despite their vast knowledge, they struggled immensely with such a heavily constrained vocabulary. The models would consistently revert to more complex synonyms or fail to maintain the simple phonetic rules, as their training predisposes them to sophisticated language.

This led to a crucial realization: the model's strength is not in limitation, but in synthesis.

Instead of forcing the LLM into a tiny creative box, we decided to give it a bigger sandbox. We pivoted the project to do what the model does best: take a large amount of related context and weave it into something new. This transformed the project from a struggling phonics generator into the powerful Story Engine it is today, designed to assist authors with complex narratives.

How It Works: The Power of a Single BQML Query
The entire process is powered by a single, powerful SQL query that leverages the ML.GENERATE_TEXT function. The query intelligently aggregates all characters and locations into a single context, then calls the model three times—once for each plot point—and inserts the results.

Future Work
This project lays the foundation for a more advanced narrative generation platform. Future enhancements could include:

Integrating Event Timelines: Using an Events table with timestamps to generate plot points that follow a specific chronological order.

Chain-of-Thought Generation: Using the output of the "Setup" generation as part of the prompt for the "Conflict" generation, creating a more logically connected story.

Character Point-of-View: Modifying the prompt to generate the story from the perspective of a specific character in the Characters table.

Story Engine demonstrates a powerful new paradigm for creative collaboration, where authors can focus on what they do best—imagination and world-building—while leveraging AI as a tireless partner to accelerate the drafting process.
