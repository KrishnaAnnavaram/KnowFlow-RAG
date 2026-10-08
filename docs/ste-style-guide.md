# The writing standard: ASD-STE100 Simplified Technical English

Use these rules for every README and for `docs/ste-style-guide.md` in each repository. Copy this file
into the repository as `docs/ste-style-guide.md` and add a **project vocabulary** section (Section 3)
with the technical names and technical verbs of that project.

## 1. The writing rules

### Words

1. Use one word for one meaning, and one meaning for one word. Do not use synonyms for variety.
2. Use a word only as one part of speech. For example, `test` is a noun or a verb, `check` is a verb.
3. Do not use phrasal verbs (`set up`, `carry out`, `find out`, `pick up`, `look up`, `come up with`).
   Use one verb: `prepare`, `do`, `find`, `get`, `make`.
4. Do not use an `-ing` form as a noun or an adjective (`the running job`, `after indexing`).
   Exception: a technical name, a file name, a command or a status value.
5. Do not use contractions (`don't`, `it's`, `can't`). Do not use slang or idioms
   (`out of the box`, `under the hood`, `at a glance`, `gotcha`, `bells and whistles`).
6. Do not use `and/or`. Write `A, B or both`.
7. Do not use `should`, `could`, `would` or `may` for instructions. Use `must` for a rule, the
   imperative for a step and `can` for a possibility.
8. Keep the articles `a`, `an` and `the` in sentences.
9. Do not make a noun cluster of more than three words. A technical name is one word.

### Sentences

1. A procedural sentence (an instruction) has a maximum of **20 words**.
2. A descriptive sentence has a maximum of **25 words**.
3. Write one instruction in one sentence.
4. Use the imperative for an instruction: `Run the tests.` Not `The tests should be run.`
5. Use the active voice. Use the passive voice only when the agent of the action is not important.
6. Use only the simple present, the simple past and the simple future.
7. Put a condition before the instruction: `If the index is stale, build it again.`
8. Do not use semicolons in sentences. Write two sentences.

### Paragraphs, notes and warnings

1. A paragraph has one topic and a maximum of **6 sentences**. Start with the topic sentence.
2. A warning or a caution starts with a clear command. Then it gives the reason.
3. A note gives information. It does not give an instruction.
4. Use a vertical list for a sequence or a set of conditions. Each item of a numbered procedure is one step.

### Tables, headings and diagrams

1. A table cell can be a short phrase. If a cell has a sentence, the sentence obeys the rules.
2. A heading is a noun phrase (`The cost model`) or an imperative (`Run the demo`).
   Do not start a heading with an `-ing` form.
3. A diagram label is a short phrase. Use the same terms as the text.

### What STE does not change

Code, commands, file names, paths, field names, environment variables, status values, enum values,
product names and URLs stay exactly as they are. They are technical names. Put them in backticks.

## 2. General words to replace

| Do not use | Use |
|---|---|
| utilize, leverage | use |
| in order to | to |
| set up | prepare, install, configure |
| carry out, perform | do |
| make sure, ensure | make sure (allowed), or `check that` |
| a lot of, lots of | many, much |
| e.g., i.e. | for example, that is |
| should (instruction) | must (rule) / imperative (step) |
| might, may (possibility) | can |
| very, really, just, simply, easily | (delete) |
| seamless, robust, powerful, blazing | (delete or give a measured fact) |

## 3. Project vocabulary

This section gives the technical names and the technical verbs of KnowFlow-RAG. The README uses each term with only this meaning.

### 3.1 Technical names (nouns)

| Term | Meaning | Do not use |
|---|---|---|
| **role** | The job of the user: Data Scientist, Data Engineer or Data Analyst | persona, job title (except in a quote of the report) |
| **level** | The experience of the user: Junior, Mid or Senior | seniority, grade, tier |
| **knowledge base** | The PDF files in `data/knowledge_base` that the app loads | corpus, document store, dataset |
| **chunk** | A part of a PDF page of up to 500 characters | passage, snippet, segment |
| **role and level filter** | `filter_docs_by_role_and_level`, the keyword filter on the chunks | role agent (except the file name `role_agent.py`) |
| **retriever** | A component that gives the chunks for a question: BM25, FAISS or hybrid | search engine, searcher |
| **hybrid retriever** | `HybridSearch`, the joined BM25 and FAISS results | fusion search, combined search |
| **agent** | The LangChain agent on `gpt-4` that selects the retriever tools | router, orchestrator |
| **tool** | One LangChain `Tool` that wraps one retriever | plugin, action |
| **context** | The text under `Context:` in the prompt | evidence, grounding |
| **tone** | The instruction that sets the depth of the answer for a level | style, voice |
| **answer** | The text that GPT-4 gives for one question | response, reply, output (except for code values) |
| **feedback row** | One record of question, answer, Yes or No, comment, role and level | rating, review, survey entry |
| **installation guide** | `KnowFlow Chatbot Documentation and Installation Guides.pdf` | manual, docs |
| **report** | `PROJECT_REPORT.pdf` | paper (except in the report title), thesis |
| **deck** | The 13-slide presentation in commit `6fff8c4` | slides, PPT |

### 3.2 Technical verbs

| Verb | Meaning |
|---|---|
| **load** | Read the PDF files of the knowledge base into pages |
| **split** | Cut the pages into chunks with an overlap |
| **filter** | Keep only the chunks that contain a keyword of the role and level |
| **embed** | Change a text into a vector with an embeddings model |
| **retrieve** | Get the top chunks for a question from one retriever |
| **rerank** | Sort chunks again by cosine similarity to the question (`rank_documents`) |
| **select** | Choose a retriever tool (the agent) or a role and a level (the user) |
| **generate** | Make the answer with `gpt-4` from the prompt |
| **export** | Write the feedback rows to `feedback_log.xlsx` |
