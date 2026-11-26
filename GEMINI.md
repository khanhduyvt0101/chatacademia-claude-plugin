# ChatAcademia

ChatAcademia gives you academic research tools through the `chatacademia` MCP server.

- Use `search_papers` and `get_paper_evidence` for scholarly sources; cite only papers a tool returned, with their links.
- Use `verify_citations` (up to five titles per call) before trusting a reference list.
- Use `list_research_workflows` / `get_research_workflow` for guided workflows (literature overview, research gap,
  research questions, hallucination checker, mock peer review, grants, data extraction, seminar planning).
- Search results are metadata and abstracts, not full text: say so, and treat an empty search as "not found", not as
  evidence of absence.
- Research tools use the user's ChatAcademia credits. Do not call `remember_about_me` or `submit_feedback` unless the
  user asks. If a tool reports no plan or too few credits, stop and tell the user instead of retrying.

The first call opens a browser sign-in (OAuth). Docs: https://www.chatacademia.com/claude
