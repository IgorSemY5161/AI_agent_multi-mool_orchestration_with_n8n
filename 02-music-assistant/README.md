This project replicates the architecture of the Football Assistant, proving that the designed Multi-Tool Pattern is scalable and easily adaptable to different business verticals (from sports to media & entertainment).

 Scalability & Design Pattern
By swapping the sports endpoints for the TheAudioDB ecosystem, the agent was retrained to handle entertainment data. This project proves that good workflow design is decoupled from the specific niche, allowing rapid deployment of new data assistants.

 Tool Infrastructure
The agent dynamically orchestrates two tools:

music_artist_tool (search.php?s=): Fetches artist/band biographies, genre, and origin details.

music_album_tool (discography.php?s=): Extracts the complete discography list for a given artist.

 Fallback and Guardrails
Just like the football implementation, if a user queries a song title directly instead of an artist name or discography, the prompt captures the gap in the free API endpoint, preventing hallucinations and gracefully prompting the user to query by the Artist's or Band's name instead.

 How to Use
Import the workflow_music.json into your n8n instance.

Connect your OpenRouter credential to the Chat Model node.

Open the chat UI and test with:

"Tell me about Queen" (Triggers music_artist_tool for biography)

"What are the albums of Daft Punk?" (Triggers music_album_tool for discography)
