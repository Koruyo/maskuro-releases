What changes from version to version – described from the application's point of view, not its internals. Anyone who wants to know what it is *built from* will find that in
[LIZENZEN.md](LIZENZEN.md); this is about what changes for working with it.

The numbering follows the usual scheme: the **first** number changes
when something no longer works the way it used to, the **second** for new
capabilities, the **third** for bug fixes.

## 0.10.52-alpha.20260903 – September 3, 2026

- A batch of more than four files no longer stalls after the user has
  responded in several preview windows. Additional documents continue to be
  prepared in the background; after a response, the corresponding file now
  reliably finishes processing and the next slot in the batch is released.
- Matching short company marks in PDFs is now limited to recognized text in
  images. As a result, in ordinary page text, a long multi-line model match no
  longer causes an identical single word elsewhere to be redacted as well.

## 0.10.51-alpha.20260903 – September 3, 2026

- The changelog now appears in the user's own language – at
  maskuro.com/neuigkeiten and in the program under “Changes”, as well as in
  “What's new” after an update. Previously, all eighteen language versions
  showed German text there beneath a translated heading. Where a translation
  is still missing, that release remains in German instead of disappearing;
  the list of releases is the same everywhere.

## 0.10.50-alpha.20260903 – September 3, 2026

- Recurring company marks in PDFs are now cleaned consistently, even
  when text recognition reads the lettering differently on different pages or
  omits the round emblem entirely. An explicit deselection in the preview
  remains binding and cannot be undone by any later re-pass.
- Currency-less prices in scanned tables are now fully redacted even
  when the table header and values sit in different, overlapping
  PDF images. Quantities, hours, weights, and percentages are left alone;
  widely separated numbers are no longer accidentally joined into one
  amount.
- Signature detection now also picks up faint blue script under strain and
  narrow red signature initials. Dotted charts, measurement curves, stamps,
  logos, and wide red revision markings remain excluded from this tight
  follow-up pass.
- Redactions in rotated, mirrored, sheared, or cropped PDF images now hit the
  actual image polygon. Technical roles in line items, vehicle and tire
  specifications, and technical "compensation" are at the same time more
  tightly separated from false hits; explicitly labeled contact roles and
  phone numbers remain protected.
- The visual check before saving a PDF no longer freezes the window: on large
  documents with many findings it previously stood unresponsive for several
  seconds; now a notice shows that checking is in progress, and the window
  keeps redrawing.
- Retrieving a value from an image in the touch-up editor now reads each
  original image with text recognition only once; before, it ran again for
  the same images on every further undo.
- Loading the high tier and the signature model now needs far less memory:
  the 596 MB package used to be held, verified, and unpacked entirely in
  memory — over a gigabyte of peak use in the running program, on machines
  with 8 GB the moment everything began to stall. It now flows to disk in
  blocks and is verified and unpacked there.
- The search in the touch-up editor no longer freezes large PDFs: the first
  letter typed into the search field previously read in all pages at once —
  at 200 pages the window stood still for two seconds, and again after every
  redaction. Pages are now read in chunks; until then "Reading…" shows in the
  counter, and the result is the same.
- Rasterized PDF pages — after text recognition or when text could not be
  cleanly removed — are now saved noticeably smaller and without image loss:
  instead of always being JPEG, each page is also encoded losslessly, and the
  smaller version goes into the file. A cleaned scan thus shrinks from 248 to
  48 KB, the sample document with text recognition from 913 to 702 KB; text
  stays razor-sharp.
- Reloadable models (high tier, signatures, faces, second text recognition)
  are now released from memory again after ten minutes without a cleaning
  run. Before, they stayed loaded until the program ended — anyone who had
  used signature detection and the high tier even once permanently held over
  two gigabytes. The next run reloads them in one to two seconds; the status
  line announces it.
- PowerPoint: the generic names of slide layouts and slide masters ("Blank",
  "Title Slide") are no longer replaced as a finding. "Blank" is also a place
  name and was wrongly redacted in every German and English presentation;
  only manually assigned slide names are now cleaned.
- In PDFs, line smoothing no longer pulls the start of the next line into a
  finding: the number of the next list item after a date was counted as a
  phone number, a field header like "Code" or "Order Number" after a number as
  a postal code with city, and the city line under the address duplicated the
  city. The correct, shorter finding was displaced as a result. Across 132
  corpus PDFs, of 24 additional smoothing findings only the two real ones
  remain; in the practice corpus, false positives drop from 29 to 21 at the
  same hit rate.
