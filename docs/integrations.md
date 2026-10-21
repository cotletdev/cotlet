# Cotlet integrations catalog

[← Back to README](../README.md) · Live catalog: [cotlet.dev/integrations](https://cotlet.dev/integrations) · Machine-readable: [cotlet.dev/integrations.json](https://cotlet.dev/integrations.json)

Cotlet hosts an MCP server and a REST API for each of the **97 apps** below. Every one of them lacks a usable official API for the work people actually want to hand to an AI agent. The "Official API" column says what the vendor offers today:

| Label | Meaning | Apps |
|---|---|---|
| **No official API** | No public API, developer docs or keys | 26 |
| **Limited official API** | Read-only, or missing the endpoints people need | 31 |
| **Partners-only API** | Only for approved partners, after an application or contract | 28 |
| **Paid API add-on** | Only on a top plan or as a separate paid product | 12 |

Each app links to its page on cotlet.dev with sources for the official API status, every tool with its parameters and example responses, and use cases. Add `.md` to any integration URL for a Markdown version.

Over MCP each app is one tool (`skool`) and its endpoints are operations (`list_members`); over REST the same endpoint is `GET /api/v1/skool/groups/{group}/members`.

## Creators & communities

19 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Substack](https://cotlet.dev/integrations/substack-api-mcp-server) | Limited official API | Posts, Notes, subscribers and stats for your publication. | Create post, Schedule post, Publish Note, List subscribers, Get post stats |
| [Skool](https://cotlet.dev/integrations/skool-api-mcp-server) | No official API | Posts, members and DMs for your Skool community. | List members, Approve membership request, Create post, Reply to comment, Send DM, Get engagement stats |
| [Meetup](https://cotlet.dev/integrations/meetup-api-mcp-server) | Paid API add-on | Events, RSVPs and member messages without Meetup Pro. | Create event, Copy event, List RSVPs, Message members |
| [Medium](https://cotlet.dev/integrations/medium-api-mcp-server) | Limited official API | Publish, edit and track stats for your Medium posts. | Create post, Edit post, Cross-post article, Get post stats |
| [Riverside](https://cotlet.dev/integrations/riverside-api-mcp-server) | Limited official API | Studios, guest invites and recordings on Pro and Standard. | Create studio, Schedule session, Invite guest, Download recording |
| [Partiful](https://cotlet.dev/integrations/partiful-api-mcp-server) | No official API | Invites, guest lists and text blasts for your events. | Create invite, List RSVPs, Export guest list, Send text blast |
| [Dribbble](https://cotlet.dev/integrations/dribbble-api-mcp-server) | Limited official API | Messages, Pro analytics and engagement for designers. | Reply to message, Get Pro analytics, List shots, Upload shot |
| [SoundCloud](https://cotlet.dev/integrations/soundcloud-api-mcp-server) | Paid API add-on | Tracks, playlists, comments and stats for your SoundCloud profile. | Upload track, Update track details, Create playlist, List comments, Reply to comment, Get track stats |
| [Bandsintown](https://cotlet.dev/integrations/bandsintown-api-mcp-server) | Limited official API | Tour dates, fan messages and stats for your Bandsintown artist page. | Add event, Update event, Delete event, Send fan message, Get fan stats, List upcoming events |
| [Patreon](https://cotlet.dev/integrations/patreon-api-mcp-server) | Limited official API | Posts, patron messages and members for your Patreon page. | Create post, Send message to patron, List members, Update tier, Schedule post, Export earnings |
| [Bandcamp](https://cotlet.dev/integrations/bandcamp-api-mcp-server) | Partners-only API | Sales, merch orders, releases and fan messages for your Bandcamp page. | List sales, Mark order shipped, List merch orders, Update release, Send fan message, Export sales report |
| [Quora](https://cotlet.dev/integrations/quora-api-mcp-server) | No official API | Answers, questions and Spaces from your Quora account. | Search questions, Post answer, List my answers, Get answer stats, Post to Space |
| [Libsyn](https://cotlet.dev/integrations/libsyn-api-mcp-server) | Partners-only API | Episodes, scheduling and stats for your Libsyn podcast. | Upload episode, Schedule episode, Update show notes, Get download stats, List episodes |
| [DICE](https://cotlet.dev/integrations/dice-api-mcp-server) | Limited official API | Events, ticket tiers, sales and guest lists for DICE promoters. | Create event, Update ticket tier, Get sales report, List ticket holders, Issue comp tickets |
| [Whova](https://cotlet.dev/integrations/whova-api-mcp-server) | No official API | Agenda, attendees and announcements for your Whova event. | Add session, Import attendees, Send announcement, List registrations, Export engagement |
| [SignUpGenius](https://cotlet.dev/integrations/signupgenius-api-mcp-server) | Paid API add-on | Create sign-ups, manage slots and message participants on SignUpGenius. | Create sign-up, Add slots, List participants, Swap participant, Message group |
| [Paperless Post](https://cotlet.dev/integrations/paperless-post-api-mcp-server) | No official API | Guest lists, RSVPs and messages for Paperless Post events. | List events, Add guests, Send invitation, Get RSVPs, Message guests |
| [Evite](https://cotlet.dev/integrations/evite-api-mcp-server) | No official API | Events, guest lists, RSVPs and messages on Evite. | Create event, Add guests, Get RSVPs, Message guests, Update event |
| [Joy](https://cotlet.dev/integrations/joy-api-mcp-server) | No official API | Guest list, RSVPs and registry for your Joy wedding. | List guests, Add guest, Get RSVP status, Update event details, List registry gifts |

## Courses & training

10 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Udemy](https://cotlet.dev/integrations/udemy-api-mcp-server) | Limited official API | Coupons, course updates, announcements and revenue for instructors. | Create coupon, Update course, Send announcement, Get revenue report |
| [Teachable](https://cotlet.dev/integrations/teachable-api-mcp-server) | Limited official API | Course content, coupons, emails and comments on any plan. | Update lecture, Create coupon, Send email, Reply to comment, List enrollments |
| [ThriveCart](https://cotlet.dev/integrations/thrivecart-api-mcp-server) | Limited official API | Products, checkouts, refunds and affiliates for sellers. | Create product, Create checkout, Issue refund, List affiliates |
| [Payhip](https://cotlet.dev/integrations/payhip-api-mcp-server) | Limited official API | Products, sales, customers, coupons and refunds for sellers. | Create product, List sales, List customers, Create coupon, Issue refund |
| [Uscreen](https://cotlet.dev/integrations/uscreen-api-mcp-server) | Limited official API | Videos, collections, live events and analytics for creators. | Upload video, Update collection, Create live event, Get analytics |
| [Systeme.io](https://cotlet.dev/integrations/systeme-io-api-mcp-server) | Limited official API | Funnels, email campaigns and sales reports for marketers. | Update funnel page, Edit email campaign, List orders, Get sales report |
| [Trainerize](https://cotlet.dev/integrations/trainerize-api-mcp-server) | Paid API add-on | Clients, programs, check-ins and messages for your Trainerize business. | List clients, Assign program, Message client, Log body stats, Schedule appointment |
| [Everfit](https://cotlet.dev/integrations/everfit-api-mcp-server) | Paid API add-on | Clients, programs and messages for your Everfit coaching business. | List clients, Assign program, Message client, Add autoflow, Get client metrics |
| [TrueCoach](https://cotlet.dev/integrations/truecoach-api-mcp-server) | Limited official API | Workouts, programs and client messages for your TrueCoach roster. | List clients, Create workout, Assign program, Read workout results, Message client |
| [Teachers Pay Teachers](https://cotlet.dev/integrations/teachers-pay-teachers-api-mcp-server) | No official API | Products, prices and sales reports for TPT sellers. | List products, Create product listing, Update price, Get sales report, Answer buyer question |

## Travel

13 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [GetYourGuide](https://cotlet.dev/integrations/getyourguide-api-mcp-server) | Partners-only API | Availability, pricing and bookings for tour operators. | List bookings, Update availability, Update pricing, Get booking |
| [Wanderlog](https://cotlet.dev/integrations/wanderlog-api-mcp-server) | No official API | Build and edit trip itineraries from your agent. | Create trip, Add place, Import booking, Update itinerary |
| [Hostelworld](https://cotlet.dev/integrations/hostelworld-api-mcp-server) | Partners-only API | Reviews, guest messages and reservations for hostel owners. | List reservations, Reply to review, Reply to guest, Get payouts report |
| [Klook](https://cotlet.dev/integrations/klook-api-mcp-server) | Partners-only API | Search and book activities from your agent. | Search activities, Book activity, List bookings |
| [Omio](https://cotlet.dev/integrations/omio-api-mcp-server) | Partners-only API | Book and change train, bus and flight tickets. | Search trips, Book ticket, Change booking |
| [Polarsteps](https://cotlet.dev/integrations/polarsteps-api-mcp-server) | No official API | Export and import trips and steps. | Export trip, Import steps, List trips |
| [Hipcamp](https://cotlet.dev/integrations/hipcamp-api-mcp-server) | Partners-only API | Calendar, pricing and guest messages for hosts. | Sync calendar, Update pricing, Reply to guest, List bookings |
| [Kiwi.com](https://cotlet.dev/integrations/kiwi-com-api-mcp-server) | Limited official API | Bookings, trips and refunds on your Kiwi.com account. | Search flights, List my bookings, Add baggage, Request refund, Check in |
| [SiteMinder](https://cotlet.dev/integrations/siteminder-api-mcp-server) | Partners-only API | Rates, availability and reservations in your SiteMinder channel manager. | Update rates, Close dates, List reservations, Update inventory, Get channel performance |
| [Tiqets](https://cotlet.dev/integrations/tiqets-api-mcp-server) | Partners-only API | Book, fetch and cancel attraction tickets on your Tiqets account. | Search tickets, Check availability, Book tickets, List my bookings, Download e-tickets, Cancel booking |
| [Little Hotelier](https://cotlet.dev/integrations/little-hotelier-api-mcp-server) | Partners-only API | Bookings, rates and availability for your Little Hotelier property. | List bookings, Update rates, Update availability, Create booking, Message guest, Get occupancy report |
| [Airalo](https://cotlet.dev/integrations/airalo-api-mcp-server) | Partners-only API | Buy, top up and track eSIMs on your Airalo account. | List my eSIMs, Check data usage, Buy eSIM, Top up eSIM, Get install instructions |
| [Civitatis](https://cotlet.dev/integrations/civitatis-api-mcp-server) | Partners-only API | Bookings, availability and tours for Civitatis activity suppliers. | List bookings, Update availability, Close dates, Get booking details, List payouts |

## Real estate

13 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Idealista](https://cotlet.dev/integrations/idealista-api-mcp-server) | Partners-only API | Your listings and leads on Idealista, managed by an agent. | List my listings, Update listing, Renew listing, Reply to lead |
| [Crexi](https://cotlet.dev/integrations/crexi-api-mcp-server) | Partners-only API | Leads, comps and listing analytics for commercial real estate. | Export leads, List saved searches, Get comps, Get listing analytics, Create listing |
| [Zoopla](https://cotlet.dev/integrations/zoopla-api-mcp-server) | Partners-only API | Listings, leads and performance stats for agents and landlords. | List my listings, Update listing, Reply to lead, Get listing stats |
| [Mashvisor](https://cotlet.dev/integrations/mashvisor-api-mcp-server) | Paid API add-on | Saved searches, property analyses and exports from your account. | Run saved search, Get property analysis, Export properties |
| [Rent Manager](https://cotlet.dev/integrations/rent-manager-api-mcp-server) | Partners-only API | Charges, work orders and tenant messages for property managers. | Post charge, Create work order, Message tenant, List tenants |
| [REsimpli](https://cotlet.dev/integrations/resimpli-api-mcp-server) | Limited official API | Leads, deal stages and drip campaigns for real estate investors. | Create lead, Update deal stage, Start drip campaign, Get skip-trace results |
| [DoorLoop](https://cotlet.dev/integrations/doorloop-api-mcp-server) | Paid API add-on | Tenants, leases, rent charges and payments for landlords. | List tenants, Create lease, Post rent charge, Record payment |
| [Peerspace](https://cotlet.dev/integrations/peerspace-api-mcp-server) | No official API | Inquiries, bookings and listings for your Peerspace venue. | List booking requests, Reply to inquiry, Send custom proposal, Accept booking, Update listing pricing |
| [Rently](https://cotlet.dev/integrations/rently-api-mcp-server) | Limited official API | Tours, prospects and listings in your Rently self-touring account. | List tours, Get prospect details, Update listing availability, Create lock code, Export leads |
| [Hemnet](https://cotlet.dev/integrations/hemnet-api-mcp-server) | No official API | Listings, sold prices, saved homes and searches for Hemnet buyers. | Search listings, Get sold prices, List saved homes, Save search, Follow home value |
| [Property Finder](https://cotlet.dev/integrations/property-finder-api-mcp-server) | Partners-only API | Listings, leads and credits in your Property Finder broker account. | Publish listing, Unpublish listing, List leads, Update agent, Get listing stats |
| [Bayut](https://cotlet.dev/integrations/bayut-api-mcp-server) | Partners-only API | Listings, leads and performance for Bayut agents. | Publish listing, Edit listing, List leads, Get listing performance, Refresh listing |
| [Immobiliare.it](https://cotlet.dev/integrations/immobiliare-api-mcp-server) | Partners-only API | Your listings, messages and visit requests on Immobiliare.it. | List my listings, Create listing, Reply to message, Request visit, Save search |

## Local services & SaaS

35 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Faire](https://cotlet.dev/integrations/faire-api-mcp-server) | Limited official API | Orders, inventory, reorders and messages for wholesale brands. | List orders, Update inventory, Create reorder, Reply to message |
| [Booksy](https://cotlet.dev/integrations/booksy-api-mcp-server) | Partners-only API | Bookings, client replies and reports for beauty businesses. | List bookings, Create booking, Reschedule booking, Reply to client, Export report |
| [Vagaro](https://cotlet.dev/integrations/vagaro-api-mcp-server) | Limited official API | Bookings, waitlists and client replies across locations. | List appointments, Create appointment, Reschedule appointment, Manage waitlist, Reply to client |
| [Buildertrend](https://cotlet.dev/integrations/buildertrend-api-mcp-server) | Partners-only API | Schedules, daily logs, change orders and selections for builders. | Get schedule, Create daily log, Create change order, List selections |
| [Pirate Ship](https://cotlet.dev/integrations/pirate-ship-api-mcp-server) | No official API | Labels, rates and tracking for small shippers. | Get rates, Buy labels in bulk, Import orders, Track shipment, File claim |
| [Fresha](https://cotlet.dev/integrations/fresha-api-mcp-server) | Partners-only API | Appointments, clients, sales and payouts for salons and spas. | List appointments, Create appointment, List clients, Get daily sales, Export data |
| [Workiz](https://cotlet.dev/integrations/workiz-api-mcp-server) | Limited official API | Jobs, scheduling, invoices and payments for field service. | List jobs, Schedule job, Create invoice, Record payment |
| [GlossGenius](https://cotlet.dev/integrations/glossgenius-api-mcp-server) | No official API | Appointments, clients and sales for salon owners. | List appointments, Book appointment, Reschedule appointment, List clients, Get sales |
| [Nextdoor](https://cotlet.dev/integrations/nextdoor-api-mcp-server) | Partners-only API | Posts, comments and recommendations for your Nextdoor business page. | Create post, Reply to comment, List recommendations, Create event, Create For Sale listing, Get page stats |
| [AccuLynx](https://cotlet.dev/integrations/acculynx-api-mcp-server) | Paid API add-on | Jobs, contacts, photos and estimates in your AccuLynx account. | Create job, Update job milestone, Add contact, Upload photo, List estimates, Add job note |
| [Thumbtack](https://cotlet.dev/integrations/thumbtack-api-mcp-server) | Partners-only API | Leads, messages, quotes and reviews for your Thumbtack pro profile. | List leads, Reply to lead, Send quote, Update weekly budget, List reviews, Export past leads |
| [Milanote](https://cotlet.dev/integrations/milanote-api-mcp-server) | No official API | Boards, notes and links in your Milanote workspace. | List boards, Add note, Add link, Upload image, Export board |
| [Setmore](https://cotlet.dev/integrations/setmore-api-mcp-server) | Paid API add-on | Bookings, customers and staff calendars in your Setmore account. | List appointments, Create appointment, Reschedule appointment, Cancel appointment, Find customer |
| [Service Fusion](https://cotlet.dev/integrations/service-fusion-api-mcp-server) | Paid API add-on | Jobs, customers, estimates and invoices in your Service Fusion account. | Create job, List customers, Create estimate, Create invoice, Update job status |
| [Mangomint](https://cotlet.dev/integrations/mangomint-api-mcp-server) | No official API | Appointments, clients and sales for your Mangomint salon or spa. | List appointments, Book appointment, Reschedule appointment, Find client, Export sales report |
| [PushPress](https://cotlet.dev/integrations/pushpress-api-mcp-server) | Limited official API | Members, classes, reservations and check-ins for your PushPress gym. | List members, Book class reservation, Check in member, Cancel reservation, Update membership plan |
| [Momence](https://cotlet.dev/integrations/momence-api-mcp-server) | Limited official API | Classes, bookings and members for your Momence studio. | List sessions, Book customer into class, Check in member, Create class, Freeze membership |
| [Mariana Tek](https://cotlet.dev/integrations/mariana-tek-api-mcp-server) | Partners-only API | Classes, reservations and customers for your Mariana Tek studio. | List classes, Book reservation, Cancel reservation, Find customer, Add class credits |
| [Meevo](https://cotlet.dev/integrations/meevo-api-mcp-server) | Partners-only API | Appointments, clients and memberships in your Meevo salon. | List appointments, Book appointment, Find client, Sell package, Pull daily sales |
| [MarketSharp](https://cotlet.dev/integrations/marketsharp-api-mcp-server) | Limited official API | Leads, appointments and jobs in your MarketSharp contractor CRM. | Create lead, Update appointment, List jobs, Add note, Get contract status |
| [DaySmart](https://cotlet.dev/integrations/daysmart-api-mcp-server) | No official API | Appointments, clients, pets and sales in DaySmart Salon or Pet. | List appointments, Book appointment, Find client, Update pet record, Export sales |
| [ClockShark](https://cotlet.dev/integrations/clockshark-api-mcp-server) | Limited official API | Timesheets, schedules and jobs in your ClockShark account. | List time entries, Approve timesheet, Create job, Schedule shift, Export payroll hours |
| [Houzz Pro](https://cotlet.dev/integrations/houzz-pro-api-mcp-server) | No official API | Leads, projects, estimates and invoices in Houzz Pro. | List leads, Create project, Create estimate, Send invoice, Update lead status |
| [Perfect Venue](https://cotlet.dev/integrations/perfect-venue-api-mcp-server) | Paid API add-on | Events, leads, proposals and payments for your Perfect Venue venue. | List events, Create lead, Update event details, Send proposal, List payments |
| [Zola](https://cotlet.dev/integrations/zola-api-mcp-server) | No official API | Guest list, RSVPs and registry for your Zola wedding. | List guests, Add guest, Track RSVPs, List registry gifts, Mark thank-you sent |
| [Contractor Foreman](https://cotlet.dev/integrations/contractor-foreman-api-mcp-server) | Limited official API | Projects, estimates, daily logs and invoices in Contractor Foreman. | Create estimate, Add daily log, Create change order, Update schedule, List invoices, Get job costing |
| [Zen Planner](https://cotlet.dev/integrations/zen-planner-api-mcp-server) | Partners-only API | Members, classes, attendance and billing in Zen Planner. | List members, Book class, Record attendance, Enroll in membership, List failed payments |
| [Service Autopilot](https://cotlet.dev/integrations/service-autopilot-api-mcp-server) | Partners-only API | Jobs, schedules, estimates and invoices in Service Autopilot. | Create job, Reschedule visit, Send estimate, List invoices, Add client, Get route |
| [ZenMaid](https://cotlet.dev/integrations/zenmaid-api-mcp-server) | No official API | Appointments, cleaners and customers for your ZenMaid business. | Create appointment, Reschedule appointment, Assign cleaner, List customers, Get schedule |
| [Beautiful.ai](https://cotlet.dev/integrations/beautiful-ai-api-mcp-server) | Limited official API | Create, edit, duplicate and export Beautiful.ai decks from your agent. | List presentations, Create presentation, Update slide text, Duplicate presentation, Export to PDF |
| [Yardbook](https://cotlet.dev/integrations/yardbook-api-mcp-server) | No official API | Customers, jobs, schedules and invoices in Yardbook for landscapers. | List customers, Schedule job, Create invoice, List unpaid invoices, Add estimate |
| [Thryv](https://cotlet.dev/integrations/thryv-api-mcp-server) | Limited official API | Clients, appointments, invoices and messages in Thryv. | List appointments, Book appointment, Create invoice, Add client, Send message |
| [Kickserv](https://cotlet.dev/integrations/kickserv-api-mcp-server) | Paid API add-on | Jobs, customers, estimates and invoices in Kickserv. | Create job, List customers, Create estimate, Send invoice, Log time entry |
| [Bark](https://cotlet.dev/integrations/bark-api-mcp-server) | Limited official API | Leads, responses and credits for Bark professionals. | List new leads, Get lead details, Contact buyer, List my responses, Check credit balance |
| [BookingKoala](https://cotlet.dev/integrations/bookingkoala-api-mcp-server) | Limited official API | Bookings, providers and customers in your BookingKoala store. | List bookings, Create booking, Reschedule booking, Assign provider, List customers |

## Invoicing & freelance CRM

7 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Dubsado](https://cotlet.dev/integrations/dubsado-api-mcp-server) | No official API | Projects, proposals, contracts and invoices for creative businesses. | Create project, Send proposal, Send contract, Send invoice, Get form responses |
| [PeoplePerHour](https://cotlet.dev/integrations/peopleperhour-api-mcp-server) | No official API | Projects, proposals and messages on your PeoplePerHour account. | Search projects, Send proposal, Reply to message, List workstreams, Create offer |
| [Pixieset](https://cotlet.dev/integrations/pixieset-api-mcp-server) | No official API | Galleries, clients, invoices and bookings in your Pixieset studio. | Create gallery, Upload photos, Send invoice, List bookings, Add client |
| [SuiteDash](https://cotlet.dev/integrations/suitedash-api-mcp-server) | Limited official API | Clients, projects, invoices and tasks in your SuiteDash portal. | Create contact, Create project, Create invoice, Add task, Send portal message |
| [Tradify](https://cotlet.dev/integrations/tradify-api-mcp-server) | No official API | Jobs, quotes, invoices and schedule in Tradify. | Create job, Create quote, Send invoice, Schedule staff, List unpaid invoices |
| [Knowify](https://cotlet.dev/integrations/knowify-api-mcp-server) | Limited official API | Jobs, bids, invoices and job costing in Knowify. | Create job, Create bid, Create invoice, Log time, Get job cost report |
| [Joist](https://cotlet.dev/integrations/joist-api-mcp-server) | No official API | Estimates, invoices, clients and payments in Joist for contractors. | Create estimate, Convert estimate to invoice, List invoices, Add client, Record payment |

## Missing an app?

Search for it at [cotlet.dev/integrations](https://cotlet.dev/integrations#catalog-search) and press **Request**. No account needed. Requests from signed-up users decide what we build next.

AI agents can file a request directly: `POST https://cotlet.dev/api/v1/integration-requests` with `{"app": "Notion", "app_url": "https://notion.so", "use_case": "what the user wants done", "client": "your agent name"}`. See [for-ai-agents.md](for-ai-agents.md).

---

Product names are trademarks of their owners. Cotlet is unofficial and not affiliated with, or endorsed by, any app in this catalog.
