Worked on GovDrive project, a secure cloud storage for government officials, by designing a tag-based search system powered by LLMs.

• Used unstructured.io library to extract text from various types of files, including scanned PDFs, DOCX, Excel,
PPTX and source codes.

• Designed and tweaked system prompts to extract desired tags and summaries in JSON format (for easier storage
of tags in Elasticsearch index) from Mistral Instruct v0.3 (7B) model.

• Used a similar workflow for images, using IDEFICS2 (8B) model to perform visual analysis and generate descriptive tags directly from images.

• Stored and indexed all generated metadata in Elasticsearch, where User query is matched with tags from files,
to give the user relevant ranked search results.

• Tested and compared various LLMs (Llama 3.1, Qwen 2, Param AI, Airavata, LLaVA, Mantis-IDEFICS2 etc.) to
select the most efficient LLM for my use case.
