===== IMPORTANT: CONCEPT FIRST, THEN IMPLEMENTATION =====

Before we build ANYTHING backend, frontend must understand concepts.

For EVERY section involving API, database, or backend:

STEP 1: EXPLAIN THE CONCEPT (Simple words, no jargon)

Example:

What is an API?

"API = a way for frontend and backend to talk to each other.

Frontend is the website you see in browser.
Backend is a computer running on a server.

They cannot talk directly. They use API.

Think of API like a phone call:
- Frontend says: 'Hello, I want to like pet #5'
- API receives this
- API tells backend: 'Someone wants to like pet #5'
- Backend does the work (saves to database)
- API sends answer back to frontend: 'Done! Now pet #5 has 42 likes'
- Frontend updates the screen

Without API, frontend and backend cannot communicate."

STEP 2: EXPLAIN THE STRUCTURE

What is a Route?

"Route = one API conversation.

Example routes:

Route 1: GET /api/posts
- Frontend asks: 'Give me all pet posts'
- Backend responds: 'Here are 10 pet posts with images and like counts'

Route 2: POST /api/like
- Frontend says: 'User 5 likes pet 8'
- Backend responds: 'Saved! Pet 8 now has 42 likes'

Route 3: POST /api/login
- Frontend says: 'Username: john, Password: pass123'
- Backend responds: 'Login successful. Here is your token: xyz123'

Each route = one specific conversation."

STEP 3: EXPLAIN HTTP METHODS

Why GET vs POST?

"GET = asking for data (like going to ask a friend 'what time is it?')
POST = sending data (like telling a friend 'I like this song')

GET: 'Give me all pets'
POST: 'Save that I like this pet'
PUT: 'Update my profile'
DELETE: 'Remove this post'

Different methods = different actions."

STEP 4: EXPLAIN REQUEST AND RESPONSE

What happens in one API call?

"Request:
- Frontend sends: { petId: 5, userId: 2 }
- This is the question

Response:
- Backend sends back: { success: true, likes: 42 }
- This is the answer

Frontend waits for response before doing anything.
Like asking a question and waiting for answer."

===== NOW IMPLEMENT =====

After explaining concept, THEN build it.

Example:

TEACHER SAYS:

"Now you understand API. You understand routes. You understand GET/POST.

Let's implement the LIKE API route."

STUDENT PROMPT (your own words):

"We understand API now. Create a POST /api/like route in backend. When frontend sends { petId: 5, userId: 2 }, backend saves it to database and sends back { success: true, newLikeCount: 42 }"

Claude builds it.

You check git diff.

EXPLAIN WHAT CLAUDE BUILT:
- Show the code
- Point out: "See? This is POST (sending data)"
- Point out: "See? This is the route /api/like"
- Point out: "See? This saves to database"
- Point out: "See? This sends response back"

COMMIT: "Add POST /api/like route"

===== RULE: CONCEPT FIRST, ALWAYS =====

Never jump to code without explaining concept.

Bad flow:
"Build a REST API" → Claude builds → Confusion

Good flow:
"What is REST? What is stateless? What are status codes?" → Claude explains → "Now build REST API" → Claude builds → Understanding

===== FOR THIS PET APP:

When we reach FILE 05 (Backend API):

TEACH FIRST:
- What is an API?
- What is a route?
- What is a request/response?
- What are HTTP methods (GET, POST)?
- What is a status code (200, 404, 500)?
- What is JSON (data format)?

THEN:
- Build first route: GET /api/posts
- Build second route: POST /api/like
- Build third route: POST /api/login

Each route = one prompt = one learning.

===== CONCEPTS TO TEACH BEFORE BUILDING:

BEFORE FILE 05 (Backend):
- API definition
- Request/Response cycle
- HTTP methods
- Routes

BEFORE FILE 07 (Database):
- What is a database?
- Tables vs Rows vs Columns
- Primary key / Foreign key
- SQL basics (SELECT, INSERT, UPDATE)

BEFORE FILE 08 (Authentication):
- What is authentication?
- What is a session?
- What is a token?
- How login works

BEFORE FILE 10 (Upload):
- How file upload works
- Where files are stored
- Security considerations

===== FORMAT FOR TEACHING CONCEPTS =====

When teaching a concept:

SIMPLE EXPLANATION:
"Here is [concept] in simple words..."

REAL WORLD EXAMPLE:
"Think of it like [real world thing]..."

VISUAL OR STRUCTURE:
Show how it works with text diagram

WHY IT MATTERS:
"We need this because [reason]..."

Then: "Now let's build it."

===== STUDENT WRITES THE PROMPT =====

After concept explanation, student should write their own prompt.

Teacher gives template, student fills in:

Template:
"We understand [concept]. Now [action]. Build [what]."

Example:
"We understand API routes. Now let's implement. Build a GET /api/posts route that returns list of all pets with their like counts."

Student types this (not copy-paste).

Claude builds.

Student learns prompt writing.

===== THIS IS CRITICAL =====

Prompt engineering means:
- Understanding what you want to build
- Explaining it clearly to AI
- AI builds it correctly

If student doesn't understand concept, their prompt will be bad.
Claude will build bad code.

If student understands concept, their prompt will be clear.
Claude will build good code.

That's why concept first.

===== FOR EVERY SECTION =====

Repeat this pattern:

1. EXPLAIN CONCEPT (no code)
2. SHOW STRUCTURE (with diagrams)
3. GIVE TEMPLATE PROMPT (what good prompt looks like)
4. STUDENT WRITES PROMPT (using template, but their own words)
5. CLAUDE BUILDS
6. EXPLAIN CODE
7. COMMIT

This teaches both:
- The technical skill (coding)
- The AI skill (prompting)
- The thinking skill (understanding concepts)