- "Search and redact a folder of PDFs" in the touch-up editor no longer
  blocks the window: the run works in the background, progress and the
  cancel button respond, and menus or tabs can no longer be operated in the
  middle of a half-finished file.
- Scanned pages with findings are now rewritten only once instead of twice
  when redacting: before, the program filled the finding boxes and the
  reasoning boxes in two passes, and the second pass recompressed the
  just-newly-saved scan image a second time. This saves time on large scans
  and a loss of image quality.
- Paging, zooming, and thumbnails in the touch-up editor respond faster:
  every rendered page previously went through a PNG compression and straight
  back out again, only to be displayed — on high-resolution screens roughly a
  tenth of a second per page. The image now arrives directly, pixel for
  pixel the same.
- The visual check before saving a PDF ("output sample") is roughly three
  times faster, with the same result.
- The main window is ready about another quarter second sooner: checking
  whether text recognition is ready on this machine ran during window
  construction — on the Mac including a test request to the system
  recognizer — and the add-ons settings page queried the status of all 48
  languages for it. Both now happen in the background, or only when the
  language list is actually opened; until then "Checking text recognition…"
  shows.
- After a signature search, the program uses roughly 300 MB less memory: the
  detection model used to sit in memory twice — once to verify its
  authenticity, once to compute. It is still verified, just without the
  second copy.
- Text recognition in PDFs has become noticeably faster: for every field
  header on a page ("Date of Birth:", "Tax Number:"), a separate probe used
  to be sent through recognition for each finding type — on every page anew,
  even when the same header had already appeared ten pages earlier. The
  answer is now remembered; a two-page schedule of services thus asked 324
  questions before, now only the distinct ones. The findings are the same.
- Large tables are again cleaned in seconds instead of minutes: in
  anonymizing mode — the default — matching against already-known values got
  slower with every further cell, because a cache was discarded and rebuilt
  on every hit. 5,000 cells took roughly 18 seconds for this before, now half
  a second; the result is character-for-character the same.
- The main window appears noticeably faster again: the country list in
  settings pulled the entire recognition library to the foreground during
  window construction — roughly 0.7 seconds on the Mac, correspondingly more
  on Windows — even though only the country names are needed for it. The
  list now comes from a lightweight catalog; the library loads in the
  background as intended, while the window already stands. This also applies
  after every language or appearance change that restarts the program.
- The document lab now runs cropped field headers, local value shadows, and
  heavy scan crops fully through PDF, DOCX, and ODT containers. The matrix
  comprises 680 files from 40 document families and 17 container axes.
  Maskuro removes all target values in both the new and the full base and
  feature profiles, without a measured false positive, damaged retention
  value, or abort.

- Reused scans are now checked and cleaned across every visible placement:
  the document lab shares the same image object across different pages,
  sizes, and rotations in PDF, and references the same image part multiple
  times in DOCX and ODT. Technical ODT frame names like "form scan small
  landscape" no longer count as a person; free-form names and places with a
  similar start remain protected. A generic form guess by the final PDF page
  pass can no longer produce a large address false positive on an image area
  already read independently. The 120 new containers achieve all 813 and 840
  target values respectively in the base and feature profile without false
  positive, retention violation, or abort; the full 800-file feature
  acceptance run confirms 5,600/5,600.

- The German OCR lab now comprises 560 scans from 40 document families. New
  variants crop field header and page margins or place a shadow directly
  over a value. Maskuro also protects names, addresses, dates of birth,
  medical codes, and labeled ID numbers with partially damaged labeling.
  At the same time, form field remnants, official headings, and factual
  legal and informational terms are no longer replaced as persons or
  places. The full base and feature profiles achieve 3,794/3,794 and
  3,920/3,920 target values respectively without a measured false positive
  or abort.

