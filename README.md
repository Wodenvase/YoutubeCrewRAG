Absolutely — here’s your refined README draft for YouTubeCrewRAG, keeping it clear, professional, and sponsor-focused, with consistent formatting, cleaner explanations, and a bit more polish:

⸻

📺 YouTubeCrewRAG

A practical sandbox for experimenting with CrewAI and Retrieval-Augmented Generation (RAG) to analyze YouTube channels and videos.
This project demonstrates how to orchestrate multiple AI agents and tools to scrape channel data, store it in a vector database, and generate structured research outputs for sponsorship insights.

⸻

🎯 Primary Use Case — Brand Sponsorship Fit

If you’re a sponsor or brand manager, this project helps you quickly answer:
✅ Is this channel’s content relevant to my product?
✅ What type of videos do they publish, and how often?
✅ Are they consistent, credible, and aligned with my brand?
✅ Where does my product fit in their content strategy?

By using a multi-agent RAG pipeline, you can automatically track, vectorize, and analyze YouTube channels — reducing manual research time and improving your sponsorship decisions.

⸻

⚡ Key Features
	•	Scrape YouTube channels: Fetch the latest videos using the YouTube Data API v3.
	•	Store in a vector database: Make video data searchable for content relevance, trend analysis, or semantic Q&A.
	•	Run orchestrated multi-agent tasks: Scrape → Vectorize → Analyze → Fill missing info → Final web fallback.
	•	Output a ContentCreatorInfo profile: Structured insights about the channel for sponsorship fit.

⸻

🗂️ Project Structure

youtubecrewrag/
├── tools/
│   ├── AddVideoToVectorDBTool.py
│   └── FetchLatestVideosFromYouTubeChannelTool.py
├── crew.py       # Main CrewAI orchestration logic
├── main.py       # Entry point script
├── .env          # API keys and environment configs
├── .gitignore
├── poetry.lock
├── pyproject.toml
└── README.md


⸻

🧩 How It Works

🕹️ Agents

✅ Scrape Agent — Fetches latest video metadata.
✅ Vector DB Processor — Stores video data in your vector database.
✅ General Research Agent — Populates the ContentCreatorInfo profile.
✅ Follow-up Agent — Fills in any missing details.
✅ Fallback Agent — Performs final web checks for gaps.

⸻

🧰 Tools
	•	FetchLatestVideosFromYouTubeChannelTool.py — Uses the YouTube Data API to get video details.
	•	AddVideoToVectorDBTool.py — Adds fetched video data to your vector database (e.g., Pinecone, FAISS).

⸻

✅ End-to-End Workflow
	1.	Scrape latest videos.
	2.	Vectorize and store video content.
	3.	Generate ContentCreatorInfo for the channel.
	4.	Run follow-ups and fallback checks to ensure the profile is complete.

⸻

⚙️ Setup & Installation

1️⃣ Clone the repository

git clone https://github.com/Wodenvase/youtubecrewrag.git
cd youtubecrewrag

2️⃣ Install dependencies

Ensure you have Poetry installed:

poetry install --no-root

3️⃣ Create your .env file

In your project root, add your API keys:

YOUTUBE_API_KEY=your_youtube_api_key
OPENAI_API_KEY=your_openai_api_key
# Add other keys as needed


⸻

📡 Set Up YouTube Data API v3
	1.	Go to the YouTube Data API v3 page on Google Cloud Console.
	2.	Click Enable.
	3.	Go to API Credentials and create an API Key.
	4.	Add it to your .env as YOUTUBE_API_KEY.

⸻

🚀 Run the YouTube Crew

From your project directory, run:

python crew.py

This will:
	•	Fetch the latest videos from your target channel.
	•	Add video metadata to the vector database.
	•	Run multi-agent tasks to enrich and verify the ContentCreatorInfo output.

⸻
