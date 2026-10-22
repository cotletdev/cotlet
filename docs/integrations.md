# Cotlet integrations catalog

[← Back to README](../README.md) · Live catalog: [cotlet.dev/integrations](https://cotlet.dev/integrations) · Machine-readable: [cotlet.dev/integrations.json](https://cotlet.dev/integrations.json)

Cotlet hosts an MCP server and a REST API for each of the **192 apps** below. Every one of them lacks a usable official API for the work people actually want to hand to an AI agent. The "Official API" column says what the vendor offers today:

| Label | Meaning | Apps |
|---|---|---|
| **No official API** | No public API, developer docs or keys | 30 |
| **Limited official API** | Read-only, or missing the endpoints people need | 100 |
| **Partners-only API** | Only for approved partners, after an application or contract | 38 |
| **Paid API add-on** | Only on a top plan or as a separate paid product | 24 |

Each app links to its page on cotlet.dev with sources for the official API status, every tool with its parameters and example responses, and use cases. Add `.md` to any integration URL for a Markdown version.

Over MCP each app is one tool (`skool`) and its endpoints are operations (`list_members`); over REST the same endpoint is `GET /api/v1/skool/groups/{group}/members`.

## Creators & communities

31 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Substack](https://cotlet.dev/integrations/substack-api-mcp-server) | Limited official API | Posts, Notes, messages, subscribers and stats for your publication. | Create post, Schedule post, Publish Note, Reply to Notes, Send direct message, Moderate comments |
| [Skool](https://cotlet.dev/integrations/skool-api-mcp-server) | No official API | Posts, members, courses, events and DMs for your Skool community. | List members, Approve membership request, Create post, Reply to comment, Send DM, Get members, churn and MRR |
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
| [AniList](https://cotlet.dev/integrations/anilist-api-mcp-server) | Limited official API | Your AniList anime and manga lists, ratings and activity, managed by your agent. | Update list entry, Rate anime or manga, List your anime list, Read notifications, Reply to activity, Favourite a title |
| [Discogs](https://cotlet.dev/integrations/discogs-api-mcp-server) | Limited official API | Collection, wantlist, listings and orders in your Discogs account. | Search releases, List copies for sale, Add release to collection, Add release to wantlist, Reprice listing, Update order status |
| [Flickr](https://cotlet.dev/integrations/flickr-api-mcp-server) | Limited official API | Photos, albums, tags and comments in your Flickr, worked by your agent. | List albums, Upload photo, Edit title and tags, Move photos between albums, Change privacy, Reply to comment |
| [Ghost](https://cotlet.dev/integrations/ghost-api-mcp-server) | Limited official API | Posts, members, newsletters and tiers in your Ghost site, worked by your agent. | List posts, Create draft post, Schedule post, Send newsletter, List members, Label members |
| [Lichess](https://cotlet.dev/integrations/lichess-api-mcp-server) | Limited official API | Teams, tournaments, studies, broadcasts and game exports for your Lichess account. | Accept team join request, Send team update, Create Arena tournament, Create broadcast, Import PGN to study, Export games |
| [Printful](https://cotlet.dev/integrations/printful-api-mcp-server) | Limited official API | Orders, products, mockups and shipping in your Printful account, worked by your agent. | List orders, Create draft order, Confirm order, Check shipping rates, List sync products, Upload design file |
| [Printify](https://cotlet.dev/integrations/printify-api-mcp-server) | Limited official API | Products, orders and artwork in your Printify shop, worked by your agent. | List products, Create product, Publish product, Update variant prices, List orders, Cancel order |
| [SmugMug](https://cotlet.dev/integrations/smugmug-api-mcp-server) | Limited official API | Galleries, uploads, sharing and captions in your SmugMug account. | List galleries, Create gallery, Upload photos, Change gallery privacy, Invite gallery viewers, Edit captions and keywords |
| [StreamElements](https://cotlet.dev/integrations/streamelements-api-mcp-server) | Limited official API | Chat commands, timers, store, tips and points, worked by your agent. | List chat commands, Edit command, Edit timer, Edit store item, Review tips, Adjust loyalty points |
| [Trakt](https://cotlet.dev/integrations/trakt-api-mcp-server) | Limited official API | Watchlist, ratings, history and lists in your Trakt account, worked by your agent. | Add to watchlist, Rate movies and shows, Mark episodes watched, Manage custom lists, Browse calendar |
| [Tumblr](https://cotlet.dev/integrations/tumblr-api-mcp-server) | Limited official API | Posts, queue and asks on your Tumblr blogs, worked by your agent. | Create post, Schedule post, Edit post, Reply to ask, Reblog post, List queue |
| [Vimeo](https://cotlet.dev/integrations/vimeo-api-mcp-server) | Limited official API | Captions, folders, showcases and stats for your Vimeo videos. | Search videos, Edit video details, Move videos to folder, Upload captions, Add videos to showcase, Get video analytics |

## Courses & training

11 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Udemy](https://cotlet.dev/integrations/udemy-api-mcp-server) | Limited official API | Coupons, course updates, announcements and revenue for instructors. | Create coupon, Update course, Send announcement, Get revenue report |
| [Teachable](https://cotlet.dev/integrations/teachable-api-mcp-server) | Limited official API | Course content, coupons, emails and comments on any plan. | Update lecture, Create coupon, Send email, Reply to comment, List enrollments |
| [ThriveCart](https://cotlet.dev/integrations/thrivecart-api-mcp-server) | Limited official API | Products, checkouts, refunds and affiliates for sellers. | Create product, Create checkout, Issue refund, List affiliates |
| [Payhip](https://cotlet.dev/integrations/payhip-api-mcp-server) | Limited official API | Products, sales, customers, coupons and refunds for sellers. | Create product, List sales, List customers, Create coupon, Issue refund |
| [Uscreen](https://cotlet.dev/integrations/uscreen-api-mcp-server) | Limited official API | Videos, collections, live events and analytics for creators. | Upload video, Update collection, Create live event, Get analytics |
| [Systeme.io](https://cotlet.dev/integrations/systeme-io-api-mcp-server) | Limited official API | Funnels, email campaigns and sales reports for marketers. | Update funnel page, Edit email campaign, List orders, Get sales report |
| [Teachers Pay Teachers](https://cotlet.dev/integrations/teachers-pay-teachers-api-mcp-server) | No official API | Products, prices and sales reports for TPT sellers. | List products, Create product listing, Update price, Get sales report, Answer buyer question |
| [Absorb LMS](https://cotlet.dev/integrations/absorb-lms-api-mcp-server) | Limited official API | Enrollments, approvals, overdue learners and users in Absorb LMS. | List users, List course enrollments, List overdue learners, Approve enrollment request, Enroll users in a course, Message learners |
| [iSpring Learn (iSpring LMS)](https://cotlet.dev/integrations/ispring-api-mcp-server) | Limited official API | Enroll learners, manage users and read progress in iSpring Learn. | Enroll users in courses, List enrollments, Get learner progress report, Cancel enrollment, Reset enrollment progress, Add users by email |
| [LearnUpon](https://cotlet.dev/integrations/learnupon-api-mcp-server) | Limited official API | Invite learners, manage groups and enroll them on courses in LearnUpon. | List users, Invite users, Add users to group, Enroll group on course, Enroll users on course, Unenroll users |
| [RemNote](https://cotlet.dev/integrations/remnote-api-mcp-server) | No official API | Notes and flashcards in RemNote, worked by your agent. | Search notes, Create note, Create flashcards, Edit note, Add to daily document, Check flashcard queue |

## Health & fitness

5 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Trainerize](https://cotlet.dev/integrations/trainerize-api-mcp-server) | Paid API add-on | Clients, programs, check-ins and messages for your Trainerize business. | List clients, Assign program, Message client, Log body stats, Schedule appointment |
| [Everfit](https://cotlet.dev/integrations/everfit-api-mcp-server) | Paid API add-on | Clients, programs and messages for your Everfit coaching business. | List clients, Assign program, Message client, Add autoflow, Get client metrics |
| [Fitatu](https://cotlet.dev/integrations/fitatu-api-mcp-server) | No official API | Food diary, macros and weight logging for your Fitatu account. | Get diary, Search food, Log food, Log quick entry, Copy day, Log measurement |
| [PushPress](https://cotlet.dev/integrations/pushpress-api-mcp-server) | Limited official API | Members, classes, reservations and check-ins for your PushPress gym. | List members, Book class reservation, Check in member, Cancel reservation, Update membership plan |
| [TrueCoach](https://cotlet.dev/integrations/truecoach-api-mcp-server) | Limited official API | Workouts, programs and client messages for your TrueCoach roster. | List clients, Create workout, Assign program, Read workout results, Message client |

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

14 apps.

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
| [Breezeway](https://cotlet.dev/integrations/breezeway-api-mcp-server) | Limited official API | Create, assign, comment on and approve Breezeway property tasks. | List tasks, Create task, Assign task, Add task comment, Close task, Approve task |

## Local services & SaaS

40 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Faire](https://cotlet.dev/integrations/faire-api-mcp-server) | Limited official API | Orders, inventory, reorders and messages for wholesale brands. | List orders, Update inventory, Create reorder, Reply to message |
| [Booksy](https://cotlet.dev/integrations/booksy-api-mcp-server) | Partners-only API | Bookings, clients, reviews and reports for beauty businesses. | List bookings, Create booking, Reschedule booking, Reply to review, Read reports |
| [Vagaro](https://cotlet.dev/integrations/vagaro-api-mcp-server) | Limited official API | Bookings, waitlists and client replies across locations. | List appointments, Create appointment, Reschedule appointment, Manage waitlist, Reply to client |
| [Buildertrend](https://cotlet.dev/integrations/buildertrend-api-mcp-server) | Partners-only API | Schedules, daily logs, change orders and selections for builders. | Get schedule, Create daily log, Create change order, List selections |
| [Pirate Ship](https://cotlet.dev/integrations/pirate-ship-api-mcp-server) | No official API | Labels, rates and tracking for small shippers. | Get rates, Buy labels in bulk, Import orders, Track shipment, Refund labels |
| [Fresha](https://cotlet.dev/integrations/fresha-api-mcp-server) | Partners-only API | Appointments, clients, sales and payouts for salons and spas. | List appointments, Create appointment, List clients, Get daily sales, Export data |
| [Workiz](https://cotlet.dev/integrations/workiz-api-mcp-server) | Limited official API | Jobs, scheduling, invoices and payments for field service. | List jobs, Schedule job, Create invoice, Record payment |
| [GlossGenius](https://cotlet.dev/integrations/glossgenius-api-mcp-server) | No official API | Appointments, clients and sales for salon owners. | List appointments, Book appointment, Reschedule appointment, List clients, Get sales |
| [Nextdoor](https://cotlet.dev/integrations/nextdoor-api-mcp-server) | Partners-only API | Posts, comments and recommendations for your Nextdoor business page. | Create post, Reply to comment, List recommendations, Create event, Create For Sale listing, Get page stats |
| [AccuLynx](https://cotlet.dev/integrations/acculynx-api-mcp-server) | Paid API add-on | Jobs, contacts, photos and estimates in your AccuLynx account. | Create job, Update job milestone, Add contact, Upload photo, List estimates, Add job note |
| [Thumbtack](https://cotlet.dev/integrations/thumbtack-api-mcp-server) | Partners-only API | Leads, messages, quotes and reviews for your Thumbtack pro profile. | List leads, Reply to lead, Send quote, Update weekly budget, List reviews, Export past leads |
| [Milanote](https://cotlet.dev/integrations/milanote-api-mcp-server) | No official API | Boards, notes and links in your Milanote workspace. | List boards, Add note, Add link, Upload image, Move and edit cards, Tick off tasks |
| [Setmore](https://cotlet.dev/integrations/setmore-api-mcp-server) | Paid API add-on | Bookings, customers and staff calendars in your Setmore account. | List appointments, Create appointment, Reschedule appointment, Cancel appointment, Find customer |
| [Service Fusion](https://cotlet.dev/integrations/service-fusion-api-mcp-server) | Paid API add-on | Jobs, customers, estimates and invoices in your Service Fusion account. | Create job, List customers, Create estimate, Create invoice, Update job status |
| [Mangomint](https://cotlet.dev/integrations/mangomint-api-mcp-server) | No official API | Appointments, clients and sales for your Mangomint salon or spa. | List appointments, Book appointment, Reschedule appointment, Find client, Export sales report |
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
| [BookingKoala](https://cotlet.dev/integrations/bookingkoala-api-mcp-server) | Limited official API | Bookings, providers and customers in your BookingKoala store. | List bookings, Assign provider, Reschedule booking, Cancel booking, Refund charge |
| [Jobber](https://cotlet.dev/integrations/jobber-api-mcp-server) | Partners-only API | Quotes, jobs, invoices and clients in your Jobber account. | Create quote, Convert quote to job, Create invoice, Send invoice, List unpaid invoices |
| [Housecall Pro](https://cotlet.dev/integrations/housecall-pro-api-mcp-server) | Paid API add-on | Jobs, estimates, invoices and customers in Housecall Pro. | Create job, Create estimate, Create invoice, Send invoice, List customers |
| [WooCommerce](https://cotlet.dev/integrations/woocommerce-api-mcp-server) | Limited official API | Orders, products, customers, coupons and refunds in your WooCommerce store. | List orders, Update order status, Create refund, Create coupon, Update product, Get sales report |
| [Acuity Scheduling](https://cotlet.dev/integrations/acuity-scheduling-api-mcp-server) | Limited official API | Appointments, availability and blocked time in Acuity, worked by your agent. | List appointments, Check availability, Book appointment, Reschedule appointment, Cancel appointment, Block off time |
| [Simpro](https://cotlet.dev/integrations/simpro-api-mcp-server) | Limited official API | Quotes, jobs, schedules and customers in Simpro, worked by your agent. | List jobs, Create quote, Convert quote to job, Update job status, Look up customer, Check schedule |
| [Tripleseat](https://cotlet.dev/integrations/tripleseat-api-mcp-server) | Limited official API | Leads, events and bookings in your Tripleseat venue account, worked by your agent. | List leads, Convert lead to event, Turn down lead, Check room availability, Change event status, Create follow-up task |

## Invoicing & freelance CRM

39 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Dubsado](https://cotlet.dev/integrations/dubsado-api-mcp-server) | No official API | Projects, proposals, contracts and invoices for creative businesses. | Create project, Send proposal, Send contract, Send invoice, Get form responses |
| [PeoplePerHour](https://cotlet.dev/integrations/peopleperhour-api-mcp-server) | No official API | Search open projects and read full briefs on PeoplePerHour. | Search projects, Get project brief |
| [Pixieset](https://cotlet.dev/integrations/pixieset-api-mcp-server) | No official API | Galleries, clients, invoices and bookings in your Pixieset studio. | Create gallery, Upload photos, Send invoice, List bookings, Add client |
| [SuiteDash](https://cotlet.dev/integrations/suitedash-api-mcp-server) | Limited official API | Clients, projects, invoices and tasks in your SuiteDash portal. | Create contact, Create project, Create invoice, Add task, Send portal message |
| [Tradify](https://cotlet.dev/integrations/tradify-api-mcp-server) | No official API | Jobs, quotes, invoices and schedule in Tradify. | Create job, Create quote, Send invoice, Schedule staff, List unpaid invoices |
| [Knowify](https://cotlet.dev/integrations/knowify-api-mcp-server) | Limited official API | Jobs, bids, invoices and job costing in Knowify. | Create job, Create bid, Create invoice, Log time, Get job cost report |
| [Joist](https://cotlet.dev/integrations/joist-api-mcp-server) | No official API | Estimates, invoices, clients and payments in Joist for contractors. | Create estimate, Convert estimate to invoice, List invoices, Add client, Record payment |
| [Expensify](https://cotlet.dev/integrations/expensify-api-mcp-server) | Limited official API | Expenses, receipts and reports in Expensify. | Create expense, Attach receipt, Create report, Submit report, Approve report |
| [Exact Online](https://cotlet.dev/integrations/exact-online-api-mcp-server) | Partners-only API | Sales invoices, relations and journal entries in Exact Online. | Create sales invoice, Send invoice, Create relation, Book journal entry, List outstanding items |
| [Acumatica](https://cotlet.dev/integrations/acumatica-api-mcp-server) | Limited official API | Bills, invoices and payments in Acumatica. | Create AP bill, Create AR invoice, Release invoice, List open invoices, Approve payment |
| [Fortnox](https://cotlet.dev/integrations/fortnox-api-mcp-server) | Partners-only API | Invoices, customers and vouchers in Fortnox. | Create invoice, Send invoice, Create customer, Book voucher, List unpaid invoices |
| [TaxDome](https://cotlet.dev/integrations/taxdome-api-mcp-server) | No official API | Clients, jobs, document requests and invoices in TaxDome. | Create job, Request documents, Send invoice, Message client, List overdue tasks |
| [Pennylane](https://cotlet.dev/integrations/pennylane-api-mcp-server) | Paid API add-on | Invoices, suppliers and transactions in Pennylane. | Create customer invoice, Send invoice, Upload supplier invoice, Categorise transaction, List unpaid invoices |
| [ERPNext](https://cotlet.dev/integrations/erpnext-api-mcp-server) | Limited official API | Invoices, payments, customers and stock in ERPNext. | Create sales invoice, Submit invoice, Create payment entry, List overdue invoices, Create customer |
| [Holded](https://cotlet.dev/integrations/holded-api-mcp-server) | Paid API add-on | Invoices, expenses and contacts in Holded. | Create invoice, Send invoice, Create expense, Add contact, List unpaid invoices |
| [MYOB](https://cotlet.dev/integrations/myob-api-mcp-server) | Partners-only API | Invoices, bills and payments in MYOB. | Create invoice, Send invoice, Record payment, Create bill, List overdue invoices |
| [Invoice Ninja](https://cotlet.dev/integrations/invoice-ninja-api-mcp-server) | Paid API add-on | Invoices, quotes, clients and payments in Invoice Ninja. | Create invoice, Send invoice, Create quote, Record payment, List overdue invoices |
| [Dext](https://cotlet.dev/integrations/dext-api-mcp-server) | No official API | Receipts and bills in Dext: upload, review, publish. | Upload receipt, List items to review, Edit extracted data, Publish to ledger, Export costs |
| [sevdesk](https://cotlet.dev/integrations/sevdesk-api-mcp-server) | Paid API add-on | Invoices, receipts and contacts in sevdesk. | Create invoice, Send invoice, Upload receipt, Book voucher, List open invoices |
| [Recurly](https://cotlet.dev/integrations/recurly-api-mcp-server) | Limited official API | Accounts, subscriptions and invoices in Recurly. | Find account, Change subscription, Cancel subscription, Refund invoice, List past-due accounts |
| [Lexware Office (lexoffice)](https://cotlet.dev/integrations/lexware-office-api-mcp-server) | Paid API add-on | Quotes, invoices, contacts and receipts in Lexware Office. | Create quote, Create invoice, Finalise invoice, Upload receipt, Add contact |
| [Alegra](https://cotlet.dev/integrations/alegra-api-mcp-server) | Paid API add-on | Invoices, contacts and payments in Alegra. | Create invoice, Email invoice, Record payment, Add contact, List unpaid invoices |
| [Fiken](https://cotlet.dev/integrations/fiken-api-mcp-server) | Paid API add-on | Invoices, purchases and contacts in Fiken. | Create invoice, Send invoice, Book purchase, Add contact, List unpaid invoices |
| [Fakturownia (InvoiceOcean)](https://cotlet.dev/integrations/fakturownia-api-mcp-server) | Limited official API | Invoices, clients and products in Fakturownia and InvoiceOcean. | Issue invoice, Send invoice, Mark invoice paid, Add client, List unpaid invoices |
| [Facturama](https://cotlet.dev/integrations/facturama-api-mcp-server) | Paid API add-on | CFDI invoices, credit notes and clients in Facturama. | Issue CFDI invoice, Issue credit note, Cancel invoice, Add client, Download XML/PDF |
| [e-Boekhouden](https://cotlet.dev/integrations/e-boekhouden-api-mcp-server) | Limited official API | Invoices, relations and bookings in e-Boekhouden. | Create invoice, Book mutation, Add relation, List open items, Export ledger |
| [Fatture in Cloud](https://cotlet.dev/integrations/fatture-in-cloud-api-mcp-server) | Limited official API | E-invoices, clients and expenses in Fatture in Cloud. | Create invoice, Send to SDI, Add client, Record expense, List unpaid invoices |
| [SnelStart](https://cotlet.dev/integrations/snelstart-api-mcp-server) | Partners-only API | Sales invoices, relations and bookings in SnelStart. | Create sales invoice, Add relation, Book entry, List open items, Upload document |
| [e-conomic](https://cotlet.dev/integrations/e-conomic-api-mcp-server) | Partners-only API | Invoices, customers and entries in e-conomic. | Create draft invoice, Book invoice, Add customer, List unpaid invoices, Create entry |
| [Procountor](https://cotlet.dev/integrations/procountor-api-mcp-server) | Partners-only API | Invoices, receipts and partners in Procountor. | Create invoice, Approve invoice, Create receipt, Add partner, List unpaid invoices |
| [Számlázz.hu](https://cotlet.dev/integrations/szamlazz-hu-api-mcp-server) | Paid API add-on | Invoices, receipts and NAV status in Számlázz.hu, run by your agent. | Issue invoice, Cancel invoice, Issue receipt, Record payment, Get invoice PDF |
| [iFirma](https://cotlet.dev/integrations/ifirma-api-mcp-server) | Limited official API | Invoices, costs and KSeF sending in iFirma, run by your agent. | Issue invoice, Send invoice, Send to KSeF, Add cost, List unpaid invoices |
| [Bokio](https://cotlet.dev/integrations/bokio-api-mcp-server) | Partners-only API | Invoices, receipts and journal entries in Bokio, run by your agent. | Create invoice, Send invoice, Upload receipt, Create journal entry, List unpaid invoices |
| [Odoo](https://cotlet.dev/integrations/odoo-api-mcp-server) | Paid API add-on | Invoices, payments, contacts and sales orders in your Odoo. | Create invoice, Send invoice, Register payment, List unpaid invoices, Create contact |
| [Chargebee](https://cotlet.dev/integrations/chargebee-api-mcp-server) | Limited official API | Subscriptions, invoices and credit notes in Chargebee. | Find customer, Change subscription plan, Cancel subscription, Issue credit note, List overdue invoices |
| [Accelo](https://cotlet.dev/integrations/accelo-api-mcp-server) | Limited official API | Tickets, projects, time and quotes in your Accelo, worked by your agent. | List tickets, Reply to ticket, Update ticket, Log time, Create task, Create quote |
| [Copper CRM](https://cotlet.dev/integrations/copper-crm-api-mcp-server) | Limited official API | Leads, deals, tasks and activities in your Copper CRM, for AI agents. | List opportunities, Update opportunity stage, Mark opportunity won or lost, Create task, Log activity, Convert lead |
| [Kommo](https://cotlet.dev/integrations/kommo-api-mcp-server) | Limited official API | Leads, incoming chats, tasks and pipeline stages in your Kommo CRM. | List leads, Accept incoming lead, Move lead to stage, Create task, Reply to chat, Add note |
| [Teamleader](https://cotlet.dev/integrations/teamleader-api-mcp-server) | Limited official API | Deals, quotations, invoices and reminders in Teamleader Focus, worked by your agent. | List overdue invoices, Send invoice reminder, List quotations, Send quotation, Move deal to a phase, Create task |

## Marketing & SEO

5 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Google Search Console](https://cotlet.dev/integrations/google-search-console-api-mcp-server) | Limited official API | Request indexing, removals, users and index reports for your sites. | Request indexing, Request URL removal, Add user to property, List not indexed URLs, Get links report, Get performance stats |
| [EmailOctopus](https://cotlet.dev/integrations/emailoctopus-api-mcp-server) | Limited official API | Campaigns, segments, sends and reports in your EmailOctopus, worked by your agent. | List campaigns, Get campaign report, Duplicate campaign, Create segment, Set campaign recipients, Schedule campaign |
| [Google Discover](https://cotlet.dev/integrations/google-discover-api-mcp-server) | Limited official API | Read your Discover feed, follow or hide publishers, get Discover stats. | Read Discover feed, Check domain in feed, Get story cluster, List followed publishers, Follow publisher, Hide publisher |
| [Sendible](https://cotlet.dev/integrations/sendible-api-mcp-server) | Limited official API | Posts, inbox replies, approvals and reports for your Sendible workspaces. | List workspaces, Schedule post, Queue post, Send post for approval, Approve or reject task, Reply to message |
| [Sprout Social](https://cotlet.dev/integrations/sprout-social-api-mcp-server) | Limited official API | Publishing, inbox and reports in your Sprout Social, worked by your agent. | Schedule post, Reply to message, Tag message, Assign case, Get post performance, List queued posts |

## Customer support

11 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Zendesk](https://cotlet.dev/integrations/zendesk-api-mcp-server) | Limited official API | Tickets, replies, macros and views in your Zendesk, worked by your agent. | List tickets, Reply to ticket, Update ticket, Apply macro, Add internal note, Search tickets |
| [Help Scout](https://cotlet.dev/integrations/help-scout-api-mcp-server) | Paid API add-on | Conversations, replies, tags and Docs in Help Scout, from your agent. | Reply to conversation, Add note, Tag conversation, Assign conversation, Update Docs article, Search conversations |
| [eDesk](https://cotlet.dev/integrations/edesk-api-mcp-server) | Limited official API | Tickets, replies, orders and tags in your eDesk, worked by your agent. | List tickets, Reply to ticket, Assign owner and add tags, Add internal note, Get order and tracking, List templates |
| [Gladly](https://cotlet.dev/integrations/gladly-api-mcp-server) | Limited official API | Conversations, customer profiles, topics and tasks in Gladly, worked by your agent. | List conversations, Search customers, Reply to customer, Add note, Apply topics, Assign conversation |
| [Gorgias](https://cotlet.dev/integrations/gorgias-api-mcp-server) | Limited official API | Tickets, replies, macros and rules in your Gorgias helpdesk. | Search tickets, Reply to ticket, Update ticket, Apply macro, Merge tickets, Edit macro |
| [HappyFox](https://cotlet.dev/integrations/happyfox-api-mcp-server) | Limited official API | Tickets, replies, private notes and canned actions in your HappyFox help desk. | Search tickets, Reply to ticket, Add private note, Update ticket, Apply canned action, List queues |
| [JivoChat](https://cotlet.dev/integrations/jivochat-api-mcp-server) | Limited official API | Chats, clients, quick phrases and reports in JivoChat, worked by your agent. | List chats, Reply to chat, Accept chat, List clients, Merge clients, Get aggregated report |
| [Kustomer](https://cotlet.dev/integrations/kustomer-api-mcp-server) | Limited official API | Conversations, customers and notes in your Kustomer, worked by your agent. | Search conversations, Reply to conversation, Add internal note, Tag conversation, Snooze conversation, Merge conversations |
| [LiveChat (Text)](https://cotlet.dev/integrations/livechat-api-mcp-server) | Limited official API | Chats, tags and canned replies in your LiveChat, worked by your agent. | List chats, Reply in chat, Tag chat, Transfer chat, Archive chat, Save canned response |
| [Tidio](https://cotlet.dev/integrations/tidio-api-mcp-server) | Limited official API | Tickets, chats, contacts, macros and flows in your Tidio, worked by your agent. | List tickets, Reply to ticket, Update ticket, Update contact properties, Create macro, Read conversation history |
| [Trengo](https://cotlet.dev/integrations/trengo-api-mcp-server) | Limited official API | Triage, label, reply to and close Trengo conversations with your agent. | List conversations, Search conversations, Read a conversation, Add label, Assign conversation, Reply to customer |

## HR & recruiting

7 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Personio](https://cotlet.dev/integrations/personio-api-mcp-server) | Limited official API | Time off, employees and attendance in Personio, handled by your agent. | Request time off, Approve time off, List absences, Get employee, Update employee, Log attendance |
| [Ashby](https://cotlet.dev/integrations/ashby-api-mcp-server) | Limited official API | Candidates, interviews and pipeline stages in Ashby, run by your agent. | Create candidate, Move candidate stage, Schedule interview, Reject candidate, Add note, List open jobs |
| [BambooHR](https://cotlet.dev/integrations/bamboohr-api-mcp-server) | Limited official API | Employees, time off and onboarding in BambooHR, done by your agent. | Request time off, Approve time off, Update employee, Create onboarding task, Get report, List employees |
| [CharlieHR](https://cotlet.dev/integrations/charliehr-api-mcp-server) | Limited official API | Approve leave, book time off, adjust allowances and offboard people. | List team members, List time off requests, Approve time off request, Deny time off request, Book time off, Record sick day |
| [Deputy](https://cotlet.dev/integrations/deputy-api-mcp-server) | Limited official API | Approve timesheets and leave, and roster shifts in Deputy. | List timesheets, Approve timesheet, Discard timesheet, List leave requests, Approve leave request, Decline leave request |
| [JazzHR](https://cotlet.dev/integrations/jazzhr-api-mcp-server) | Limited official API | Move candidates, email them and manage jobs in your JazzHR. | List candidates, Move candidate to a workflow stage, Bulk change candidate status, Email candidate, Add candidate note, Create task |
| [Manatal](https://cotlet.dev/integrations/manatal-api-mcp-server) | Partners-only API | Candidates, jobs, pipeline stages and notes in your Manatal, worked by your agent. | Search candidates, Create candidate, Add candidate to job, Move candidate to stage, Drop candidate with reason, Add candidate note |

## Productivity & teams

16 apps.

| App | Official API | What your agent can do | Example tools |
|---|---|---|---|
| [Redmine](https://cotlet.dev/integrations/redmine-api-mcp-server) | Limited official API | Issues, time entries and projects in your Redmine, from your agent. | Create issue, Update issue, Log time, List my issues, Add comment, List projects |
| [Zotero](https://cotlet.dev/integrations/zotero-api-mcp-server) | Limited official API | Your Zotero library: add papers, organize collections and pull notes. | Add item by DOI, Search library, Add to collection, Get annotations, Create note, Export citations |
| [Nextcloud](https://cotlet.dev/integrations/nextcloud-api-mcp-server) | Limited official API | Files, calendar, contacts and Deck boards in your Nextcloud. | Upload file, Share file, Create calendar event, Add contact, Create Deck card, Search files |
| [Otter.ai](https://cotlet.dev/integrations/otter-api-mcp-server) | Partners-only API | Meeting transcripts, highlights and sharing in Otter, by your agent. | Search transcripts, Export transcript, Share conversation, Add highlight, Upload audio, List action items |
| [Bluedot](https://cotlet.dev/integrations/bluedot-api-mcp-server) | Limited official API | Organize, template, comment on and share Bluedot meetings; read transcripts too. | List meetings, Search transcripts, Get meeting summary and transcript, Move meeting to collection, Create collection, Create notes template |
| [Connecteam](https://cotlet.dev/integrations/connecteam-api-mcp-server) | Limited official API | Approve timesheets, publish shifts, answer time off and create tasks in Connecteam. | List timesheets, Approve timesheet, Copy previous week, Publish shifts, List time off requests, Approve time off request |
| [Feedly](https://cotlet.dev/integrations/feedly-api-mcp-server) | Limited official API | Feeds, Boards, Read Later and read state in your Feedly, worked by your agent. | List feeds, List articles, Search articles, Save article to Board, Mark articles as read, Follow source |
| [Fillout](https://cotlet.dev/integrations/fillout-api-mcp-server) | Limited official API | Forms, questions, logic and submissions in your Fillout, worked by your agent. | Create form, Add question, Set form logic, Publish form, Close form, Read submissions |
| [Habitica](https://cotlet.dev/integrations/habitica-api-mcp-server) | Limited official API | Habits, dailies and to-dos in your Habitica, worked by your agent. | List tasks, Create task, Score habit or daily, Update checklist, Hatch and feed pets, Start party quest |
| [Hubstaff](https://cotlet.dev/integrations/hubstaff-api-mcp-server) | Limited official API | Timesheets, approvals, projects and tasks in your Hubstaff, worked by your agent. | List timesheets, Approve timesheet, Review manual time request, Add time entry, Create project, Create task |
| [Inoreader](https://cotlet.dev/integrations/inoreader-api-mcp-server) | Limited official API | Feeds, folders, rules and starred articles in your Inoreader, worked by your agent. | List subscriptions, Read unread articles, Star article, Mark as read, Add feed, Create rule |
| [Instapaper](https://cotlet.dev/integrations/instapaper-api-mcp-server) | Limited official API | Reading list, folders, tags and highlights, worked by your agent. | List unread articles, Save URL, Archive article, Move to folder, Read highlights, Fetch article text |
| [Jotform](https://cotlet.dev/integrations/jotform-api-mcp-server) | Limited official API | Forms, submissions, reports and notifications in your Jotform, worked by your agent. | List forms, Read submissions, Edit submission, Archive submissions, Set notification recipients, Create report |
| [Timetastic](https://cotlet.dev/integrations/timetastic-api-mcp-server) | Limited official API | Leave requests, wallchart, approvals and absence reports for Timetastic. | List wallchart absences, List pending leave requests, Approve leave request, Decline leave request, Book time off, Cancel booking |
| [tl;dv](https://cotlet.dev/integrations/tldv-api-mcp-server) | Limited official API | Meetings, transcripts, notes, clips and sharing for your tl;dv account. | List meetings, Get transcript, Create clip, Add note, Share meeting, Add meeting to folder |
| [Yousign](https://cotlet.dev/integrations/yousign-api-mcp-server) | Limited official API | Signature requests, reminders, signed PDFs and audit trails in Yousign. | List signature requests, Create request from template, Send signature request, Send reminder, Cancel signature request, Download signed documents |

## Missing an app?

Search for it at [cotlet.dev/integrations](https://cotlet.dev/integrations#catalog-search) and press **Request**. No account needed. Requests from signed-up users decide what we build next.

AI agents can file a request directly: `POST https://cotlet.dev/api/v1/integration-requests` with `{"app": "Notion", "app_url": "https://notion.so", "use_case": "what the user wants done", "client": "your agent name"}`. See [for-ai-agents.md](for-ai-agents.md).

---

Product names are trademarks of their owners. Cotlet is unofficial and not affiliated with, or endorsed by, any app in this catalog.