- The automatic PDF image selection no longer removes large product photos,
  energy labels, and portrait rows solely because they begin at the top page
  margin. Genuine flat header/footer images and letterhead images starting
  at the sheet edge still fall. In staff directories, names are now also
  recognized from structurally repeated entries when the visible document
  title exists only as an image. Detection is no longer tied to two specific
  role words and the abbreviation "ext."; one to four wrapped roles as well
  as "extension", "direct dial", "ext.", and "Durchwahl" are inferred from
  the shared layout. Roles and section headers are left alone even when the
  language model, after overlap resolution, leaves only a role adjective
  behind. Horizontal role grids are no longer mistaken for name columns. If
  the page OCR merges several cards into one extremely wide run of capitalized
  text, a tight local counter-check separates the actual word boxes; this
  leaves neither a single name nor a wide false-positive bar behind. Repeated
  multi-line company logos are now redacted based on an already-confirmed
  identical pixel template even on pages without usable OCR text and with up
  to two pixels of position deviation; shorter local second readings of the
  OCR must at the same time no longer append a larger header area as a
  fabricated name. Page numbers before a company letterhead
  no longer belong to the organization name, and numerically-starting genuine
  brand names remain protected. Several measured product, technical, and form
  words are no longer suggested as persons.

- Signature detection in PDFs now runs after OCR image cleaning, also
  visits pages without an ordinary text hit, and correctly maps finding
  boxes on rotated pages back into document space. Dense product photos
  are no longer redacted as a signature. Over explicitly labeled signature
  fields, a tight line fallback closes thin model gaps; empty lines with a
  preprinted date do not trigger it. Pure scans with only OCR/signature
  findings no longer abort at this stage because of an image redactor that
  used to be loaded only in the text branch.

- Many simultaneously open documents remain distinguishable in the touch-up
  editor: the tabs no longer shrink down to a bare ellipsis, and a list
  button on the right shows all full file names stacked below one another.
  Tabs can be reordered by dragging and removed with their close button from
  the same list as in the main window; unsaved work is still cleared up
  first. A right-click also offers "Close", "Close Other Tabs", and "Close
  Tabs to the Right".

- A brief Windows lock by antivirus scanners or the search indexer no
  longer causes the fully loaded language model or dictionary folder to
  fail with "Access Denied" during the final move into place. Maskuro now
  retries this final folder move for a short time.

- The German document lab now also checks containers with varying PDF page
  rotation, independently rotated PDF images, and scaled and cropped table
  images in DOCX and ODT. Field values in visibly rotated images are again
  fully recognized, technical column labels are no longer replaced as
  places, and names sharing a family name are no longer split into
  duplicate partial hits by the consistency follow-up pass. The matrix,
  doubled to 320 files, achieves 2,240/2,240 target values with date,
  money, and medical detection enabled, without a measured false positive
  or abort.

- Multi-page image PDFs, mixed text/image PDFs, and scans embedded in DOCX
  or ODT are now checked in a dedicated 160-file lab across all 40 German
  document families. Technical ODT frame names and labeled device codes are
  no longer replaced as places; genuine names, places, and addresses in the
  same structures remain protected. With medical or money detection
  enabled, a directly following dosage or payment interval respectively is
  also fully removed. Container, text-base, text-feature, and OCR-feature
  runs together achieve their respective full totals without a measured
  false positive or abort.

- The security check before saving now shows conspicuous PDF spots as an
  individually selectable list. "Check in editor" opens exactly the chosen
  page and highlights the area; overlapping partial hits at the same spot
  now appear only once. The new interface texts are fully present in all 17
  translated interface languages.

- Markdown files keep their link, emphasis, and footnote syntax when
  replacing. Maskuro reads a character-length-identical version without
  Markdown markup for this; underscores in email addresses, arithmetic
  asterisks, and ordinary links without a personal detail remain unchanged.

- Multiple handwritten entries on the same PDF page are now searched for in
  up to three passes. Strokes already found are only hidden in the working
  image, so they no longer crowd out weaker signatures; on rotated pages the
  redaction areas again land on the visible finding spot. Image fills from
  earlier security phases are preserved when writing back afterward.

- "Reset all settings" now also covers "Text in images". If the OCR
  component is unavailable, the toggle stays technically off without being
  incorrectly marked as deviating from the shipped defaults.

- Large image fragments at the top page margin are no longer considered a
  header solely because of their position. This especially preserves
  image-based product descriptions and table contents. Newly recognized,
  type-exact email and form findings are also no longer filtered out of the
  final visual check on an already-checked image area.

