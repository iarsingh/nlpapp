# nlpapp — interview questions and answers

[README](README.md) · [Project architecture](PROJECT_ARCHITECTURE.md)

Answers below use this repository’s files and implementation. They distinguish existing behavior from suggested extensions; source links let you verify each walkthrough.

## 1. What problem does nlpapp address, and what can you demonstrate?

A Python desktop NLP application built with Tkinter, object-oriented design, JSON storage, and an external NLP API.

I would demonstrate the linked implementation or examples and distinguish that evidence from any planned production features. Start with [`README.md`](README.md).

## 2. How is this repository organized?

- [`app.py`](app.py): Implementation or supporting configuration.
- [`myapi.py`](myapi.py): Implementation or supporting configuration.
- [`mydb.py`](mydb.py): Implementation or supporting configuration.
- [`README.md`](README.md): Project explanations or operating notes.

[PROJECT_ARCHITECTURE.md](PROJECT_ARCHITECTURE.md) contains the component diagram and the implementation walkthrough.

## 3. Can you walk through `register_gui` and explain the decision it makes?

The main walkthrough here is `register_gui(self)` in [`app.py`](app.py#L55).

```python
    def register_gui(self):
        self.clear()

        heading = Label(self.root, text='NLPApp', bg='#34495E', fg='white')
        heading.pack(pady=(30, 30))
        heading.configure(font=('verdana', 24, 'bold'))

        label0 = Label(self.root, text='Enter Name')
        label0.pack(pady=(10, 10))

        self.name_input = Entry(self.root, width=50)
        self.name_input.pack(pady=(5, 10), ipady=4)

        label1 = Label(self.root, text='Enter Email')
        label1.pack(pady=(10, 10))

        self.email_input = Entry(self.root, width=50)
        self.email_input.pack(pady=(5, 10), ipady=4)

        label2 = Label(self.root, text='Enter Password')
```

This is an excerpt; follow the source link for the rest of the branches.

The implementation calls `Button`, `Entry`, `Label`, `heading.configure`, `heading.pack`, `label0.pack`, `label1.pack`, `label2.pack`, `label3.pack`. In an interview, trace those calls in execution order using a fixture input.

## 4. What responsibility does `login_gui` have?

`login_gui(self)` is defined in [`app.py`](app.py#L26).

It uses `Button`, `Entry`, `Label`, `heading.configure`, `heading.pack`, `label1.pack`, `label2.pack`, `label3.pack`. This is the code path I would compare against the caller to explain responsibility boundaries.

## 5. What would you verify before extending this repository?

I would identify an executable example or define a concrete acceptance case for the material in [`README.md`](README.md). For code, verify inputs, outputs, and failure handling; for notes or templates, verify that a reader can follow the procedure and distinguish examples from measured results.

## 6. How would you verify correctness when no test suite is present?

There are no dedicated test files in the inspected first-party inventory. I would select one concrete example from [`README.md`](README.md), define expected output or an acceptance checklist, and add repeatable verification before expanding scope. For a documentation-only repository, that means checking links, instructions, and the reproducibility of examples.

## 7. How do you separate the current design from a future production design?

The current design is the source/component map in [PROJECT_ARCHITECTURE.md](PROJECT_ARCHITECTURE.md). A future deployment needs explicit input contracts, persistence decisions, authentication, monitoring, and rollback. I would present these as proposed work until the corresponding implementation and verification exist.

## 8. How would you investigate data ownership and persistence?

Trace the data/configuration files and the code that reads or writes them in the component table. Identify which files are examples, which records are mutable, and which external store is actually configured. I would document those facts before discussing retention, backup, or tenant isolation.

## 9. How would another engineer reproduce your walkthrough?

Follow [`README.md`](README.md) and the linked component documents. This documentation update does not assert an application launch command for a repository without a verified launch contract.

## 10. How would you add CI without confusing it with deployment?

First automate the repository-specific checks above, including documentation link validation. Add deployment only after defining the target environment, required credentials, approval boundary, smoke test, and rollback procedure. No GitHub Actions workflow is asserted by the inspected inventory.

## 11. How would you present this project in a Forward Deployed Engineer interview?

Start with the user and operational problem described in [`README.md`](README.md). Explain one constraint that changes the implementation, show the linked code or example, and walk through a success case and a failure case. Agree on a measurable acceptance criterion before expanding the solution, and leave a handoff with data boundaries and rollback ownership. Any proposed production or business metric should be identified as a target until measured.

## 12. What is the input-to-output contract of `register_gui`?

In [`app.py`](app.py#L55), `register_gui(self)` receives the inputs. The function computes these intermediate values:

- `heading = Label(self.root, text='NLPApp', bg='#34495E', fg='white')`
- `label0 = Label(self.root, text='Enter Name')`
- `self.name_input = Entry(self.root, width=50)`
- `label1 = Label(self.root, text='Enter Email')`
- `self.email_input = Entry(self.root, width=50)`
- `label2 = Label(self.root, text='Enter Password')`
- `self.password_input = Entry(self.root, width=50, show='*')`
