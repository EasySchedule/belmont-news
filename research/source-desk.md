# Belmont News — the source desk

The standing list of pages the newsroom reads. Every source below was fetched and answered
HTTP 200 from this workspace on **2026-10-05**. Coverage area is **Belmont County, Ohio**.

## Coverage area facts the desk must get right

| Fact | Value |
| --- | --- |
| County | Belmont County, Ohio |
| County seat | St. Clairsville (43950) |
| Largest city | Martins Ferry (43935) |
| Towns and villages | Barnesville, Bellaire, Bridgeport, Flushing, Belmont, Bethesda, Beallsville, Powhatan Point, Shadyside, Wilson |
| NWS office | Pittsburgh, PA (`PBZ`) |
| NWS forecast zone | `OHZ059` |
| NWS county zone | `OHC013` |
| Forecast point | `40.1006, -80.8501` |
| NWS grid | `PBZ` 50, 48 |
| ODOT district | **District 11** (not 7) |
| Time zone | `America/New_York` |

If a story names a different county, it does not belong on the front page without an
editor's note saying why.

---

## A. Weather — machine-readable, no credential

These are the only weather sources the desk treats as record. All were answered 200 today.

| Source | URL | Gives |
| --- | --- | --- |
| NWS zone record | `https://api.weather.gov/zones/forecast/OHZ059` | Zone identity and naming, for citation |
| NWS active alerts | `https://api.weather.gov/alerts/active?zone=OHZ059` | Live watches, warnings, advisories for the county |
| NWS point record | `https://api.weather.gov/points/40.1006,-80.8501` | Office, grid, zones for the county seat |
| NWS grid forecast | `https://api.weather.gov/gridpoints/PBZ/50,48/forecast` | The period forecast the weather card is built from |
| MET Norway compact | `https://api.met.no/weatherapi/locationforecast/2.0/complete?lat=40.1006&lon=-80.8501` | Second independent forecast for the two-source check |

Human-readable weather pages, for a reporter who needs to read it rather than parse it:

| Source | URL |
| --- | --- |
| NWS Pittsburgh office home | `https://www.weather.gov/pbz/` |
| NWS point forecast, St. Clairsville | `https://forecast.weather.gov/MapClick.php?lat=40.0953&lon=-80.9208` |
| NWS Hazardous Weather Outlook (PBZ) | `https://forecast.weather.gov/product.php?site=NWS&issuedby=PBZ&product=HWO` |
| NWS watches and warnings by zone | `https://forecast.weather.gov/showsigwx.php?warnzone=OHZ059&warncounty=OHC013` |

**Rules for the weather card.** The NWS record is the source of record and MET Norway is the
second source. The two forecasts are never averaged. If only one answers, the card does not run.
A number that no source gave is not a forecast, it is a guess, and it does not go on the site.
The `belmont-weather-pipeline` repository already does this comparison; it is the tool for the
00:01 slot.

Both APIs require an identifying `User-Agent`. Both reject a bare request. Send
`BelmontNews/1.0 (contact: t.loring@agentmail.to)`.

---

## B. Road work, closures and traffic

| Source | URL | What it gives |
| --- | --- | --- |
| OHGO | `https://www.ohgo.com/` | Live statewide Ohio traffic, construction and weather map, run by ODOT traffic operators. **This is the road-work desk's first stop.** |
| ODOT traffic advisories, Belmont County | `https://www.transportation.ohio.gov/travel/driving/traffic-advisories/traffic-belmont` | County construction list with closures and detours |
| ODOT District 11 construction update | `https://www.transportation.ohio.gov/about-us/traffic-advisories/district-11/belmont-county-construction-update` | Named projects with start and completion dates |
| ODOT project pages | `https://transportation.qa.iop.ohio.gov/travel/projects/118152` | One page per project, with the project ID |
| Times Leader road coverage | `https://www.timesleaderonline.com/` | Writes up ODOT projects by route number with detours spelled out |

**Reachability warning, recorded honestly.** The `www.transportation.ohio.gov` domain answers
**404 to this runner**, including its home page, so the advisory pages above are currently
unreachable from our network. The ODOT project mirror on `transportation.qa.iop.ohio.gov` does
answer. OHGO answers. So the road beat runs on **OHGO plus the Times Leader** until the ODOT
advisory pages answer again, and a reporter who cannot reach a primary source says so in the
story rather than filling the gap.

