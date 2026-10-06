# nlpapp

<!-- project-guide:start -->
## Project guide

[Project architecture](PROJECT_ARCHITECTURE.md) · [Interview questions and answers](INTERVIEW_QA.md)

Use the architecture document for the component diagram, implementation boundaries, and verification entry points. The interview guide includes source-backed answers and project walkthroughs.

### Implementation map

| Component | Responsibility |
| --- | --- |
| [`app.py`](app.py) | Functions: `__init__`, `login_gui`, `register_gui`, `clear`, `perform_registration`, `perform_login`, `home_gui` |
| [`myapi.py`](myapi.py) | Functions: `__init__`, `sentiment_analysis`, `ner`, `emotion_prediction` |
| [`mydb.py`](mydb.py) | Functions: `add_data`, `search` |
| [`README.md`](README.md) | Project explanations or operating notes |

Setup and examples are described in the existing project notes below. Consult the component-specific manifests before assuming a single launch command.

<!-- project-guide:end -->

<!-- repository-summary -->
A Python desktop NLP application built with Tkinter, object-oriented design, JSON storage, and an external NLP API.
<!-- /repository-summary -->
An API based NLP application created using Tkinter and OOP

Link for API - https://komprehend.io/api-wrappers

## Documentation checks

Project architecture, interview guides, and local source links are checked automatically on pushes and pull requests. Run the same check locally:

```bash
python3 .github/scripts/validate_project_docs.py
```
