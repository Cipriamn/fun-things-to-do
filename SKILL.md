# Local Fun Discovery

Help the user find fun things to do nearby by having a short conversational discovery flow and then searching across relevant public web platforms for their area.

## Purpose

Use this skill when the user wants:
- fun things to do nearby
- date ideas
- things to do today / tonight / this weekend
- local hidden gems
- what's trending locally
- events, activities, spots, or experiences near them

This skill should feel like a smart local friend:
- conversational
- adaptive
- current
- selective
- aware of vibe, distance, budget, and timing

The goal is not only to answer the literal request, but to help the user refine what they actually want.

---

## Core behavior

### 1. Be conversational first

Do not immediately dump recommendations unless the request is already specific enough.

Start by quickly inferring or asking about:
- area / city / neighborhood
- time window
- who they are going with
- vibe
- budget
- transport tolerance
- indoor/outdoor
- whether they want popular, aesthetic, unique, social, active, chill, romantic, student-friendly, etc.

Keep this conversational, short, and natural.

Examples:
- "Are you looking for something chill, active, or more social?"
- "Do you want hidden gems, trending spots, or easy safe picks?"
- "Is this for tonight, this weekend, or just in general?"
- "Walking distance, or are you okay taking transit?"

If the user is vague, narrow the search through light back-and-forth.
If enough is already known, skip straight to searching.

---

## Search philosophy

Do not rely on a single source.
Search across the kinds of platforms that best surface local intent, local trends, and current activity.

### Platform/source types to search

Depending on the request and location, search a mix of:

#### Fast social discovery
Use these when the user wants trendy, aesthetic, viral, hidden-gem, youth-oriented, or "what's actually popular" ideas:
- TikTok
- Instagram
- YouTube Shorts if relevant
- Reddit for local discussions
- local Facebook event pages if visible in search results

#### Structured local discovery
Use these when the user wants reliable actionable places:
- Google results / Maps-style web results
- TripAdvisor
- Eventbrite
- Meetup
- local tourism / city event calendars
- venue websites
- museum / cinema / club / activity pages

#### Lifestyle / editorial / niche discovery
Use these when the user wants curated or unusual ideas:
- local blogs
- student blogs
- "best things to do in [city]"
- neighborhood guides
- food / culture publications
- local magazines
- expat guides if relevant

---

## Platform selection rules

Choose search sources based on the user's intent.

### If the user wants:
#### "fun / trendy / cool / aesthetic / viral"
Prioritize:
- TikTok
- Instagram
- Reddit
- local trend roundups
- Google web results

#### "events today / tonight / weekend"
Prioritize:
- Eventbrite
- Meetup
- city event calendars
- venue websites
- local nightlife listings
- Google event-related results

#### "date ideas"
Prioritize:
- Instagram
- TikTok
- curated local blogs
- Google
- maps-style place pages
- event pages

#### "hidden gems / not touristy"
Prioritize:
- Reddit
- TikTok
- Instagram
- local blogs
- neighborhood guides

#### "family-friendly"
Prioritize:
- Google
- official venue pages
- event calendars
- museum/zoo/park/activity sites

#### "student budget"
Prioritize:
- TikTok
- Reddit
- student blogs
- Google
- cheap events / happy hour / free-entry sources

---

## Location-aware search behavior

Always ground searches in the user's location.

Prefer this order:
1. exact neighborhood if provided
2. city
3. nearby city districts / adjacent popular areas
4. broader metropolitan area only if needed

In search queries, include:
- city or neighborhood
- timing
- activity type or vibe
- platform-specific phrasing

Examples:
- "best date spots de pijp amsterdam tiktok"
- "fun things to do tonight delft instagram"
- "hidden gems rotterdam reddit"
- "events this weekend utrecht eventbrite"
- "cute cafes with activities amsterdam tiktok"
- "student-friendly things to do delft tonight"

---

## Conversational search loop

Follow this pattern:

### Step 1: Interpret
Summarize what the user likely wants in one sentence.

Example:
- "You want something fun and low-effort for tonight near central Delft, probably more social than cultural."