- Technical line-item and article rows in HVAC and electrical quotes are now
  more tightly distinguished from persons, places, and organizations. This
  affects, among other things, cable types, AC supply, item numbers, and
  uppercase product codes; genuine names and addresses remain protected.

- Checking real cleaned PDFs no longer confuses price components like
  `1,699.59` with phone numbers and no longer cuts a supposed card number out
  of a complete date like `05/08/2025`. Names after a salutation now end at
  the line break instead of running into the following street; place names in
  attachment filenames are limited to the actual place. Vehicle colors,
  technical status values, trade designations, and product legal forms are
  also preserved. Damaged placeholder readings like `|PLLZ` are no longer
  treated as a personal detail on a second OCR pass.

- Sideways-stored PDF images now get an additional look at their unaltered
  image orientation during the final visual check. This may only re-redact
  values that Maskuro has already reliably recognized elsewhere on the same
  page. This fully covers, for example, a small rotated address stamp,
  without inventing new words from image captions or technical drawings as
  personal details.

- In OpenDocument text documents, a comment's author initials are now
  cleared together with the author. LibreOffice stores them next to the
  full name as a separate short form and displays exactly that in the
  margin; previously "SO" remained there while "Sieglinde Ortner" next to
  it had long been a placeholder. Clearing only happens when the author was
  actually replaced — a department's comment keeps its label.

- In Italian business letters, standard opening phrases no longer count as a
  name or place: "Restiamo a disposizione", "Rimaniamo", "Attendiamo",
  "Alleghiamo", "Comunichiamo", and "Auguriamo buon lavoro" used to get stuck
  as a supposed person or place. Genuine names in the same spot ("Rossi
  Mario") are still recognized.

- Two-column scans now protect labeled IDs and place names even when text
  recognition delivers all field headers first and all values afterward.
  The mapping follows the visible pixel row and also works on pages rotated
  by 90 degrees. Tightly separated parts of a passport or contract ID are
  redacted together; labeled dates of birth, ICD, and PZN codes are also
  covered, subsequent technical words are left alone. Short names and
  usernames are protected at exact fields; email addresses split across
  several OCR words only with close proximity and complete email grammar. A
  field-bound correction of confusable characters and local re-reading of a
  still-empty person field cover damaged and rotated scans, without
  expanding technical fields or already-filled values. Safety margins follow
  word size, and the feature profile picks up immediately adjacent dosage
  units and payment intervals. Slightly skewed scanned forms are
  geometrically reprojected from several same-direction OCR lines; rounding
  noise or contradictory witnesses are not enough. Short letter prefixes
  remain in front of a hyphenated code, and a complete labeled address
  finding only replaces its similar partial street finding. A misread role
  field header only falls in a form column occupied by at least three known
  headers; chat names remain protected. A narrow edge crop and a local
  overexposure with a diagonal light reflection round out the image matrix.
  Person, place, and company findings spanning several form lines are now
  limited to the respective value in a multiply-occupied field column. A
  technical position value only falls with a position header and matching ID
  form; genuine names remain protected. Even email values cut off by a light
  reflection are removed behind an explicit email field header with a tight,
  neighbor-limited image margin. Two field-value pairs on the same visible
  line are now evaluated independently; values on a lower baseline are only
  linked after three matching geometric witnesses. As a result, ID numbers,
  dates of birth, and addresses remain fully protected even in dense form
  layouts. Street, postal code, and city are only merged within the same
  address field and with matching postal grammar. Narrowly scoped technical
  fields for aids/tools and dental status no longer produce place or
  directory false positives; genuine names and similarly named fields remain
  protected. The German document lab now comprises 440 scans and achieves
  2,981/2,981 in the base profile and 3,080/3,080 in the feature profile.
  All eleven image mutations and all 40 document families stand at 100
  percent,
  still without a measured false positive, retention violation, or abort.

- PDF text layers with lost cell separators now limit organization,
  address, and place findings based on the repeated field-value structure.
  Field headers before company values and technical arrows like `=>` or
  `->` no longer belong to the finding. The additional view for soft line
  breaks may no longer extend legal-form and place findings across several
  table rows; an already complete address ends before the next field header
  with its value. The final run across all 1,600 TXT, HTML, PDF, and DOCX
  documents removes 10,840/10,840 target values with zero false positives,
  zero retention violations, and zero aborts.