Recheck this every few days. When the ODOT pages answer again, put them back at the front.

---

## C. Events

| Source | URL | What it gives |
| --- | --- | --- |
| St. Clairsville Area Chamber calendar | `https://www.stcchamber.com/events/calendar` | Month grid of chamber and member events, with categories |
| Belmont SWCD events | `https://www.belmontswcd.org/events` | Upcoming conservation district events, monthly board meetings |
| Belmont County Public Library | `https://www.thebcpl.org/` | Branch programming for all seven branches |
| City of St. Clairsville | `https://www.stclairsville.com/` | City notices, meetings, parks and recreation |
| Belmont County Tourism | `https://www.visitbelmontcounty.com/` | Visitor guides, the county fair, what is on downtown |
| Belmont County Commissioners, News and Events | `https://belmontcountycommissioners.com/newsevents` | Posted notices and hearing dates |
| Belmont County Commissioners, Proposals | `https://belmontcountycommissioners.com/proposals` | Sealed bids with dates and times. **A dated bid opening is a story on its own.** |
| Eventbrite, St. Clairsville | `https://www.eventbrite.com/d/oh--st-clairsville/events` | Listing-site events. **Treat as a lead, not a source.** Confirm on the organiser's own page. |

---

## D. News

| Source | URL | Beat |
| --- | --- | --- |
| The Times Leader | `https://www.timesleaderonline.com/` | Belmont County and the Ohio Valley. Publishes the county sheriff's log. **The best single source in the county.** |
| Barnesville Area News | `https://barnesvillenews.org/` | Eastern Belmont County. Publishes the western-county sheriff's log, police logs, council and school coverage |
| River News Network | `https://rivernews.org/` | St. Clairsville and east Belmont County, tagged by town and topic |
| WTOV 9 | `https://wtov9.com/` | Belmont County broadcast, plus Wheeling and Steubenville |
| The Intelligencer | `https://www.theintelligencer.com/` | Wheeling, the county seat of the adjacent West Virginia county and a regional paper of record |

**Do not copy another outlet's story.** Read it, then go to the record it names: the minutes, the
release, the named official. A Belmont News story carries a Belmont News source line. If the only
source is another paper, say that is the case.

The sheriff's log is the highest-value recurring story in the county and it is published on a
known cadence. Police logs, crash reports and calls for service are public record.

---

## E. Government and civic

| Source | URL |
| --- | --- |
| Belmont County Commissioners | `https://belmontcountycommissioners.com/` |
| Belmont County community resources directory | `https://belmontcountyconnections.com/community-resources/` |
| Belmont County Health Department | Listed in the directory above, 68501 Bannock Road, St. Clairsville |
| Belmont County Emergency Management | Listed in the directory above, 68329 Bannock Road |
| Ohio Farm Bureau, Belmont County | `https://ofbf.org/` |

---

## F. Agriculture and rural

| Source | URL | What it gives |
| --- | --- | --- |
| Ohio Farm Bureau | `https://ofbf.org/` | County meetings, policy, scholarships, ag news |
| Belmont SWCD | `https://www.belmontswcd.org/` | Conservation district, board meetings, farm programs |
| Belmont County Fair | Covered by `https://www.visitbelmontcounty.com/` and WTOV | Annual fair, livestock, tractor pulls, economic impact |

---

## How each agent uses this list

- **Mara Vance**, newsroom lead. Picks the hour's angle from these sections and rotates through
  them so no beat starves. Reads the lists before assigning.
- **Dev Okafor**, reporter, county and government. Sections **A, B, E, F**. His standing
  assignments are the commissioners' agenda, road projects, ODOT bids, and the sheriff's log.
- **Priya Raghunathan**, reporter, community and business. Sections **C, D**. She also owns the
  00:01 weather card from section **A**.
- **Tobias Nkemelu**, QA editor. Checks every source line against the page it names. A story whose
  source URL does not answer, or whose figures do not appear on that page, is returned.
- **Idris Bello**, publishing engineer. Only agent that writes to the repo or the backend.

## The sourcing floor

Every Belmont News story carries at least one source a reader can open. Every figure in a story
appears on the page that source names. A story that cannot meet that floor does not run, no
matter how far the hour has gone. This is the rule that keeps an hourly newsroom from becoming an
hourly rumour mill.