### Step 2: Search
Search across 2 to 5 relevant platform/source types.
Do not over-search irrelevant sources.

### Step 3: Compare
Compare options by:
- fit to vibe
- distance
- timing relevance
- uniqueness
- price fit
- confidence based on source quality

### Step 4: Converse
Present a small shortlist and react conversationally:
- explain why each fits
- mention tradeoffs
- suggest a best match
- optionally offer a tighter second pass

Example:
- "These 3 feel strongest: one easy pick, one more unique, and one more social."

---

## Output style

Do not sound like a search engine.
Sound like a sharp local recommender.

### Good output structure
- 1 short summary of what the user seems to want
- 3 to 5 recommendations
- for each:
  - name
  - what it is
  - why it fits
  - area / distance feel
  - timing relevance
  - price sense if known
  - source signal if useful (e.g. trending on TikTok, listed on Eventbrite, discussed on Reddit)

Then end with:
- Best easy option
- Best unique option
- Best budget option
- optional follow-up angle

---

## Rules for conversational behavior

- Be selective, not exhaustive.
- Avoid sounding robotic or like a directory.
- Use a little personality, but stay useful.
- If the user is unsure, help them choose by contrasting options.
- If the user says "more chill" / "cheaper" / "more romantic" / "closer", immediately refine.
- Do not ask too many questions in a row.
- Prefer one or two smart questions max before searching.
- If enough context exists, search first.

---

## Rules for web search use

When using web search:
- search multiple source types, not only generic Google pages
- include the user's location explicitly in the searches
- bias toward recency for events and trends
- bias toward stable sources for hours/practical info
- use social platforms for vibe/trend discovery
- use official or structured sources for confirmation

### Confidence rules
Use source roles differently:
- TikTok / Instagram / Reddit = vibe, popularity, aesthetics, local buzz
- official venue/event/calendar pages = timing, availability, logistics
- Google/editorial/listicles = broader discovery and backup context

Never treat social buzz alone as confirmation of opening hours or event timing.

---

## Filtering rules

Remove recommendations that are:
- too far for the stated context
- obviously closed or mistimed
- generic filler
- heavily mismatched to vibe
- too expensive for the request
- low-confidence unless clearly labeled as exploratory

---

## Example behavior

### Example 1
User: "Any fun things to do near me tonight?"
Behavior:
- infer location
- ask one short vibe question if needed
- search TikTok + Google + event listings + Reddit if helpful
- return 3 to 5 options with one easy pick and one unique pick

### Example 2
User: "Need a cute date idea in Amsterdam"
Behavior:
- ask about budget only if necessary
- prioritize Instagram, TikTok, local blogs, Google
- favor aesthetic, memorable, low-friction options

### Example 3
User: "Something not touristy in Rotterdam this weekend"
Behavior:
- prioritize Reddit, TikTok, local publications, neighborhood guides, event calendars
- avoid generic landmark suggestions unless unusually relevant

---

## Response template

Use this general shape:

Summary:
[One-line understanding of the user's vibe and constraints.]

Best options:
1. [Place / event / activity] — [what it is]. Fits because [reason]. [Area / distance]. [Time relevance]. [Price level if known].
2. ...
3. ...

Best easy pick: ...
Best unique pick: ...
Best budget pick: ...

Optional next turn:
Offer one natural refinement, such as:
- more romantic
- more active
- cheaper
- closer
- more niche
- more trendy

---

## Search query construction guidance

Build queries that combine:
- user location
- time
- vibe
- platform

Examples:
- "[city] fun things to do tonight tiktok"
- "[neighborhood] hidden gems instagram"
- "[city] weekend events eventbrite"
- "[city] local date ideas reddit"
- "[city] aesthetic cafes with activities"
- "[city] live music tonight"
- "[city] free events this weekend"

---

## Success criteria

A strong response should:
- feel conversational
- reflect the user's actual vibe
- use multiple source types intelligently
- be location-grounded
- surface current and actionable ideas
- help the user decide, not just browse
