# YoutubeCrewRAG

A hands-on sandbox for experimenting with CrewAI + Retrieval-Augmented Generation (RAG) to analyze YouTube channels and videos.
This project shows how to orchestrate multiple AI agents and tools to scrape YouTube data, store it in a vector database, and run structured follow-up research.

⸻
🎯 Primary Use Case: Brand Sponsorship Fit

If you’re a sponsor or brand manager, this project helps you answer:
✅ Is this YouTube channel’s content relevant to my product?
✅ What type of videos do they publish, and how often?
✅ Are they consistent, credible, and aligned with my brand message?
✅ What gaps exist that my product can fill?

By using a multi-agent RAG pipeline, you can track, vectorize, and analyze channels automatically — so you spend less time on manual research and more time making informed sponsorship decisions.

⸻

⚡ What this project does
	•	Scrapes YouTube channels: Fetches the latest videos with the YouTube Data API v3.
	•	Stores video data in a vector database: Makes it searchable for content relevance and trends.
	•	Runs orchestrated multi-agent research: Scrape → Vectorize → Analyze → Fill missing info → Final web fallback.
	•	Outputs a ContentCreatorInfo model: Structured data about the channel, useful for sponsorship fit assessments.

⸻

🗂️ Project Structure

agentfleet-rag-lab/
├── 2_youtube_and_web/
│   ├── tools/
│   │   ├── AddVideoToVectorDBTool.py
│   │   └── FetchLatestVideosFromYouTubeChannelTool.py
│   ├── crew.py          # Main CrewAI orchestration logic
│   ├── main.py          # Entry point script
│   ├── .env             # API keys and environment configs
├── .gitignore
├── poetry.lock
├── pyproject.toml
└── README.md


⸻

🧩 How it works (Explained)

🕹️ Agents & Tools

✅ Agents
	•	Scrape Agent: Fetches latest video metadata.
	•	Vector DB Processor: Stores videos in a vector DB.
	•	General Research Agent: Fills in content creator info.
	•	Follow-up Agent: Searches for missing details.
	•	Fallback Agent: Does final web searches if needed.

✅ Tools
	•	FetchLatestVideosFromYouTubeChannelTool.py: Uses the YouTube API to get video details.
	•	AddVideoToVectorDBTool.py: Adds fetched data to your vector DB (e.g., Pinecone, FAISS).

✅ Tasks
	•	Scrape channel → Vectorize videos → Fill out ContentCreatorInfo → Follow up on missing info → Final fallback search.

⸻

⚙️ Setup & Installation

1️⃣ Clone the repo

git clone https://github.com/yourusername/agentfleet-rag-lab.git
cd agentfleet-rag-lab/2_youtube_and_web

2️⃣ Install dependencies

Make sure you have Poetry installed.

poetry install --no-root

3️⃣ Create .env file

In 2_youtube_and_web/, create a .env file with your API keys:

YOUTUBE_API_KEY=your_youtube_api_key
OPENAI_API_KEY=your_openai_api_key
# Add other relevant keys if needed


⸻

📡 Setup YouTube API v3
	1.	Go to the YouTube Data API v3 page on Google Cloud.
	2.	Click Enable.
	3.	Go to API Credentials and create an API Key.
	4.	Paste that key in your .env as YOUTUBE_API_KEY.

⸻

🚀 Run the YouTube Crew

From the 2_youtube_and_web/ directory:

python crew.py

This will:
	•	Fetch the latest videos from your target channel.
	•	Add video metadata to the vector database.
	•	Run the multi-agent tasks to enrich and verify the data.

⸻
