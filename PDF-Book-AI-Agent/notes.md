\# \*\*PDF Book AI Agent — Automation Summary\*\*



The \*\*PDF Book AI Agent\*\* is an advanced n8n automation that transforms a simple Telegram message into a fully generated, multi‑chapter illustrated PDF book. It combines AI topic validation, historical research, image generation, HTML templating, and cloud storage into a seamless end‑to‑end pipeline.



---



\## \*\*What the Automation Does\*\*

\- Accepts user input via Telegram and validates whether the request is a historical or educational topic.

\- Generates a structured, multi‑chapter narrative (up to 20 chapters) using AI.

\- Creates detailed image prompts for each chapter and sends them to an external image‑generation API.

\- Waits for image generation, retrieves the results, and uploads them to Cloudinary.

\- Builds a polished, multi‑page HTML layout for the book, including headers, images, and styled text.

\- Converts the HTML into a PDF using an external PDF rendering API.

\- Uploads the final PDF to Google Drive and logs all job metadata in Google Sheets.



---



\## \*\*High‑Level Workflow\*\*

\### \*\*1. Input \& Topic Validation\*\*

\- A Telegram Trigger receives user messages.

\- A classifier agent checks whether the message is a valid historical/educational topic.

\- If invalid → sends a polite decline message.

\- If valid → refines the topic and creates a new “Briefing Job” entry in Google Sheets.



\### \*\*2. Content Generation\*\*

\- A historian‑style AI agent researches the topic and produces:

&nbsp; - 5–20 chapters  

&nbsp; - Titles, dates, educational paragraphs  

&nbsp; - Image prompts with explicit text instructions  

\- Chapters are split into individual items for processing.



\### \*\*3. Image Generation Loop\*\*

For each chapter:

\- A unique ID is generated.

\- A task is sent to the \*\*Nano Banana Pro\*\* image generation API.

\- The workflow polls the task status until:

&nbsp; - \*\*Success\*\* → downloads the image  

&nbsp; - \*\*Generating\*\* → waits and checks again  

&nbsp; - \*\*Fail\*\* → stops the loop  

\- The generated image is uploaded to Cloudinary.

\- The corresponding Google Sheets row is updated with the public image URL.



\### \*\*4. PDF Assembly\*\*

\- All chapter data is aggregated.

\- A custom HTML template renders each chapter as a full‑page layout:

&nbsp; - Header with title and date  

&nbsp; - Image block  

&nbsp; - Drop‑cap styled paragraph  

&nbsp; - Footer with chapter ID  

\- The HTML is sent to a PDF rendering API.

\- The resulting PDF is uploaded to Google Drive.

\- The job entry in Google Sheets is updated with the final PDF link.



---



\## \*\*Tech Stack \& Integrations\*\*

\- \*\*n8n\*\* for orchestration  

\- \*\*Telegram Bot\*\* for user interaction  

\- \*\*LangChain Agents\*\* for topic validation and chapter generation  

\- \*\*OpenAI Models\*\* for narrative creation  

\- \*\*Nano Banana Pro API\*\* for image generation  

\- \*\*Cloudinary\*\* for image hosting  

\- \*\*Google Sheets\*\* for job tracking  

\- \*\*Google Drive\*\* for PDF storage  

\- \*\*APITemplate.io\*\* for HTML‑to‑PDF conversion  



---



\## \*\*Purpose \& Value\*\*

This automation creates a fully autonomous \*\*AI‑powered educational book generator\*\*. It:

\- Eliminates manual research, writing, and design work  

\- Produces consistent, high‑quality illustrated content  

\- Scales to unlimited topics and chapters  

\- Provides a clean audit trail via Google Sheets  

\- Delivers a polished PDF ready for distribution  



It’s a showcase of your ability to combine AI, automation, and multi‑service orchestration into a production‑ready content engine.

