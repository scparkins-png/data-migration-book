# Appendix A — The Terminology Translator

*Speaking business, system and process — so nothing gets lost in the move*

## Why this appendix exists

Almost every hard problem in a migration is a **mapping** problem, and mapping breaks down when the same thing has three different names.

The person on the shop floor calls it a *"job"*. The old system's screen labels it a *Works Order*. The new ERP stores it as a *Manufacturing Order* in a table called MFGORDER. The consultant writing the plan calls it *"production demand."* All four are the same object — but if the person doing the field mapping in Step 5 does not know that, you get duplicated records, broken links between tables, or data quietly dropped on the floor.

This appendix is a **three-language dictionary**. For each business area it lines up:

| Column | What it holds |
|:-|:-|
| **What the business says** | The everyday, departmental or shop-floor term your team actually uses out loud. |
| **What the system calls it** | The label you will typically meet on a screen, in an export header, or in an ERP/CRM/accounting field. |
| **What it actually is** | The plain-English process or data meaning — the thing all the names are pointing at. |

It is not a glossary of every term in the book. It is a *translation layer* for the specific moment terminology bites hardest: when you are matching a source field to a target field and someone in the room insists they are two different things.

**How to use it.** Keep it open beside you from planning to go-live — above all during **Step 1** (the Business Process List), **Step 4** (reviewing the target's fields) and **Step 5** (mapping). When a source column header and a target field name do not obviously match, check whether they are the same object wearing two names before you decide they are two different things. Most "extra" fields are not extra — they are duplicates in disguise.

**A note on scope.** Terminology varies by industry, by software vendor and even by company. The tables below cover the terms most migrations meet across sales, purchasing, manufacturing, logistics, finance, eCommerce and CRM. Treat them as a starting map, not gospel — always confirm the meaning with the process owner you identified in Step 1.

## The one rule to remember

**Same object, three names.** Before you create a new target field for something that "isn't in the new system", prove it is genuinely new — not the same object your source called by a different name.

The clearest real example comes from one of my own mapping projects. A single source system held a customer file whose everyday fields translated into the target like this:

| Source field (what the business exported) | Target field (what the new system wanted) | What it actually is |
|:-|:-|:-|
| FULLNAME ("Kimberly Smith") | *split into* First Name + Last Name | One field in the source, two in the target |
| POSTCODE | Mailing Postal Code | Same object, different label |
| TEL | Phone | Same object, different label |
| OPTEDIN ("Yes") | Email Opt Out ("False") | Same fact, **inverted logic** |

Notice the last row. OPTEDIN = Yes and Email Opt Out = False mean the identical thing, but a careless mapping flips every marketing consent in your database. That is what this appendix is here to catch.

## 1. Sales & Order Management

Sales language is the loosest in the business — "the order", "the deal", "the account" all get used for several different objects in the same sentence.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "The order", "the sale" | Sales Order (**SO**) | A confirmed customer commitment to buy — demand on the business |
| "Quote", "estimate", "pro forma" | Quotation / Sales Quote | A priced offer that is **not yet** a commitment |
| "The account", "the customer" | Customer / Account / Sold-To party | The organisation or person you sell to (a master record) |
| "Where it ships to" | Ship-To / Delivery Address | A destination, often one of many under one customer |
| "Where the invoice goes" | Bill-To / Invoice Address | A billing destination, often different from Ship-To |
| "The rep", "account manager" | Salesperson / Owner / Account Owner | The person responsible for the relationship |
| "Line", "line item" | Order Line / SO Line | One product-and-quantity row within an order |
| "Despatch note", "the paperwork" | Delivery Note / Despatch Advice | Proof of what physically left the building |
| "The bill", "the invoice" | Sales Invoice / AR Invoice | The demand for payment (feeds Accounts Receivable) |
| "Trade price", "their price" | Price List / Customer-specific Pricing | Rules that decide the number on the line |

**Migration watch-out.** One customer often owns **many** addresses (a head office Bill-To, several branch Ship-Tos). Flat spreadsheets tend to store one address per customer row, so the same customer appears many times. In the new system these must collapse to **one** customer master with multiple linked addresses — a classic "one version of the truth" job (Step 3). *Illustrative scenario.*

## 2. Purchasing & Procurement

The mirror image of sales — and the source of the most confusing single word in any migration: **"Order."**

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "The order" (buying side) | Purchase Order (**PO**) | A commitment to *buy* from a supplier |
| "The supplier", "the vendor" | Supplier / Vendor / Buy-From party | The organisation you purchase from (a master record) |
| "Requisition", "purchase request" | Purchase Requisition (**PR**) | An internal *request* to buy, before it becomes a PO |
| "Booking it in", "receiving" | Goods Receipt / **GRN** (Goods Received Note) | The record that goods physically arrived |
| "Supplier's bill" | Purchase Invoice / AP Invoice | The supplier's demand for payment (feeds Accounts Payable) |
| "Their catalogue price" | Supplier Price List / Cost Price | The number that lands on the PO line |
| "Lead time" | Lead Time / Planned Delivery Time | How long between ordering and receiving |

**"Order" is a false friend.** In a sales export it means Sales Order; in a purchasing export it means Purchase Order; on the shop floor it can mean a Works Order. Always confirm *which* order a column called "Order No." actually holds before you map it — three different objects, three different tables. *Illustrative scenario.*

## 3. Manufacturing & Production

The area where the everyday word and the system word diverge most — and where the Sage 50 → X3 case study shows the cost of assuming the source already holds what the target needs.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "Recipe", "spec", "the parts list" | Bill of Materials (**BOM**) | The structured list of components that make up a finished item |
| "The method", "the steps", "how it's made" | Routing / Operations | The ordered sequence of production steps |
| "The line", "the machine", "the cell" | Work Centre / Resource | Where an operation is carried out |
| "The job", "the works order" | Works Order / Manufacturing Order / Production Order | An instruction to make a quantity of something |
| "Part", "item", "product", "SKU" | Item / Material / Product Master | The master record for a thing you make, buy or sell |
| "Half-made stock", "WIP" | Work In Progress (WIP) | Value/quantity of items part-way through production |
| "Cost of making it" | Standard Cost / Product Costing | The costed value of the BOM plus routing |
| "The quality cert" | Certificate of Analysis (**CoA**) | A quality document proving a batch meets spec |

**Migration watch-out (real).** In the Sage 50 → Sage X3 migration, the target system *demanded data the source had never tracked*: there were no warehouse locations and **no BOMs at all** in Sage 50, yet X3 required them — and X3 recognised **four different types** of BOM plus separate work centres and operations. Much of the data the target required did not exist anywhere and had to be created from scratch. Manufacturing targets are almost always richer than their sources; budget for *creating* structure, not just moving it.

**CoA is itself a false friend.** In manufacturing quality it means *Certificate of Analysis*; in finance it means *Chart of Accounts* (see Section 5). Same three letters, entirely different data. This is exactly the kind of clash this appendix exists to surface.

## 4. Inventory, Warehousing & Logistics

Where "stock" and "location" hide a surprising amount of structure.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "Stock", "what we've got" | Inventory / Stock On Hand | Quantity of an item currently held |
| "The shelf", "the bay", "where it lives" | Bin / Location / Storage Location | A specific place stock sits within a site |
| "The warehouse", "the site" | Site / Warehouse / Plant | A physical location that holds stock |
| "Batch", "lot" | Batch / Lot Number | A traceable group of stock made or received together |
| "Serial number" | Serial Number | A unique ID for a single tracked unit |
| "Stock take", "counting the shelves" | Stocktake / Cycle Count / Physical Inventory | Reconciling recorded stock against actual |
| "Moving stock about" | Stock Transfer / Inventory Movement | A recorded change of location or status |
| "The courier note", "tracking" | Shipment / Consignment / Carrier Tracking | The outbound delivery record |
| "Reorder level" | Reorder Point / Min-Max / Safety Stock | The trigger to buy or make more |

**Migration watch-out (real).** In the same case study, "stock not matching the warehouse" and *random text where product codes should be* were live data-quality problems, and the source held **no recorded warehouse locations** for a target that needed them. If your source tracks stock as a single number with no location, expect to *invent* the location structure the new system assumes already exists.

## 5. Finance & Accounting

The area with the tightest, most standardised vocabulary — which is a blessing, because the terms are precise, and a trap, because the everyday words ("account", "book", "posting") mean something very specific here.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "The accounts list", "the codes" | Chart of Accounts (**CoA**) / Nominal Ledger | The master list of accounts every transaction is booked to |
| "Account code", "nominal code" | GL Account / Nominal Code | A single line in the Chart of Accounts |
| "The books", "the ledgers" | General Ledger (GL) | The complete record of financial transactions |
| "Money owed **to** us" | Accounts Receivable (**AR**) / Sales Ledger / Debtors | Customer balances outstanding |
| "Money **we** owe" | Accounts Payable (**AP**) / Purchase Ledger / Creditors | Supplier balances outstanding |
| "Goods in, no bill yet" | **GRNI** (Goods Received Not Invoiced) | An accrual for stock received before the supplier's invoice arrives |
| "The VAT codes" | Tax Codes / VAT Rates | Rules that determine tax on a transaction |
| "Cost centre", "department code" | Cost Centre / Dimension / Analysis Code | A tag that slices transactions for reporting |
| "Opening balances" | Opening Balances / Trial Balance Brought Forward | The starting financial position on go-live |
| "The journal", "an adjustment" | Journal Entry / GL Posting | A manual accounting transaction |

**Migration watch-out.** Financial data is usually the **last** thing loaded (it depends on customers, suppliers, stock and orders already being in place) and the **least forgiving** — the numbers must reconcile to the penny. GRNI in particular is a *balance*, not a document: it only makes sense once both the goods receipt and the eventual invoice line up, so migrating open GRNI mid-cycle needs care. Agree with your accountant whether you migrate **open transactions** or **opening balances only**. *Illustrative scenario.*

**"Account" is a false friend.** In sales/CRM it means the *customer*; in finance it means a *line in the Chart of Accounts*. A column called "Account No." could be either. Confirm before mapping.

## 6. eCommerce

Web-shop language borrows from retail and adds its own — and often overlaps awkwardly with the ERP terms above when the two systems integrate.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "Product", "listing", "the SKU" | Product / Variant / **SKU** | A sellable item (a *variant* is one size/colour of a product) |
| "Product code" | SKU (Stock Keeping Unit) | The unique code identifying a sellable variant |
| "The basket", "the cart" | Cart / Basket | Items selected but **not yet** purchased |
| "The web order" | Order / Checkout | A confirmed online purchase (becomes a Sales Order in the ERP) |
| "Customer account", "the login" | Customer / Shopper Account | The web-side customer record (must reconcile with the ERP customer) |
| "Categories", "the menu" | Category / Collection / Taxonomy | How products are grouped for browsing |
| "Photos", "the images" | Media / Assets | Product images and files (easy to forget in a migration) |
| "Stock on the site" | Available-to-Promise / Inventory Sync | The quantity the web shows as buyable |
| "Refunds", "returns" | Refund / RMA (Return Merchandise Authorisation) | A reversal of a sale |

**Migration watch-out.** The web **SKU** and the ERP **item code** are frequently *not the same code*, even though they name the same product — so the two must be mapped to each other, not assumed identical. Product images and category structures are also data, and are the most commonly forgotten records in an eCommerce move. *Illustrative scenario.*

## 7. Marketing & CRM

Relationship language is fluid, and the same word ("lead", "contact", "campaign") can be a record type in one system and a status in another.

| What the business says | What the system calls it | What it actually is |
|:-|:-|:-|
| "A lead", "an enquiry" | Lead | An unqualified potential customer |
| "A prospect", "a live one" | Opportunity / Deal | A qualified sales possibility with a value and stage |
| "A contact", "a person" | Contact | An individual person record |
| "The company", "the account" | Account / Company / Organisation | The organisation a contact belongs to |
| "The pipeline" | Pipeline / Sales Stages | The ordered stages a deal moves through |
| "A campaign", "a mailshot" | Campaign | A grouped marketing activity |
| "Unsubscribed", "opted out" | Email Opt Out / Consent / Subscription Status | Whether you may legally market to them |
| "Tags", "labels" | Tags / Segments / Lists | Ways of grouping contacts for targeting |
| "Activity", "notes", "the history" | Activity / Interaction / Task | Logged touchpoints with a contact |

**Migration watch-out (real).** Consent is where terminology errors become **legal** errors — remember the OPTEDIN / Email Opt Out example at the start of this appendix. Map a consent field carelessly and you can opt your entire database back in, breaching GDPR. Always confirm the *direction* of a consent field, not just its presence.

## The false-friends quick list

The handful of words that cause the most trouble because they mean different things in different departments. When you meet one of these in a column header, stop and ask *"which one?"* before mapping.

| The word | Could mean… | …or mean… |
|:-|:-|:-|
| **Order** | Sales Order (selling) | Purchase Order (buying) *or* Works Order (making) |
| **Account** | Customer (sales/CRM) | GL/nominal account (finance) |
| **CoA** | Chart of Accounts (finance) | Certificate of Analysis (manufacturing quality) |
| **Book / posting** | A ledger, or posting a transaction (finance) | Booking stock in (warehouse) |
| **Item / part / product / SKU** | The same master record — under four different departmental names | — |
| **Invoice** | Sales Invoice (money in) | Purchase Invoice (money out) |
| **Ship-to vs Bill-to** | Where goods go | Where the bill goes — routinely different addresses |

## Your Turn

### Exercise A.1 — Build Your Own Translator

Your business's words will not be exactly these, so build your own three-language translator. Start it in Step 1 and have it complete before you map in Step 5.

1. Take your **Business Process List** from Step 1 (checklist item 1C).
2. For each process, write down the word your **team** uses, the label the **source system** shows, and the field name the **target system** expects.
3. Mark whether they are the **same object**, and flag every row where the three names do not obviously match — those are your highest-risk mappings.

{{worksheet: A.1 | Terminology Translator}}

Pin the finished sheet up where the mapping happens. It will save more arguments than any other single page in this book.

## Conventions

The three-column definitions describe terminology as it is *commonly* used across ERP, CRM, accounting and eCommerce systems. They are a general guide, not a specification for any one product. Watch-outs marked *(real)* come from the Sage 50 → Sage X3 case study or my own projects (see *About the Sources*); all others are labelled *illustrative scenario*.
