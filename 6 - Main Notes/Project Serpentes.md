 Project: Serpent Library - Smart Snake Info Web App
 ================================================

1. Project Goal
 ---------------
Build a modern web app that shows detailed snake information 
(species, images, venom, antivenom), integrated with AI to answer 
snake-related questions conversationally.


 2. Core Features
 ----------------
- 🐍 View all snake species
- 📷 View snake images
- ☠️ Show venom type (e.g., hemotoxic, neurotoxic)
- 💉 Display required antivenom
- 🤖 AI Chat: Ask questions about any snake, treatment, danger level, etc.


 3. APIs to Use
 --------------

A. iNaturalist API
- Endpoint: https://api.inaturalist.org/v1/taxa?q=snake
- Docs: https://api.inaturalist.org/v1/docs/
- Use for: Snake species data, scientific names, common names, images, region info

B. GBIF API (Global Biodiversity Information Facility)
- Docs: https://www.gbif.org/developer/summary
- Use for: Species classification, taxonomy, geographical distribution

C. Reptile Database (Manual scraping or custom data)
- Site: https://reptile-database.reptarium.cz/
- Use for: Venom info (basic), detailed taxonomic hierarchy

D. WHO/CDC/HerpMapper (Manual data or scraping)
- Use for: Antivenom and venom type data (not public APIs)
- Example: WHO Snakebite Information and Antivenom Lists


 4. Custom Dataset (Important)
 -----------------------------
Because venom and antivenom data is not widely available via API,
you’ll need to:
- Create a custom JSON/CSV or Mongo/Postgres DB
- Fields: species name, venom type, danger level, antivenom name, symptoms, first-aid


 5. AI Integration
 -----------------
- Use: OpenAI GPT-4 or GPT-4o API
- Mode: Chat or function-calling
- Use cases:
  - “What is the danger level of Inland Taipan?”
  - “What should I do if bitten by this snake?”
  - “Where is it found?”
- Optional: Embed AI on species detail page or a global chatbot on the app

API Docs: https://platform.openai.com/docs


 6. Tech Stack (Suggested)
 --------------------------
Frontend:
- React or Next.js
- Chakra UI or Tailwind CSS

Backend:
- Node.js + Express (or Next.js API routes)
- MongoDB (Atlas) or PostgreSQL (supabase)

AI:
- OpenAI API (for GPT-4)
- Optional: Use LangChain if you want memory / function calls

Deployment:
- Vercel (Frontend & API routes)
- Render/Fly.io (if using Express separately)

Image Hosting:
- Use TMDB-style helper to build image URL from iNaturalist API image keys
- Fallback: Use CDN or upload safe images manually


7. Bonus Ideas
 --------------
- Upload image to detect snake (vision model)
- Add snake danger meter (Low / Moderate / High)
- Interactive Map with snake location
- Gamified quiz: “Guess the snake”
- PWA: Offline mode for emergency info


 8. Real-World Value
 -------------------
✅ Educational: Learn about biodiversity  
✅ Medical: Know which snakes are dangerous  
✅ Useful in rural areas or hikers  
✅ Unique blend of biodiversity + AI + FE


 9. Resume Worthiness
 --------------------
✅ Yes! Demonstrates:
- API integration
- Real-world data usage
- AI features
- Custom data modeling
- Frontend UI/UX
- Good problem-solving and initiative


 10. Next Steps
 --------------
[ ] Create design layout (Home, Species List, Detail, Chat)
[ ] Start with iNaturalist API integration
[ ] Build snake detail UI
[ ] Create backend DB for venom & antivenom
[ ] Integrate OpenAI chat
[ ] Style and deploy

