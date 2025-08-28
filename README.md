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



SAMPLE OUTPUT:

For Image Screenshot:

{
 "document_type": "Screenshot",
 "governmental_entity": "Aadhaar",
 "location": "Delhi",
 "person": 1,
 "organization": "Aadhaar",
 "date": "2017-11-01",
 "keywords": [
 "Aadhaar Card",
 "Delhi",
 "India"
 ],
 "contextual_keywords": [
 "Aadhaar Card",
 "Delhi",
 "India"
 ],
 "summary": "A screenshot of an Aadhaar Card with personal information redacted.",
 "is_confidential": true,
 "is_suspicious":false
}


For PDF:

Processed: ICMR-NIN User Manual.pdf
 Extracted Tags: {
 "filename": "ICMR-NIN User Manual.pdf",
 "document_type": "E-Learning Manual",
 "governmental_entity": "Ministry of Women and Child Development, Ministry of Health & Family
Welfare, Government of India",
 "location": "Hyderabad, Telangana State, India",
 "person": [],
 "organization": [
 "ICMR-National Institute of Nutrition",
 "Ministry of Women and Child Development",
 "Ministry of Health & Family Welfare, Government of India"
 ],
 "date": "2019-01-19",
 "keywords": [
 "POSHAN Abhiyaan",
 "E-Learning",
 "Nutrition",
 "Basics of Nutrition",
 "Child feeding",
 "Mothers’ Health & Nutrition",
 "Anemia",
 "Yoga",
 "Food fortification",
 "Physical activity"
 ],
 "contextual_keywords": [
 "Nutrition Education Programme",
 "e-Learning platform",
 "Module Certificate"
 ],
 "summary": "The document is a user manual for POSHAN Abhiyaan E-Learning ICMR-NIN Modules, an
initiative by the Ministry of Women and Child Development and Ministry of Health & Family Welfare,
Government of India. The modules aim to educate people on practical nutritional knowledge pertaining to
daily life. Users can register, login, watch videos, and take tests to earn certificates.",
 "is_confidential": false,
 "is_suspicious": false
 }
