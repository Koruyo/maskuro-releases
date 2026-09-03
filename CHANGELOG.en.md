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

## 0.10.44-beta.1 – September 1, 2026

- Package builds now produce separate outputs for Windows x64 and ARM64,
  macOS on Apple Silicon and Intel, and Linux x64 and ARM64. Package names,
  update selection, and releases distinguish the architecture; a
  release stays blocked as long as one of the six targets or its
  dependency evidence is missing. Linux ARM64 requires at least glibc
  2.39 because of Qt. Fully accepted on real hardware for now are only
  Windows x64 and macOS on Apple Silicon; the remaining architecture packages
  are clearly marked as pre-release builds for testing rather than
  production use.

- With multiple files, detection now keeps working while a
  preview waits to be reviewed. Up to three prepared previews are shown
  one after another; at the same time, only one document is still
  being computed, and a result file is only created after its release.
  A standing exception chosen in the preview also applies to already
  prepared subsequent documents.

- Redaction certificates can now be checked at any time directly from the File menu
  against the redacted document. Maskuro distinguishes between a matching
  signed file, a matching but unsigned record, an invalid
  signature, and a document that does not belong to the certificate. A license
  or the original operating system account is not required for the
  cross-check.
  For automated checkpoints, the same comparison is available via
  `--zertifikat-pruefen`; return codes distinguish a match,
  operator error, and invalid evidence.
  The cross-check additionally compares the embedded Maskuro ID with the
  certificate; a freely entered foreign ID is thus also flagged even with
  an unsigned record.
  With a valid signature, the check result also shows the editor activated by
  administration, with operating system account, technical
  account ID, and platform. Unconfirmed data from unsigned or
  invalid records is not output.

- A new German document lab generates 160 fully synthetic
  TXT, HTML, PDF, and DOCX documents from ten domains and four
  structural variants. The manifest now explicitly distinguishes between
  data that must disappear and specialist text or
  factual identifiers that must be preserved; document family, mutation, and
  public structure source are traceably recorded.

- The German document lab was expanded to 280 files, seven structural forms,
  1,540 target items, and 1,036 preservation anchors. Newly checked are
  numbered forms, bracketed PDF/mask fields, and technical
  `=>` mappings. The expanded full run reaches 100 percent in TXT, HTML, PDF, and
  DOCX with zero false positives. Bracketed date and
  ID number fields, arrow separators, and explicitly labeled associations
  are now recognized structurally.

- A second lab expansion raises the count to 400 documents, ten
  structural forms, 2,200 target items, and 1,480 preservation anchors. JSON-like
  key values, YAML lists, and uppercase form fields together
  with the existing set reach 100 percent with zero false positives. Quoted
  dates of birth and ID numbers, as well as explicitly labeled roles such as
  insured, applying, filing-obligated, and authorized-representative persons,
  are now also recognized in these export forms.

- A separate OCR mode of the German document lab additionally generates
  200 pure image scans from all 40 families. Clean, low-contrast,
  low-resolution, JPEG-artifact-afflicted, and 90-degree-rotated pages
  are re-measured with exact pixel boxes, without changing the comparable
  1,600-file text baseline. The manifest separates
  toggleable date, money, and medical features from the base profile and recognizes
  documented OCR readings without counting them as additional target items. The
  measurement is broken down by mutation and document family. Narrow
  field boundaries prevent, among other things, `Az` in the place name `Graz` from
  redacting a following date as a case number; the current base matrix runs
  with zero false positives and zero aborts.

- Five further German document families for invoice/delivery note,
  bank/loan, rent/property management, school/university, and logistics/customs
  expand the lab to 600 files with 3,520 target items and 2,360
  preservation anchors. A narrow PDF table path uses the explicit header
  `Feld Angabe` when the text layer loses cell separators; a new
  `--familien` selection speeds up partial measurements. The 200 new files
  reach 1,320/1,320 with zero false positives and zero aborts.

- Insurance/claim, work/payroll, medicine/lab, vehicle/workshop, and
  engineering/maintenance expand the German document lab to 800 files with
  4,960 target items and 3,200 preservation anchors. Narrowly labeled policy,
  patient, inspector, and vehicle identifiers as well as new role, address,
  and organization fields are recognized. The new partial matrix and the
  full matrix reach 100 percent with zero false positives and zero
  aborts in TXT, HTML, PDF, and DOCX.

- Construction/tender, energy/environment, association/society,
  communication/calendar, and hotel/event raise the German
  document lab to 1,200 files with 7,920 target items and 4,800
  preservation anchors. New role, company, address, register, award,
  booking, and user account fields are also recognized in all
  export formats. Meter numbers remain preserved as factual identifiers. Partial and
  full matrix reach 100 percent with zero false positives and zero aborts.

- Catering/delivery service, pharmacy/prescription, funeral/cemetery,
  sports/membership, and real estate/broker expand the German
  document lab to 1,400 files with 9,360 target items and 5,640
  preservation anchors. New person roles, address fields, and
  search order numbers are recognized. Labeled company names with legal form
  remain fully protected even across an automatic line break;
  age classes and specialist job titles are no longer falsely replaced. Partial and
  full matrix reach 100 percent with zero false positives and zero aborts.

- Dental treatment, driving school, fire department/deployment, energy community, and
  package tour expand the German document lab to 1,600 files with
  10,840 target items and 6,440 preservation anchors. New roles, address fields,
  as well as treatment, training, deployment, energy, and
  travel contract identifiers are recognized structurally. The new 200-file
  partial matrix reaches 1,480/1,480; the full matrix reaches
  10,840/10,840. Both remain at zero false positives and zero aborts.

- The full measurement of the document lab reduced, through narrow official factual forms
  and structural rules, unnecessary replacements from 68 to 0, the explicitly
  measured preservation violations from 23 to 0, and the aborts from 3 to 0.
  The find rate rose at the same time from 91.1 to 100.0 percent; TXT, HTML, PDF, and
  DOCX each reach 100 percent. General
  table headers such as `Feld` are only slowed in the documented sequence `Feld`/`Angabe`;
  an identically spelled surname remains protected. Court case numbers with an
  ending letter, equals-sign fields,
  `Geburtsdatum des Kindes`, and several labeled individual names on the same
  line are fully recognized. Word tables and pre-line fields use
  their field header as temporary detection context; labeled
  PDF addresses remain fully protected even with a sentence-driven line break.

- German personal characteristic, occupation, and medical fields now also work
  with Windows line breaks. Single-letter gender entries such as
  `Geschlecht`/`w` are protected in the pre-line form. Factual
  `Artikel-PZN` fields, on the other hand, trigger neither a drug key nor a
  person find; genuine PZN, ICD, and ATC entries remain recognized.

- German form and number fields are more precise: "DW." now also works
  before a soft line break, explicitly labeled names are
  removed even in lowercase, and purely numeric case numbers are assigned
  to their correct ID type. Conversely, a coincidentally
  Luhn-valid invoice, receipt, or item number no longer counts as a
  credit card. Synthetic HTML and PDF output samples confirm removal
  and preservation in the finished document.
  ID numbers and usernames are also recognized when their
  label is in the immediately preceding table or form row; factual
  document numbers remain visible even in this form.

- Passwords are now also recognized behind a standalone field header on the
  previous line. Trailing special characters such as `!` or `#`
  belong entirely to the protected value. Product and item PINs
  are conversely no longer masked as a card PIN; explicit
  `PIN` and `Karten-PIN` fields remain protected.

- Lowercase form values are now output as an address or
  postal code with city rather than just a generic place for unambiguous German
  address and `PLZ/Ort` fields. Likewise, lowercase company values such as
  "beispiel service" remain fully protected behind a company field, without
  the final word being cut off as a supposed next field header.

- Help, FAQ, privacy text, and website now explain the provenance evidence
  together: neutral Maskuro ID in the document, optional assignment to the real
  operating system account only in the local verification log, user switching across
  Windows/macOS/Linux, and the significance of SHA-256 and the signature.

- Image-based technical bills of quantities are cleaned more conservatively.
  Unambiguous factual words such as "Abbruchhämmern," "Deckungsrücklass,"
  "Positionsnummern," "Einbauplatine," or "Terminsituation," as well as OCR forms
  split mid-word, no longer count as a person or place. A real
  municipal office quote thereby dropped from 140 to 90 unambiguous replacements,
  without producing new hits; names such as Schneider, Lang, Bauer, and Hahn
  remain explicitly protected.

- Further false positives from real quotes have been fixed: "Digital signiert"
  no longer contains a supposed person, a BIC is now recognized even without a colon
  behind its label, `15000 Alternativ` no longer counts as a
  postal code with city, and the EU citation "(VO (EG) 715/2007" no longer produces an
  organization. A photovoltaic quote thereby dropped from 26 to 16
  replacement occurrences; genuine names, places, and account data were
  preserved.

- In staff directories, the deputy abbreviation "Stv." and
  a standalone "FACILITY" section heading are no longer replaced as a
  person name. The real 13-page cross-check dropped from 878 to 875
  replacements; names, extension numbers, and the company name remained
  protected.

- Cleaned PDF, OpenDocument, and Office files now receive a neutral
  `MASKURO-…` identifier in their document properties. The verification report and
  signed verification log carry the same identifier as well as SHA-256 values of
  the source and result; the redaction certificate takes over the identifier from
  the finished file. A user name is only added if
  administration explicitly enables the existing user field.

- The main window and settings are organized more calmly: Save, Copy,
  Details, statistics, and deleting a detection profile appear only
  once the respective action is possible. Technical OCR language codes and
  long examples appear in the tooltip when needed instead of permanently in
  the work area. The detection page adapts better to narrower windows,
  without truncated explanations or horizontal scroll bars; the warning about
  plain text in the replacement list remains visible throughout.

- Detection now covers further German and international contact cases: phone numbers are now checked for all selectable country regions, Hungarian and Croatian contract roles now also fully capture surnames that match an occupation, and numbered spare-parts/material lists no longer trigger a person false positive because of "Mutter / Flach." Person fields with an evidently digit-containing factual value are no longer adopted as a name; the machine-readable passport zone (MRZ) can also be toggled together via the "Identifiers" group.

- Companies without a legal form are now better distinguished from persons behind
  ambiguous employer fields: names such as "Huber Handel," "Müller Logistik," or
  "Kowalski Handel" are fully captured as a company, while
  "Arbeitgeber: Bauer Anna" remains a person name. The automatic
  country selection continues to take the entire French-speaking area,
  including Luxembourg, into account for French documents.

- Recognized signatures and personal text within an image were previously always covered with a black rectangle — even when a different color or a pattern such as "rainbow" was set for redactions. These image areas now also adopt the chosen redaction appearance; the opaque area continues to be written directly into the pixels.

- English detection was re-measured and specifically improved against eleven manually translated real documents: inventory status, technical quote and webshop fields, and roles in staff directories remain visible, "CV" is no longer read as a legal form in the template sentence, quoted fonts are preserved, and names in vertical résumé headers, multi-page staff lists, behind "Account manager," and digit-starting company names are fully recognized. Austrian company register numbers now also work behind an English label; the short form "Customer:," EAR registration numbers, and employer numbers carry their value. Dimension chains, cable types, EU legal references, quote validity dates, places of performance, places of jurisdiction, register courts, the tax abbreviation "NoVA," technical numbers in tire labels, as well as standard references such as "OVE R6-2" and "AStV" no longer produce a false positive. A valid labeled IBAN ends cleanly before the registration field or the heading of the following line; addresses with a commercial-zone addition are fully recognized even from PDF text streams with Windows line breaks. English company introductions and structured savings bank names are fully delimited. The country of the source document is preserved for the language variants of postal codes and country-specific identifiers.

- In recipient and message header lines, the language model could merge the first two names of a comma list into a single find ("Bcc: Huber, Mayer"). Both names are now recognized, replaced, and listed in the report individually — likewise behind "Sent:," "Reply:," and "Fwd:."

- The machine-readable zone of a passport or ID card (MRZ) was missing from the group control "What is searched for." It now belongs to "Identifiers" and can be turned on and off together with this group.

- Anyone who chooses the "rainbow" template for replacement text now also gets redacted areas in the same appearance; previously they surprisingly stayed classic black. The redaction areas can then still be switched to a different template independently.

- The page panel of the touch-up editor could remain empty after restoring a saved window layout, until its width was changed by hand. The thumbnails are now rearranged after the visible window build and appear centered in the panel immediately.

- The colored verification marks around replacement text in PDFs remained barely visible depending on category and traffic-light color. A light-colored underline now reliably separates the verification frame from the colored placeholder and from the page background.

- Anyone who redacts a line in the touch-up editor whose document is set with tight line spacing (typical for quotes and bills of quantities) got a bar that reached into the ascenders of the line below — it was afterward only half legible. The bar now ends at the actually drawn typeface of the neighboring line; the redacted line itself remains fully covered, including its descenders.

- The practice document ("Help → Open practice document," also in the guided tour) now demonstrates every detection type: added to the fictional letter are a photo with a recognizable face, a handwritten signature, occupation and department, diagnosis and medication — alongside company name, amount, and date, which were already there. What the default deliberately leaves in place is explained by the sheet itself, along with the switch that removes it; the face in the photo is pixelated by default.

- Monetary amounts in the usual German notation with the symbol after the number ("1.240,00 €") were never found by the "Also remove monetary amounts" switch — "1.240,00 EUR" and "€ 1.240,00" always were. Now all three notations are recognized.

- Signature detection now also works on standalone image files: anyone who cleans a scan as JPG or PNG gets handwritten signatures in it redacted — the same detection, the same message in the report as with PDF. Images embedded in Office files continue not to be searched, because detection there measures as unreliable; the checkbox is therefore now called "PDF and image files: redact handwritten signatures."

- A redaction bar could visibly reach into the ascenders of the line below with tight line spacing and make it half illegible — the bar height came from the font metrics, not from what is actually on the paper. The bar now ends at the actually drawn ink of the neighboring line, in the touch-up editor as well as in automatic cleaning. The line's own descenders remain always fully covered; if the lines really overlap, the bar prefers to remain on the neighboring line rather than release anything.

- In a staff directory with the role under the name, a female management title ("Anna Berger" with "Montageleiterin" below) was drawn into the name replacement — the male form next to it correctly remained. The female "…leiterin" forms (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-, Amtsleiterin) are now treated like their male counterparts as a job title; Filial-, Personal-, and Vertriebsleitung are newly included in both forms.

- The optional occupation detection did not find female management roles such as "Projektleiterin," "Teamleiterin," or "Abteilungsleiterin," but did find their male forms. Both forms now count equally.

- In the preview window, on the Mac, the multiplicity marker stuck directly to the term ("Anna Musterfrau2" instead of "Anna Musterfrau 2"). The spacing is back.

- The comparison magnifier has a new button next to the zoom slider: with one press it lays it in full width over the result — half the height each, and the original at the same scale as the document (the magnifier zoom jumps to 100 percent for this). A second press docks it back small into the left column and restores the previous magnifier zoom. The circle icon next to it now only resets the zoom — its tooltip previously falsely claimed it also re-docks the window.

- In the toolbar of the touch-up editor, the chosen tool is again visibly marked as chosen: the active tool's button carries a filled area with a blue border — likewise every other enabled toggle button in the toolbar (such as the comparison magnifier or learning mode). The marking had been lost with the button's own redesign on August 29.

- Item numbers of a bill of quantities ("2.3.3.3, 2.3.3.4, 2.3.3.5" stacked) were mistaken for IP addresses and removed from the result; three-level numbers with a year-like last part ("2.3.19, 2.3.20") fell as calendar dates. An ascending number sequence at the start of a line is now recognized as what it is — an item list; genuine addresses (network tables with technical word context, numbers above 99) and genuine dates continue to be recognized.

- Surnames such as "Müller," "Fischer," "Bauer," "Koch," "Wagner," "Schneider," "Weber," "Jäger," "Schmied," "Becker," "Schuster," "Schäfer," or "Meister" remained in plain text in lists of the form "surname, first name" (e.g. "Teilnehmer: Müller, Peter; Nowak, Anna"), because they are also common occupation titles. They are now reliably recognized.

- When redacting a PDF, the bar could take the whole cell along in narrow table cells: from the hit "D-LINK" in a bill of quantities, the entire product description next to it was removed, even though the preview had only named the hit. The bar continues to cover whole address block lines and field labels, but swallows at most as much unrelated content as it covers protection-worthy content — the description next to the hit now remains.

- After "Reset view" in the touch-up editor, the page panel remained empty — the page thumbnails were only visible again after closing and reopening the window. They now appear directly after the reset too, centered as before.

- The touch-up editor has a fourth tool: **Remove** takes the text under the frame out without replacement — no bar (redact) and no placeholder (replace); the gap remains visibly empty. It works word-precisely; if there is an image underneath, its background is cleared white, and "Restore original" also reverses a removal without replacement. Its own toolbar icon and crosshair badge (cross), its own mnemonic key in all 18 languages (German F as in entFernen).

- In the PDF search bar, "Folder …" now stands to the right of the search options. Since replacing hits has existed alongside redacting, five buttons no longer fit side by side at ordinary window width — the first one was squeezed and its text truncated.

- "Reset all settings" now also resets the "Replace red/green with other colors" checkbox and marks it as "changed," like any other, when it deviates from the shipped default.

- Replacement text in PDFs now looks more even: where the full placeholder would have to be noticeably smaller than its line (e.g. "[BEG16]" squeezed into a short word like "Das"), a short form at line size ("[B16]") appears instead — well legible instead of tiny, and the number for restoring carries both spellings. A placeholder only becomes tiny when even the shortest form finds no room — that remains better than a bar with no information at all.

- A multi-colored replacement text (gradient or rainbow) in a PDF only stayed intact until the next intervention: every further replacement or redaction on the same page could squeeze already-set placeholders into an unreadable, compressed stack of letters — anyone replacing word by word in the editor saw only overprinted characters instead of "[BEG17]." Once-set placeholders now remain as they were set.

- The switch for standing exceptions in the preview is now called "Never remove" — like the list it enters into; previously it read "never again." The hit row next to it is tidier: the info icon "ⓘ" is bigger and easier to hit, and the checkbox, replace marker, and button now share a common height. The sentence around a hit now actually uses its announced width — the previous width setting had silently been discarded by the display, and the excerpt wrapped further as a narrow strip.

- In the editor, the mouse cursor now indicates which tool is active: a crosshair for aiming, next to it a small icon — a bar for redact, swap arrows for replace, an undo arc for restore, a pixel grid for pixelate. The previous hand icons were dropped; a hand otherwise always means "grab and pan." It now has a fitting task: over a red-highlighted word or bar, the cursor becomes a pointing hand — a click is enough there.

- "Maximum detection (AI)" no longer offers a downloadable, local language model — the tier now computes exclusively via a custom AI configured under "Connect your own AI." Anyone who had already connected their own server notices no difference.

- The preview's guided tour now also explains the info icon "ⓘ," which shows the sentence around a hit. And this sentence itself is more legible: one step larger font, more line spacing, fixed width instead of a narrow, densely packed wrap.
- "Check file," "Detection rules and custom terms," "Clean text," and "Clean image" now also have their own guided tour — via a new "Guided tour of the window" button, since these four windows have no menu bar of their own.
- Names under nine Ukrainian contract-role labels remained incompletely recognized with a homographic surname when the label stood alone on its own line: "Покупець"/"Продавець" (buyer/seller), "Поручитель"/"Боржник" (guarantor/principal debtor), "Свідок" (witness), "Орендодавець"/"Орендар" (landlord/tenant), and "Спадкодавець"/"Спадкоємець" (testator/heir). The names are now fully recognized.

- The comment of a named range in an Excel workbook (Name Manager, "Comment" field) carried a name entered in it forward unchanged. It is now cleaned like the rest of the workbook's content.

- Names under seven Hungarian contract-role labels remained completely undetected with a homographic surname: "Bérbeadó"/"Bérlő" (landlord/tenant), "Vevő"/"Eladó" (buyer/seller), "Kezes"/"Főadós" (guarantor/principal debtor), and "Tanú" (witness). The names are now fully recognized.

- Names under the Czech buyer label "Kupující" remained completely undetected with a homographic surname. The name is now fully recognized.

- Names under the Russian guardian label "Опекун" remained completely undetected with a homographic surname. The name is now fully recognized.

- Names under six further Croatian labels remained undetected: "Jamac" (guarantor), "Glavni dužnik"/"Dužnik" (principal debtor/debtor), "Ostavitelj" (testator), "Nasljednik" (heir), and "Vjerovnik" (creditor). The names are now fully recognized.

- A saved HTML page with an embedded subpage in the `src` attribute of an `<embed>` (instead of `data` with `<object>`) carried personal data in it forward unchanged. It is now cleaned just like with `<object>`.

- Names under five Danish contract-role labels remained incompletely recognized with a homographic surname when the label stood with a colon before the name: "Arvelader"/"Arving" (testator/heir), "Befuldmægtiget"/"Fuldmagtsgiver" (attorney-in-fact/grantor), and "Værge" (guardian). The names are now fully recognized; the corresponding Norwegian labels have also been added as a precaution.

- Placeholders in Word and PowerPoint files now carry the same color as in the chosen appearance (solid, gradient, rainbow, or per category) — previously they remained in ordinary text color there, even when PDF results had long been colored.

- "Copy as text" and "Copy as Markdown" place the plain text of the result directly on the clipboard — for pasting into chat, email, or another program without first opening the file.

- Names under five further Slovenian labels remained undetected: "Toženec" (defendant), "Tožnik" (plaintiff), "Zastavitelj" (pledgor), "Zastavni upnik" (pledgee), and "Darovalec" (donor). The names are now fully recognized.

- The author name of a tracked table-cell change (inserted, deleted, or merged cell in Word) remained in the file, even when the same name as a comment author had long since been removed. It is now removed as well.

- Names under nine further Slovenian labels remained undetected: "Najemodajalec"/"Najemnik" (landlord/tenant), "Zapustnik"/"Dedič" (testator/heir), "Upnik"/"Dolžnik" (creditor/debtor), "Glavni dolžnik" (principal debtor), and "Skrbnik" (guardian/custodian). The names are now fully recognized.

- Names under five Slovenian labels remained undetected: "Izvedenec" (expert), "Kupec" (buyer), "Prodajalec" (seller), "Naročnik" (client), and "Izvajalec" (contractor). The names are now fully recognized.

- Names under five further Lithuanian labels remained undetected: "Užsakovas" (client), "Vykdytojas" (contractor), "Vežėjas" (carrier), "Siuntėjas" (sender), and "Arbitras" (arbitrator). The names are now fully recognized.

- Names under six further Lithuanian labels remained undetected: "Įgaliotinis" (attorney-in-fact), "Įgaliotojas" (grantor), "Naudos gavėjas" (beneficiary, insurance), "Trečiasis asmuo" (intervenor/third party in civil proceedings), "Ankstesnis nuomininkas" (previous tenant), and "Naujasis nuomininkas" (new tenant). The names are now fully recognized.

- A bookmark in ODT documents (`text:bookmark`) carries a freely assigned name, often named after the spot it points to (e.g. "Herr_Mueller_Unterschrift") — invisible to the reader, but literal in the file. The name is now cleaned along with it.

- Names under eight further Lithuanian labels remained undetected: "Pareiškėjas" (applicant), "Suinteresuotas asmuo" (respondent in non-contentious proceedings), "Ekspertas" (expert/appraiser), "Bankroto administratorius" (insolvency administrator), "Valdybos narys" (supervisory board member), "Direktorius" (managing director), "Palikėjas" (testator), and "Įpėdinis" (heir). The names are now fully recognized.

- Names under seven further Lithuanian labels remained undetected: "Liudytojas" (witness), "Vertėjas" (interpreter/translator), "Notaras" (notary), "Dovanotojas" (donor), "Apdovanotasis" (donee), "Pirkėjas" (buyer), and "Pardavėjas" (seller). The names are now fully recognized.

- Names under six further Lithuanian labels remained undetected: "Globėjas" (guardian/custodian), "Palikimo administratorius" (estate administrator), "Laiduotojas" (guarantor), "Pagrindinis skolininkas" (principal debtor), "Nuomotojas" (landlord), and "Nuomininkas" (tenant). The names are now fully recognized.

- A name under the Lithuanian label "Ieškovas"/"Atsakovas" (plaintiff/defendant as a party to proceedings) remained undetected, regardless of whether the surname was also a common word (e.g. "Vilkas" = wolf) or not. The name is now fully recognized.

- A person-index entry in ODT documents (bookmark for the keyword index) carried the name a second time in its own sort key — invisible in the running text, but literal in the later-generated index. The key is now cleaned along with it.

- The slide name and the section name of a PowerPoint presentation (visible in the selection pane or in slide sorter view) remained uncleaned because both hang as an attribute on an element that is not slide text. Both are now recognized.

- A Lithuanian hyphenated double surname such as "Petraitis-Kazlauskas" lost its second half as soon as any running text preceded it (it remained complete only at the start of the text): the surname is now fully recognized even then.

- A name under the label "Cesionar" (Croatian, assignee in a debt assignment) produced a false positive because the field label itself was falsely read as a person. A name under the Russian label "Цессионарий" (also assignee), on the other hand, remained completely undetected. Both cases are now fixed.

- A name under the label "Zedent"/"Zessionar" (German, debt assignment) remained undetected with no fallback when the surname was also a common word (e.g. "Bauer"). The name is now fully recognized.

- A name under the label "Darczyńca"/"Obdarowany" (Polish, donor/donee in a gift contract) remained undetected when the surname was also a common word (e.g. "Wilk" = wolf). Likewise, the Romanian label "Donatar" (donee) got stuck with an ordinary surname even as a supposed part of the name itself. Both cases are now fixed.

- A name under the label "Wierzyciel"/"Dłużnik" (Polish, enforcement creditor/enforcement debtor or general creditor/debtor) remained undetected when the surname was also a common word (e.g. "Wilk" = wolf). The name is now fully recognized.

- A name under the label "Poręczyciel"/"Dłużnik główny" (Polish, guarantor/principal debtor in surety contracts) remained undetected when the surname was also a common word (e.g. "Wilk" = wolf). The name is now fully recognized.

- A name under the label "Ubezpieczony"/"Ubezpieczający" (Polish, insured/policyholder in insurance policies) remained partly or completely undetected when the surname was also a common word (e.g. "Wilk" = wolf). Likewise a name under "Osiguranik"/"Osiguravatelj" (Croatian, the same roles), where it disappeared entirely along with the first name (e.g. "Golub" = dove). Both names are now fully recognized.

- A name under the label "Pełnomocnik"/"Mocodawca" (Polish, attorney-in-fact/grantor in powers of attorney) remained undetected when the surname was also a common word (e.g. "Wilk" = wolf). Likewise a name under "Opunomoćenik"/"Opunomoćitelj" (Croatian, the same roles), where it even disappeared entirely along with the first name. Both names are now fully recognized.

- A name under the label "Pozwany" (Polish, defendant as a party to proceedings) remained undetected when the surname was also a common word (e.g. "Wilk" = wolf). The name is now fully recognized.

- A name under the label "Najmoprimac"/"Najmodavac" (Croatian, tenant/landlord in rental agreements) remained undetected when the surname was also a common word (e.g. "Kovač" = smith). The name is now fully recognized.

- A name under the label "Pracodawca"/"Pracownik" (Polish, employer/employee as a contracting party in employment contracts) remained partly undetected when the surname was also a common word (e.g. "Krawiec" = tailor). The name is now fully recognized.

- Hungary had only the personal identifiers and the VAT ID in the country catalog: the company register number (Cégjegyzékszám) is now recognized when the field word "Cégjegyzékszám" or the abbreviation "Cg." stands immediately before it — the number itself carries no check digit.

- Estonia had only the Isikukood in the country catalog: the Käibemaksukohustuslase number (VAT ID on every Estonian invoice) is now recognized with a check digit.

- Latvia had only the Personas kods in the country catalog: the PVN reģistrācijas numurs of legal persons (business ID on every Latvian invoice) is now recognized with a check digit.

- An email with encrypted content (S/MIME or PGP/MIME envelope, `multipart/encrypted`) was output without any warning as apparently fully checked, even though its actual content was encrypted and thus unchecked. Such emails now point this out just like an unchecked attachment.

- Malta was missing from the country catalog: the Maltese VAT ID (VAT number) is now recognized.

- Luxembourg was missing from the country catalog: the Luxembourg VAT ID (n° TVA) is now recognized.

- A Bulgarian "Изчакайте" ("Please wait!") placed at the start of a sentence was reported as a place — the same model limitation as previously with Hungarian, Polish, Czech, and other imperative forms without their own language model. This false positive no longer occurs.

- A name under the label "Zleceniodawca," "Zleceniobiorca" (Polish), "Prestator" (Romanian), "Naručitelj," or "Izvođač" (Croatian) remained partly or completely undetected when the surname was also a common word (e.g. "Wilk," "Vuk" = wolf, "Vulpe" = fox, "Sokol" = falcon). The name is now fully recognized.

- A name under the label "Nadawca" (Polish), "Afsender" (Danish), or "Pošiljatelj" (Slovenian) remained partly or completely undetected when the surname was also a common word (e.g. "Sowa" = owl, "Bager" = baker, "Volk" = wolf). The name is now fully recognized.

- A name under the label "Gavėjas" (Lithuanian) or "Prejemnik" (Slovenian) remained partly or completely undetected when the surname was also a common word (e.g. "Vilkas" = wolf). As already with "Primatelj" (Croatian) and "Modtager" (Danish), the name is now fully recognized.

- A circular header such as "To All Staff" or "To All Employees" was falsely recognized as a person's name and removed. This no longer happens.

- A name under the label "Primatelj" (Croatian) or "Modtager" (Danish) remained partly undetected when the surname was also a common word (e.g. "Golub" = dove, "Bager" = baker). As already with "Odbiorca" (Polish) and "Destinatar" (Romanian), the name is now fully recognized.

- A full name in the signature line of a Danish, Norwegian, or Greek document remained partly undetected when the label "Underskrift" or "Υπογραφή" stood alone above the name — in the Greek case the surname was even recognized as a place instead of a name. As already with "Подпись" (Russian), the name is now fully recognized.

- Text on a phone photo lying on its side (the usual portrait shot that is only displayed upright via an image rotation marker) could be overlooked by text recognition, because it previously read the raw, sideways pixels. Such photos are now rotated the right way up before reading — as previously already done for face detection.

- A full name in the signature line of a Russian, Ukrainian, or Lithuanian document remained partly undetected when the label "Подпись," "Підпис," or "Parašas" stood alone above the name — the first name or patronymic was dropped. As already with "Potpis" (Croatian), the name is now fully recognized.

- A face on a phone photo lying on its side (the usual portrait shot that is only displayed upright via an image rotation marker) could be overlooked by face detection, because it previously checked the raw, sideways pixels. Such photos are now rotated the right way up before the search.

- A full name in the signature line of a Croatian document remained partly undetected when the label "Potpis" stood alone above the name or with a colon before it — the first name was dropped, whether on its own line or in "Potpis: Vorname Zweitname Nachname." As already with "Unterschrift" and "Signature," the name is now fully recognized.

- A married name behind the civil-status abbreviations "verh." (married) and "verw." (widowed) previously remained completely undetected, whether in parentheses, after a comma, or attached without a space ("Anna Meier (verh. Weber)," "Klaus Bauer (verw.Fischer)") — as already with "geb.," it is now reliably recognized.

- A name behind the power-of-attorney signature mark "ppa." (e.g. in the signature line of a business email or business letter) previously remained partly or completely undetected with a surname matching an occupation, such as "Bauer" or "Koch" — as already with "gez.," it is now reliably recognized.

- The number of the Polish national ID card (dowód osobisty) was only recognized without a space between the series and the number ("ABS123456"). But that is exactly not how the document prints the item — officially there is a space in between ("ABS 123456"), and in this notation the number previously remained undetected.

- An animated PNG (APNG, e.g. a short screen recording saved as PNG instead of GIF) was previously only checked and cleaned using its first frame, without this being reported — as previously with animated WebP, Maskuro now reports that every further frame remains unchecked in the result.

- An animated WebP image (e.g. from a screenshot tool or a chat application with several images in one file) was previously only checked and cleaned using its first frame, without this being reported — as previously with a multi-page TIFF, Maskuro now reports that every further frame remains unchecked in the result.

- A Slovenian hyphenated double first name ("Ana-Marija Novak") lost its first half as soon as running text preceded it in the text — the same error as previously with Polish. "Ana-" remained unredacted in plain text while the rest of the name was already replaced.

- A Polish hyphenated double first name ("Anna-Maria Kowalska") lost its first half as soon as running text or a preposition like "z"/"od" preceded it — the rest of the name was replaced, "Anna-" remained unredacted in plain text.

- Kazakh courtesy phrases "Хабарласыңыз"/"Байланысыңыз" (contact us) as well as Serbian verb forms "Помоћи," "Чекамо," and "Пишите" without their own language model were falsely recognized as a person's name or a place in phone sentences.

- The Azerbaijani courtesy word "Xahiş" (please/request) without its own language model was falsely recognized as a person's name in phone sentences.

- Indonesian and Malay courtesy/imperative words without their own language model, such as "Silakan," "Mohon" (Indonesian), "Sila," and "Tolong" (Malay), were falsely recognized as a person's name or a place in phone sentences.

- The Uzbek imperative form "Kutamiz" (we are waiting) without its own language model was falsely recognized as a place in phone sentences.

- Turkish imperative forms without their own language model, such as "Arayınız" (call) and "Bekliyoruz" (we are waiting), were falsely recognized as a person's name in phone sentences.

- Imperative forms in further languages without their own language model (Czech, Slovak, Greek), such as "Zavolejte" (call), "Prosíme" (we ask), and "Περιμένουμε" (we are waiting), were falsely recognized as a person's name or a place in phone sentences.

- Hungarian and Polish imperative forms such as "Hívjon" (call), "Kérjük" (we ask), "Várjuk" (we expect), "Zadzwoń" (call), and "Czekamy" (we are waiting) were falsely recognized as a person's name or a place in phone sentences.

- In a numbered name list without a table form (e.g. "1. Robert Brown," below it "2. Mary Johnson"), a name with certain English surnames (including "Brown," "White," "Green," "Black," "Young") was completely overlooked — the language model had appended the following line's number to the name, so the hit never matched exactly again.

- With the Polish language model, a preceding first-name initial before a surname (e.g. "J. Kowalski," "A. Nowak") remained unrecognized and uncleaned in the text — only the surname was replaced. Other tested languages (including German, English, Romanian, Croatian, Hungarian, Russian) already caught the same initial before this.

- A person's name behind a lowercase title such as "dr.," "ing.," or "dipl. ing." was not recognized at all in Hungarian, Romanian, and Croatian — not only the title but the whole name was lost (e.g. "dr. Kovács Béla," "ing. Andrei Popescu," "dipl. ing. Marko Horvat").
- In Slovenian meeting records, a pure role designation before a colon (e.g. "Tajnik:," "Podpredsednik:," "Poročevalec:," "Predsedujoči:") was falsely recognized as a person's name as soon as a genuine speaker name already stood elsewhere in the record.
- In Russian meeting records, a pure role designation before a colon (e.g. "Секретарь:," "Докладчик:," "Докладчица:") was falsely recognized as a person's name as soon as a genuine speaker name already stood elsewhere in the record.
- In Romanian meeting records, a pure role designation with a definite article before a colon (e.g. "Secretarul:," "Președintele:," "Vicepreședintele:," "Moderatorul:," "Consilierul:") was falsely recognized as a person's name — "Președintele" on its own already, the others additionally as soon as a genuine speaker name already stood elsewhere in the record.
- In Croatian meeting records, a pure role designation before a colon (e.g. "Izvjestiteljica:," "Zapisničar:"/"Zapisnicar:," "Predsjedavajući:") was falsely recognized as a person's name.
- A Polish PO box address "Skrytka pocztowa" behind a sender or recipient label (e.g. "Odbiorca: Skrytka pocztowa 45") was falsely recognized as a person's name.
- A Croatian PO box address "Poštanski pretinac" behind the address label "Adresa:" (e.g. "Adresa: Poštanski pretinac 45," also with an appended "br." for the number) was falsely recognized as a person's name.
- A place without further labeling in Norwegian running text (e.g. "Anna Hansen bor i Oslo") was not recognized — the language model there mostly names places with its own, previously unmapped label instead of the usual "LOC."
- A date in ISO year-month-day order with a hyphen or period (e.g. "2024-12-31") was not recognized as a date at all in some languages — most noticeably in Lithuanian, where official correspondence mostly gives dates in this order.
- A Hungarian VAT ID (közösségi adószám) in the officially equally valid, separator-less 11-digit form (e.g. "12345678123" instead of "12345678-1-23") was not recognized.
- A Polish tax number NIP with separators grouped 3-2-2-3 (e.g. "856-73-46-215," as is common on invoices from companies and sole proprietors) was not recognized — only the 3-3-2-2 grouping for natural persons matched.
- A company name under the Slovak field label "Zamestnávateľ:" or "Názov zamestnávateľa:" (employer/company) was not recognized.
- A company name under the Romanian field label "Angajator:" or "Denumire angajator:" (employer/company) was not recognized.
- A company name under the Hungarian field label "Cég:" or "Munkáltató:" (company/employer) was not recognized.
- A company name under the Polish field label "Pracodawca:" or "Nazwa firmy:" (employer/company) was not recognized.
- A company name under the Slovenian field label "Podjetje:" or "Delodajalec:" (company/employer) was not recognized.
- A company name under the Croatian field label "Tvrtka:" or "Poslodavac:" (company/employer) was not recognized.
- A spelled-out monetary amount with a lowercase currency (e.g. "500 euro") was not recognized, only the capitalized form ("Euro") matched.
- The surname behind "Schwager"/"Schwägerin" (brother-in-law/sister-in-law) (e.g. "Der Schwager Bauer erhält die Erbschaft.") was not recognized.
- With a Turkish address without a separating punctuation mark between postal code+city and street+house number (e.g. "34000 İstanbul İstiklal Caddesi No: 45"), the house number remained unclean.
- With a Slovak address without a separating punctuation mark between postal code+city and street+house number (e.g. "831 01 Bratislava Hlavná 15"), the house number remained unclean.
- A country of birth without further labeling in a Croatian form field (e.g. "Zemlja rođenja: Njemačka") was not recognized.
- A country of birth without further labeling in a Lithuanian form field (e.g. "Gimimo valstybė: Vokietija") was not recognized.
- A country of birth or residence without further labeling in a Polish form field (e.g. "Kraj: Niemcy") was not recognized.
- A nationality or place of residence without further labeling in a Slovenian form field (e.g. "Državljanstvo: Nemčija") was not recognized.
- A country of residence without further labeling in a Norwegian form field (e.g. "Bosted: Tyskland") was not recognized.
- New settings page "Notifications" (previously a section in "Program"): the three taskbar messages (preview ready, processing finished, update downloaded) now have their own dedicated place.
- New: the result can additionally be saved alongside as a plain text file (.txt) or with the .md extension — for further processing in an AI or another program.
- With a Croatian contact entry labeled "Osoba za kontakt"/"Kontakt osoba" (e.g. "Osoba za kontakt: Golub Marko"), the name remained completely unrecognized when the surname was also a common noun (Golub = "dove").

- With a Romanian contact entry labeled "Persoana de contact"/"Persoană de contact" (e.g. "Persoana de contact: Lup Ion"), the name remained completely unrecognized when the surname was also a common noun (Lup = "wolf") and the first name very short and generic.

- With a Polish contact entry labeled "Osoba kontaktowa"/"Osoba do kontaktu" (e.g. "Osoba kontaktowa: Wilk Adam"), the surname remained unrecognized when it was also a common noun (Wilk = "wolf," Zielony = "green").

- With a Romanian address without a separating punctuation mark between postal code+city and street+house number (e.g. "010061 București Strada Victoriei 30"), the house number remained unclean.
- With a Serbian address without a separating punctuation mark between postal code+city and street+house number (e.g. "11000 Beograd Bulevar Kralja Aleksandra 73"), the house number remained unclean.
- With a Greek address without a separating punctuation mark between postal code+city and street+house number (e.g. "104 32 Αθήνα Ερμού 15"), the house number remained unclean.
- With a Slovenian address without a separating punctuation mark between postal code+city and street+house number (e.g. "1000 Ljubljana Slovenska cesta 58"), the postal code remained unclean.
- With a Lithuanian address without a separating punctuation mark between postal code+city and street+house number (e.g. "LT-01100 Vilnius Gedimino pr. 9"), the postal code remained completely unclean.
- With a Hungarian address without a separating punctuation mark between postal code+city and street+house number (e.g. "1052 Budapest Kossuth Lajos utca 12"), the postal code remained unclean.
- A surname behind "Erben" (heirs) (e.g. "Die Erben Wagner erhielten die Mitteilung fristgerecht.") remained, in an inheritance/estate context, almost always unrecognized.
- A surname behind "Geschwister" (siblings) (e.g. "Die Geschwister Bauer wohnen in Linz.") had previously remained almost always unrecognized — unlike with "Familie"/"Ehepaar," this affected not only surnames matching an occupation (Koch, Bauer, Richter) but any surname at all in this position.
- A surname behind "Ehepaar" or "Eheleute" (married couple) (e.g. "Das Ehepaar Koch zieht um.") remained unrecognized when it was also a common noun or an occupation title (Koch, Bauer, Richter).
- An ordinary order, contract, or item number in the typical grouping pattern of a tax number or social security number (e.g. "030 4471 2298") was falsely redacted as such without any accompanying label.
- A receipt/case number in the format "year/running number" (e.g. in "Rechnung Nr. 4/2024/778899") was falsely redacted as a phone number by phone-number detection.
- A name behind "Herr"/"Frau" with a multi-word chain of academic titles before it ("Herr Dr. med. Weber," "Herr Prof. Dr. Krause") previously remained completely unprotected — previously only a single title word between the salutation and the name was recognized.
- A court case number in the classic format with a chamber/panel abbreviation ("4 Ca 1523/24," "Az.: 7 O 234/25") previously remained completely unprotected — even the common short form "Az."/"Gz." was not recognized alongside the spelled-out label.
- A credit card number split in the middle of its four-digit grouping by a line break — e.g. in a narrow table column — previously remained completely unprotected.
- A tax identification number split in the middle of its grouping by a line break — e.g. in a narrow table column or a form field — previously remained completely unprotected.
- A social security number split in the middle of its grouping by a line break — e.g. in a narrow table column — previously remained completely unprotected, not even partially replaced.
- A house number with a range like "12a-14b" or "3-5" was only half replaced — the second part after the hyphen remained openly in the result.
- A chassis number (FIN/VIN) split in the middle of its 17 characters by a line break, space, or hyphen — e.g. in a narrow table column or a vehicle registration field — previously remained completely unprotected.
- A letter/email salutation like "Liebe Anna!" or "Lieber Hans" — without a comma after the name, the most common form in casual emails — left the name completely unprotected, even in the full document with running text and a closing greeting below it.
- The same gap also affected the casual chat/email salutations "Hallo Anna!," "Hi Anna!," "Hey Anna!," and "Servus Anna!" without a comma — the name likewise remained completely unprotected.
- A pure signature block starting directly with "MfG" or "Herzlichst" — e.g. copied from the clipboard, without a preceding sentence — left the name below it completely unprotected.
- A field with several people, e.g. "Angehörige: Kaczmarek, Piotr (Sohn), Kaczmarek, Anna (Ehefrau)," merged both names along with the parenthetical note into a single, far too long hit — the second name partly remained unprotected in the result.
- A street without a "-straße"/"-weg" suffix — common in rural areas, e.g. "Am Marktplatz 5" or "Im Grund 12" — went unrecognized if followed by a postal-code/city line, for example in a registration certificate: "Neue Anschrift: Am Weidengarten 17, 54295 Trier" lost the street entirely, only the postal code was removed.
- A name behind a combined field label with a slash (e.g. "Name/Vorname: Bauer Klaus") was partly not recognized — an ambiguous surname like "Bauer" went undetected without the field evidence. The same gap affected combo fields like "PLZ/Ort: 04109 / Leipzig". The same applied to combo fields with a spelled-out connector instead of a slash, e.g. "Vor- und Nachname: Bauer Klaus" or "Nachname bzw. Vorname: …".
- A date of birth in the form "Datum der Geburt: …" and a date of death in the form "Todesdatum: …" or "Datum des Todes: …" were not recognized — only "Geburtsdatum: …" and "Sterbedatum: …" matched.
- A wedding date in the form "Datum der Heirat: …" or "Datum der Hochzeit: …" was not recognized — only "Hochzeitsdatum: …", "Heiratsdatum: …" and "Datum der Eheschließung: …" matched, even though divorce, naturalization, and civil-partnership dates already knew the same "Datum der X" form.
- A divorce date in the form "Datum der Scheidung: …" was not recognized — only "Scheidungsdatum: …" and the trailing verb form matched, even though naturalization and civil-partnership dates knew the same "Datum der X" form from the start.
- A civil-partnership date was not recognized at all until now — neither with a label ("Verpartnerungsdatum: …", "Datum der Lebenspartnerschaft: …") nor in running text ("… wurden am … verpartnert"). It is now replaced as its own data type, like birth, wedding, divorce, and naturalization dates.
- A naturalization date was not recognized at all until now — neither with a label ("Einbürgerungsdatum: …") nor in running text ("… wurde am … eingebürgert"). It is now replaced as its own data type, like birth, wedding, and divorce dates.
- A divorce date was not recognized at all until now — neither with a label ("Scheidungsdatum: …") nor in running text ("Die Ehe wurde am … geschieden"). It is now replaced as its own data type, like birth, death, and wedding dates.
- A wedding date behind the genealogy marriage symbol "⚭" without a label was not recognized, even though birth and death dates on the same line via the star and cross symbols were already recognized — the wedding date is now recognized too.
- A date of death behind the obituary cross without a label ("*03.06.1940 †21.11.2023") was not recognized, even though the date of birth before it via the genealogy star was already recognized — the date of death is now recognized too.
- A surname before a first name at the end of a subject/ticket line with preceding factual text and a dash ("Betreff: Reklamation - Bauer, Anna") was not recognized when the surname coincided with an occupational word — it is now recognized.
- Applicant and claimant numbers behind their label ("Bewerbernummer: 4471829", "Antragstellernummer: 7654321") fell through detection entirely — they are now recognized.
- Replace no longer redacts when there is no room for a legible placeholder — a placeholder that is too small is now shrunk instead of becoming an empty bar, as long as any room remains at all. Also new: whether a hit on an image (letterhead, scan background) is labeled or only redacted can now be set independently of the rest of the output type. And a hit on an image that is removed entirely used to be labeled as if the image remained — the placeholder appeared light on a background that was never redacted, and thus disappeared invisibly on the now-white paper.
- A hit on a **kept** image was always redacted in black and white when replacing, regardless of the chosen appearance (category colors, rainbow …) — visible as a break between colorful labels in running text and black bars on the letterhead. The image background now follows the same color as the placeholder next to it.
- Detection of the vehicle identification number (FIN/VIN) unconditionally flagged every 17-character alphanumeric code without I/O/Q as a chassis number — including order, serial, and license-key numbers that happen to have the same form. It now only counts with a context word nearby ("FIN", "VIN", "Fahrgestell", "Chassis" etc.).
- In ticketing/calendar systems, name detection after "Assigned to"/"Closed by" etc. dragged along the next field word when it directly followed on the same line without a separator ("Assigned to Max Mustermann Priority High" became "Max Mustermann Priority"). In Git commit headers, name detection likewise dragged along the **next** trailer key when two lines were joined by only a single space instead of a line break ("Author: julia bergmann Reviewed-by: …" became "julia bergmann Reviewed-by"). Both brakes have been added.
- The name behind "p.A.", "zH"/"zHd", "i.A."/"i.V." and "geb." dragged a directly following department word into the same hit when it stood without a separator on the same line ("p.A. Max Mustermann Buchhaltung" became "Max Mustermann Buchhaltung", "i.A.Max Mustermann Vertrieb" became "Max Mustermann Vertrieb"). The same brake as with "Assigned to"/Git trailers has now been added here too.
- A labeled IBAN directly above the BIC, BLZ, or SWIFT line dragged that line's label into its own hit, because "BIC" and "BLZ" themselves looked like another block of numbers — from "IBAN: DE89 … 0130 00" and the line below, a single, over-reaching hit resulted, and the label of the next line disappeared along with it during cleaning. This affected nearly every bank detail with IBAN and BIC stacked on top of each other.
- The hit panel now says **where** a placeholder is that it cannot find on the page. Two cases previously only reported "not found," even though the replacement had taken place: if the placeholder is in non-visible secondary text — such as a link's target address, an annotation, or a form field — the row now carries this as its own note ("in secondary text"), and clicking explains it. And if the placeholder was written in shortened form for lack of room ("[N382]" instead of "[NAM382]"), clicking now jumps the long line to the short-form spot and names the renaming; the mapping deliberately links both lines together for this.
- If the same replacement value occurs several times in the document, each further click on the panel row jumps in a circle to the next occurrence — even across page boundaries; the status line counts along ("occurrence 2 of 4"), and the currently targeted spot is framed more boldly than the others. And if a placeholder is only in the hit list but nowhere in the document (because the spot was absorbed into an overlapping replacement), the status line now says so instead of the click remaining silently without effect.
- An abbreviated first name behind "an" or "für" is now reliably recognized as a name — "Überweisung an M. Wagner" and "Rechnung für M. Wagner" previously often remained unclean, while the same name with a different preceding label (e.g. "Zahlungsempfänger:") was already found. This mainly affected bank statement and posting lines.
- "Angeklagter"/"Angeklagte"/"Beschuldigter"/"Beschuldigte" now count as a name field: if a name in criminal proceedings documents stood directly behind one of these labels, it previously went completely unrecognized for around half of the names tested — neither first nor last name.
- The spot clicked in the hit panel is now framed in blue instead of highlighted in yellow — on the colored traffic-light-check areas, the yellow of search hits was not distinguishable. In addition, clicking now also finds multi-word replacement values (invented names, masked numbers): previously the click had no effect on such lines, because the hit location was only searched word by word.
- Adoptive, foster, and step-parents ("Adoptivvater," "Pflegemutter," "Stiefvater," and others) are now recognized as a name field; the name previously fell through unclean.
- Number-heavy tables and lists are no longer falsely discarded: if a short number (e.g. a customer-number fragment misread as a phone number) was replaced, the final check reported the same digit sequence as a remaining item even when it merely happened to occur elsewhere inside an entirely different number — and then delivered no result at all. A number now only counts as a remainder where it stands as its own number.
- Civil-status documents: "Vater:"/"Mutter:" is now recognized as a name field; the parent's name previously fell through unclean.
- Further family roles ("Pate," "Großvater/-mutter," "Ehepartner," "Lebenspartner," "Onkel," "Tante") are now recognized as a name field; the name previously fell through unclean.
- The German bank sort code (Bankleitzahl) is now also recognized in its official grouped form ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), not only as eight contiguous digits.
- The German pension insurance number is now also recognized with a period, hyphen, or slash between the five blocks ("65-170839-J-08-8", "65.170839.J.08.8"), not only with spaces.
- The main window appears faster: the detection libraries (Presidio including the language-model substrate) were previously already loaded during window setup — around four seconds on Windows before anything was even visible. They now load fully in the background; the "Clean" button becomes available, as before, only once everything is ready.
- Office documents with many images or videos are written faster: already-compressed media is now stored in the result package instead of being uselessly compressed a second time — that previously saved no bytes and tended to make JPEGs larger.
- Spreadsheets and other documents made of many small text units are checked faster: language detection now processes all cells and paragraphs of a document in one pass instead of individually — with demonstrably the same hits (400 cells: from around 4.7 to 2.5–3.5 seconds).
- List-like PDF pages (directories, item lists) are noticeably faster when inserting placeholders: the space search per label previously ran over all words on the page — now only over the surrounding line, with demonstrably the same result (on a page with 300 labels, around sixteen times faster).
- Image-heavy documents skip several unnecessary work steps per image: counting faces and codes on PDF pages no longer decodes the page image twice, checking for metadata no longer decrypts a clean image at all, pixelated images are written with normal instead of the slowest PNG compression (same size, a third of the time), and without a configured watermark the useless rewriting of the whole PDF at the end is skipped.
- Scanned PDFs with text recognition enabled are noticeably faster to process: previously, every page was rendered twice in full resolution (once for reading, once for rasterizing) — the image is now reused. And on Windows/Linux, text recognition reads the strips of a large scan in one pass instead of starting a separate program for each strip.
- Large documents are cleaned noticeably faster: matching already-found values previously grew with the number of hits (a 64 KB text block cost around one second just for this at the end of a large file, now a sixtieth of that), and the search for company legal forms ran with all ~280 catalog forms over every text location (now around twenty times faster, with demonstrably the same hits).
- A name directly after "Beste Grüße"/"Beste Wünsche" without preceding text or punctuation was not recognized at all — a pure signature block with no running text before it made the name disappear without a trace.
- An address field at the start of a document with a surname that matched an occupation ("Bauer Anna," "Koch Stefan" as the first line above street and city) previously partly went unrecognized or was classified as a place rather than a person — without preceding text, the language model lacked the sentence structure that otherwise lets it recognize "Bauer" as a name rather than an occupation.
- A name behind the signature mark "gez." with a surname matching an occupation before the first name ("gez. Bauer Anna" at the end of a notice or judgment) previously was incompletely recognized — only the first name was found, the surname disappeared without a trace.
- A name directly behind a customer number, contract number, or similar ID without its own line ("Vertragsnummer 55219 Bauer Anna," "Kundennr. 4711 Bauer Anna") was previously incompletely or not recognized at all when the surname matched an occupation.
- The icon in the macOS menu bar is now a template that adapts to light and dark mode like its neighboring icons — with its two cut-out bars it remains recognizable as Maskuro. If the clipboard watcher is running, this is shown by a separate dot at the shield's tip.
- A click in the hit panel now also leads to the location in anonymizing mode: switch page, scroll to the image, highlight in yellow. Previously the click had no effect there, because it still considered the placeholders unnumbered — since every hit now carries its own number, the spot is unambiguous. Only for a truly unnumbered placeholder does the status line still explain why no jump target can be determined.
- The first save in the touch-up editor (Ctrl+S or the floppy-disk button) now asks for a location, like "Save as …" — pre-filled with the original's folder and the result name. Previously the file landed silently next to the original. Anyone who already chose the storage location via the status line beforehand is not asked again; every further save continues to write the same file as before.
- If the safety check before saving reports a suspicious spot, "Back to check" now leads there: the first occurrence scrolls into view and is framed in red, the status line names it. Previously one was left alone with a page number and point coordinates. From the main window, the editor now opens at that location for this purpose. The button now also leads to the target when there is a note about a differing page count — to the first page that exists in only one of the two documents.
- Anyone who switches the preview to "Side by side in two columns" now automatically gets a window that both panes fit into — previously they squeezed into the old width until you dragged it yourself. It only widens up to the screen edge and is never narrowed back; a width you dragged yourself remains as set.
- Last name and first name in separate table columns (e.g. "Nachname | Vorname" in a registration confirmation or a CSV export) remained unclean — each cell on its own looked to detection like an arbitrary word with no name context. They are now recognized.
- Surname and first name on the back of an EU card-format driving license remained unclean — there they stand behind the official field codes "1." and "2." instead of behind a German word, and that is exactly what left them unrecognized. They are now recognized when the license number (field code "5.") stands next to them.
- The vehicle owner's first name on the vehicle registration certificate remained unclean — it stands behind the official field code "C.1.2" instead of behind a German word like "Vorname," and that is exactly what left it unrecognized. Surname and first name under field codes C.1, C.1.1, and C.1.2 are now recognized.
- The first line of the machine-readable zone (MRZ) on a passport or ID card remained unclean — it carries the name in the format "SURNAME<<FIRSTNAME" and slipped through completely even with the new MRZ recognizer for the check-digit line. A find now only counts if a check-digit-valid second MRZ line stands directly next to it — the name line itself carries no check digit of its own.
- The second line of the machine-readable zone (MRZ) on a passport or ID card remained completely unrecognized — it contains the passport number, birth date, and expiry date in plain text, but matched no existing recognizer at all. A dedicated recognizer now verifies the four ICAO check digits.
- A license plate without any space before its label remained unclean — "KennzeichenM-AB1234" or "KFZ-KennzeichenM-AB1234" were not recognized at all, because the underlying license-plate check requires a non-word character before the plate. This affected vehicle data where there is no space between the field word and the plate.
- A phone number without any space before its label remained unclean — "Handynummer0171/2345678" or "Tel0171/2345678" were not recognized at all, because the underlying phone-number check requires a space or punctuation before the number. This affected contact details where there is no space between the field word and the number.
- A birth name behind the abbreviation "geb." was not recognized at all — "Julia Bergmann (geb. Weber)" found only "Julia Bergmann"; the period in "geb." caused the language model to skip the following name entirely. This affected personal data with a birth name in parentheses or after a comma.
- The first name before a nickname in quotation marks remained unclean when a salutation and title stood together before it — "Herr Dr. Klaus "KP" Peters" yielded only "Peters," "Klaus" remained legible. This affected signatures and contact details with title and nickname.
- A name behind the period-less short form "zH"/"zHd" (attention of) was not recognized at all — unlike with "z.Hd." with a period, the missing sentence structure dragged the name away with it. This affected addresses without a period in the abbreviation.
- A name behind "p.A." (care of) was not recognized at all — the period in the abbreviation caused the language model to skip name detection entirely. This affected invoices and applications with a collective address.
- A name behind "i.A."/"i.V." (on behalf of/representing) attached without a period was not recognized at all, e.g. "i.A.Robert Lang" without a space — the same sentence-structure error as with "p.A.". This affected signature lines and email signatures in representation cases.
- A plain attendance list in bullet-point form without any further data ("- Max Mustermann," also with a period at end of line) lost all names to the same brake that is actually meant only to protect factual enumerations like "- Farbe: Blau". Such lists are now recognized.
- Files that could no longer be cleaned can be cleaned again. A value that had already been replaced by detection could be rediscovered inside its own, already-replaced marker like "[SVNR1]" — the final check then rejected an impeccably cleaned file. In addition, a phone reference in a CSV table is now also removed, and anyone who restricts the search to individual types now gets it applied the same way everywhere in the document — including in an image's alt text, an Excel header row, a dropdown list, or an HTML attribute.
- A name behind the email header "To:" (or "To" without a colon) was not recognized, because a foreign language model read the whole line as a single unremarkable hit and swallowed the name inside it entirely — unlike with "Cc:," "Bcc:," or "From:" before the same name. A name behind "To" is now reliably found.
- The wedding date could not be treated as a date in custom rules ("move" was rejected with "only available for dates"), was missing from the group assignment of hit types — meaning it could not be turned off via the "What is searched for" markers — and received the full wording as a placeholder instead of a short abbreviation like the date of death. Fixed for all six abbreviation/label tables.
- A value deliberately deselected in the preview could still be redacted elsewhere: if, for example, an email address was deselected, the address itself remained, but its local part without the domain was replaced as soon as it matched the derived username of another, still-selected person ("anna.musterfrau@beispiel.de" next to "Anna Musterfrau"). A deselected wording now stays off-limits document-wide, regardless of which hit type it comes from.
- A date of birth remained unrecognized if a family register or civil-status extract carried it under a shared header with the place of birth ("Geburtsdatum, Geburtsort: 19.11.1982, Steyr") — the second field word between "Geburtsdatum" and the date previously made detection fail entirely.
- An already-recognized phone number remained legible in its shortened confirmation form when it was mentioned elsewhere in the same document only by its last four digits ("erreichbar unter der Nummer ...5678," "Rückruf unter ...5678") — the same pattern as with IBAN and credit card.
- An already-recognized credit card number remained legible in its shortened confirmation form when it was mentioned elsewhere in the same document only by its last four digits ("Ihre Kreditkarte endet auf ...0366") — the same pattern common in payment confirmations as with the IBAN.
- An already-recognized IBAN remained legible in its shortened confirmation form when it was mentioned elsewhere in the same document only by its last four digits ("Die IBAN endet auf ...3201") — a pattern common in confirmation emails.
- A speaker in a chat or meeting log remained unrecognized if a salutation stood before their name ("Herr Bauer: …," "Frau Koch: …") — and this often also affected the next speaker line in the same log, because too few recognized lines remained to classify the document as a log at all.
- A date of birth remained unrecognized when the field word "geboren" stood AFTER the date instead of before it ("Das Kind wurde am 14.01.2026 geboren") — this is how, for example, a parental-leave or maternity-protection certificate phrases a child's date of birth. Previous patterns always assumed the field word came before the date.
- A form label with a reaction or checkmark symbol directly before it ("Ansprechpartner 😊:," "Kontaktperson ✓:") was no longer recognized as a label, and the name below or after it was thus sometimes only partially found (e.g. only the surname with "Mayer Roman").
- The same gap also affected especially protection-worthy data under GDPR Art. 9 (religion, health, union membership): a reaction symbol directly before the separator or line break ("Konfession 😊: römisch-katholisch") caused the label to fail entirely, and the data remained completely unrecognized.
- An address with a hyphenated double place name (e.g. "79761 Waldshut-Tiengen," "78050 Villingen-Schwenningen") lost the postal code entirely, even though the place itself was recognized and redacted — on a vehicle document or cover letter, the postal code thus remained legible.
- A table column without column spacing (a genuine PDF text extract) could, under a name column, also falsely redact two capitalized words standing next to each other by chance as a person, e.g. two place names in a data row; this is now only the case when no other hit at the same spot already recognizes something else.
- The same name column, in the same row form, also falsely redacted two factual words unknown to the language model (e.g. "Frontend Backend," "Turbo Modul") as a person, because no other hit triggered the brake there; it now additionally requires at least one of the two words to be read by the language model itself as a proper noun.
- The German pension insurance number was not recognized in its official full grouping (e.g. "65 170839 J 08 8" — as it appears on the social security card and payslip) and remained in the original; only the compact spelling and the form grouped only up to the letter were recognized.
- The German tax identification number was not recognized at all in its official spelling (grouping 2-3-3-3, e.g. "48 836 075 988" — as it appears on every real tax assessment and every notice from the Federal Central Tax Office) and remained in the original; only the rarer 3-3-3-2 grouping was covered.
- The North Rhine-Westphalia tax number (e.g. "221/5147/0815," with a four-digit instead of three-digit second group) was not recognized at all in tax assessments and remained in the original — every other German state was already covered.
- In employment contracts, a name behind the label "Arbeitgeber:" was completely overlooked as soon as the surname was also an ordinary word (e.g. "Bauer Anna") — "Arbeitgeber" appears in the list both as a name and as a company label, and the company assignment overwrote the name assignment.
- In a rental agreement header with the labels "Vermieter:"/"Mieter:", a surname that is also an ordinary word (e.g. "Bauer") was overlooked — only the first name remained recognized. Numbered tenant parties ("Mieter 1:," "Mieter 2:") were additionally affected, even for names without this ambiguity.
- In a court record with the labels "Zeuge:"/"Kläger:"/"Beklagter:" (also numbered, "Zeuge 1:," "Zeuge 2:"), a surname that is also an ordinary word (e.g. "Bauer") was likewise overlooked — only the first name remained recognized.
- In certificates of inheritance, powers of attorney, dunning proceedings, and purchase contracts, a surname that is also an ordinary word (e.g. "Bauer") was overlooked behind labels such as "Erblasser:," "Erbe:," "Vollmachtgeber:," "Bevollmächtigte:r," "Antragsgegner:," "Schuldner:," "Gläubiger:," "Käufer:," "Verkäufer:," "Vermächtnisnehmer:," or "Testamentsvollstrecker:" — sometimes only the first name remained recognized, sometimes the whole name was dropped.
- In a multi-party list before the case-caption separator "./." (e.g. "Sand, Werner und Huber, Anna ./. Wechsler, Martina"), the first party remained unmasked — only the party immediately adjacent to "./." was recognized.
- In the case-caption separator "./." (e.g. "Sand./.Wechsler"), the name after the symbol was completely overlooked when there was no space there — detection only worked with a space before and after.
- The surname "Wahr" was completely overlooked when it stood alone (e.g. "Frau Wahr bearbeitet Ihren Vorgang.") — the word happens to also be on the list of common German words that otherwise filters name finds out of sentences like "Das ist wahr."
- Surnames such as "Los," "Weit," "Rund," or "Hoch" were completely overlooked when they stood alone (e.g. "Herr Hoch übernahm die Leitung.") — all four words happen to also be on the list of common German words that otherwise filters name finds out of sentences like "Rund einhundert Gäste kamen zur Feier."
- Surnames such as "Ganz" or "Recht" were completely overlooked when they stood alone (e.g. "Herr Ganz unterschrieb den Vertrag.") — both words happen to also be on the list of common German words that otherwise filters name finds out of sentences like "Ganz genau, das stimmt."
- A form field with an asterisk or a superscript footnote digit behind the label (e.g. "Konfession*: römisch-katholisch" or "Religionszugehörigkeit¹: evangelisch") was not recognized and remained in plain text — only the form without this character matched.
- The same field also remained in plain text when two footnote marks stood behind the label at once (e.g. "Konfession**: römisch-katholisch" or "Gewerkschaft¹²: ver.di").
- A version number such as "Softwareversion 4.2.1.19" or "Firmware Build 2.0.4.11" is no longer falsely redacted as an IP address. The same now applies to receipt and case numbers such as "Rechnungsnummer 10.20.30.40" or "Bestellnummer 7.8.9.10".
- Two IBANs directly one below the other (e.g. one's own and that of a foreign business partner in an invoice header) were no longer both recognized — the second remained unnoticed.
- A labeled IBAN sometimes dragged along the following word in the sentence ("Bankverbindung AT61 … wird belastet" was redacted all the way into "wird") whenever the following word was lowercase — the plain-text remainder next to it was left untouched.
- Liechtenstein addresses are now recognized ("FL-9490 Vaduz"), just as German, Austrian, and Swiss ones already were.
- Passport and travel-document numbers are now recognized behind their label and removed (e.g. "Reisepassnummer: C01X00T471").
- Residence permit and registration certificate numbers are now recognized behind their label and removed.
- An ID number behind its label is now also recognized when an en dash separates instead of a colon (e.g. "Kundennummer – K903944").
- Bank details labeled "IBAN" or "Kontonummer" are now also recognized when an en dash separates instead of a colon.
- A name behind a label such as "Kontaktperson (Vertrieb)" or "Sachbearbeiter/in" is now also recognized with a parenthetical addition or a gender-neutral slash ending.
- The same asterisk gender form ("Sachbearbeiter*in") is now also recognized.
- A name behind a label is now also recognized when an equals sign separates instead of a colon (e.g. "Ansprechpartner = Mayer Roman" or "Kontaktperson=Mayer Roman"), as is common in configuration files or CSV headers. If several such label-value pairs stand separated by semicolons in one line, only the first value is now recognized instead of the whole rest of the line.
- A GPS coordinate pair behind the word "Koordinaten" is now reliably recognized (e.g. "Koordinaten: 48.2082, 16.3738") — the word carried the wrong inflected form in the internal catalog.
- An ID number behind its label (customer number, contract number, case number, ID-card number, and around a hundred other field words) was no longer recognized as soon as the label did not exactly match the stored capitalization — "kundennummer:" in an email or "KUNDENNUMMER:" in a form header remained untouched.

### New

- **Realistic replacement values are now a deliberately applied example instead of a default.** The exception table in the "Placeholders" tab now starts empty. A new button optionally enters plausible fake values for name, place, address, organization, email, phone, extension, and IBAN. It explicitly leaves monetary amounts at the numbered placeholder; the "invent" strategy remains selectable by hand for individual types.
- **The AI tier can use the graphics card.** On Windows, an additional package of just under 17 MB can be downloaded for this; the AI tier then computes noticeably faster on a suitable graphics card than on the processor. Anyone without one, or who doesn't download it, keeps working unchanged — just slower. On macOS the acceleration is already built in regardless.
- **Two new notifications via the taskbar icon**: when the preview is ready for review before replacement, and when a processing run is finished. Both are enabled by default and can be turned off individually under *Settings → Program → Notifications*.

### Changed

- **ID-card and driving-license numbers are now recognized** when their label precedes them ("Personalausweisnummer: …," "Führerscheinnummer: …") — previously both fell through every detection.
- **Maskuro now follows Windows' contrast themes.** Anyone who has turned one on under *Settings → Accessibility → Contrast themes* previously got it everywhere except here: Maskuro then applied its own colors afterward. Now it stays with the system's theme — windows, lists, drop zone, log, and status colors. The colored traffic-light check in the preview and touch-up windows is deliberately omitted there; what it says has stood alongside as a symbol and as a word ever since anyway.
- **Review need no longer relies on color alone.** Red, orange, and green are nearly equally bright — anyone with red-green color blindness saw a list without differences in the preview and hit panel, and that is roughly every twelfth man. Every row now also carries a symbol that differs in shape: ▲ check first, ● check, ○ well documented, ◆ unrated. The tooltip names it in words, and a screen reader reads it aloud.
- **Alt opens the menus again as usual.** The menu bar had no keyboard shortcuts: anyone not using the mouse had to arrow through every menu. Every entry now carries an underlined letter — Alt+D for "Datei" (File), from there B for "Beenden" (Exit) — in every interface language.
- **Controls tell a screen reader again what they are for.** In the touch-up window, the rules window, the log, the word lists, the help, the search run, and five further windows, lists, search fields, dropdowns, and sliders were previously only announced as "tree" or "combo box" — without saying of what. Around forty spots now carry a name. (The main window had been fine since August; the windows added afterward never went through that step.)
- **Anyone operating by keyboard sees everywhere where they are.** The review-need sliders, the checkbox and the "never again" button of the preview, the type headings inside it, the page panel of the touch-up window, and the settings sidebar were missing the frame the system otherwise draws around the focused control.
- **Larger system font no longer cuts anything off.** Anyone setting *Accessibility → Text size* above 175% previously lost the end of labels in folder monitoring and in the keyboard-shortcut fields. The help's chapter list already truncated long chapter names even at ordinary font size; it now wraps them and names the full title in the tooltip.

- **Detection has become noticeably faster.** The recognizer for labeled ID numbers ("Kundennummer: K903944") previously checked over 1200 individual patterns in sequence per text segment — this was the single biggest item in detection time, for every paragraph and every table cell. It is now a single pattern with the same result: on the measurement corpus, not a single hit changes, and the base tier per text segment becomes roughly three to four times faster.
- **The window appears immediately on startup.** Previously the main window loaded the full language tools before it even showed itself — around four seconds of blind time on every start. The models now load in the background as intended, while the window already stands; the Clean button, as before, only becomes available once everything is ready. Pure informational command-line calls (e.g. `--version`) also now respond immediately instead of after several seconds.
- **Images are now read only once during automatic language detection.** Previously, with the "Language: automatic" default, text recognition ran twice over the same image — once for the language guess, once for the actual check. Image files, clipboard images, and the text window are thus roughly twice as fast; with text recognition switched off, the reading that previously ran unnoticed anyway is now skipped entirely.
- **Saved web pages and emails are cleaned faster.** Values in HTML attributes, comments, and embedded data blocks were previously recognized individually — a municipal page with hundreds of labels put hundreds of individual queries to detection. They are now collected and recognized only once per distinct value; on the measurement corpus not a single hit changes, and .html and .eml are roughly a third faster.
- **The secondary storage areas of spreadsheets and presentations are also recognized in bulk now.** Alt text, formula strings, chart labels, comments, pivot caches, and document properties each put their own detection query per value — a workbook with thousands of pivot rows correspondingly thousands of queries. A collected run over the distinct values now runs instead, and the final full follow-up pass at the end now only runs if new values have actually been added since the running text. On the measurement corpus not a single hit changes.
- **Form-heavy PDFs are cleaned faster.** Fields, notes, bookmarks, and references repeat the same values en masse ("Off" on every checkbox, the same author on every annotation) — each previously put its own detection query. A value is now recognized only once per run; replacement and the consistency follow-up still run per location as before.
- **Large table files (.csv/.tsv) are cleaned noticeably faster.** The four table follow-up passes each previously split the same file into cells character by character on their own (around 30 s of extra work at 40 MB); now the splitting runs once. The column-header recognition (date-of-birth and personnel-number columns) issues one bundled query instead of one per cell — roughly twenty times faster with identical hits. And the name-column summary of large personnel lists is no longer quadratic in the number of rows.
- **The statistics panel no longer freezes the window.** Expanding the statistics previously read the text of many large files first and made the window unresponsive for seconds during that. The calculation now runs in the background; the panel opens immediately and fills in the numbers afterward.
- **The search-run report no longer freezes the window.** After searching many thousands of files, the shared folder was recalculated for every affected file; on large runs the window stood still for double-digit seconds during that. The report now appears immediately.
- **PDFs with text recognition are checked faster.** Every page was unnecessarily converted to PNG format twice during the cross-check; the already-existing image is now passed through instead. The result is unchanged, only the check runs more quickly.
- **Gradient annotations on large images no longer stutter.** Dragging the handles of a gradient annotation previously recalculated the gradient point by point — a visible stutter on a large screenshot. The result is the same, just without the pause.

### Fixed

- **The cross to remove a file from the list is a plain X again.** The new editor tool "Remove" had accidentally used the same icon identifier and thereby also showed its red cross with the dashed text line in every file row. Both actions now have separate icon names and keep their respective appropriate look.
- **Multi-part data is now also recognized in PDFs across a visible line break.** Maskuro additionally reads the geometrically generated page text as an offset-matched running-text view. This applies to all base- and high-tier recognizers as well as custom search patterns, not only to the first visible case "Diabetes mellitus Typ 2." Blank lines and recognized table or section boundaries remain hard limits; hit locations continue to fit exactly onto the words to be redacted.
- **The example under "Pseudonymize" contradicted itself.** The sentence promised "same person, same number" and then showed two different numbers — exactly the picture that is correct under "Anonymize." Both examples now match their own sentence.
- **A freshly inserted placeholder could remain as an overlapping smear of letters instead of disappearing when using "Restore original."** A single-color placeholder previously wrote its own output command per character, of which only the first carried its own text matrix — the next time the same spot was edited (e.g. "restore" right afterward), the remaining character commands were assigned the first one's character indices in turn, and the placeholder split into two overlapping positions. A single-color placeholder now gets a single output command for its entire text.

- **If the same redacted or removed value stood under two lines in the touch-up window and both were marked for reversal, the second line falsely counted as "not unique" — even though the value had long since been restored.** Both lines now count as done.

- **The name after "Reply-To:" is now found.** In an email header like "Reply-To: Huber," the name previously went completely unrecognized — the language model read "Reply-To:" as its own, false person and overlooked the real name after it.

- **The email header words "Reply" and "Fwd" are no longer redacted as a name themselves.** In a subject line like "Fwd: Angebot von Huber," the header word itself was previously recognized and redacted as a person in addition to the actual name.

- **"Arbeitgeber: Siemens AG" is now recognized as a company, no longer as a person.** If the company value behind the label "Arbeitgeber" carried a legal form such as GmbH, AG, or KG, it remained a person hit despite organization detection being enabled — only the narrower case without a legal form ("Wollmuth und Partner") was previously recognized as a company.

- **An address recognized once no longer remains elsewhere.** If a street address was recognized and replaced in one place, the same address could remain in a second place — for example in a hard-to-read footer of a scanned document, where automatic text recognition read it garbled. Addresses are now, like names and companies for a while already, removed consistently throughout the whole document.

- **Emails with several recipients were silently damaged during cleaning.** A `.msg` message with two or more recipients lost parts of its internal structure when saved, so the cleaned result was incomplete. The cause was a mix-up of identically named internal components that occur for every recipient. Such messages are now rebuilt completely.

- **Two of the bundled test documents could not be opened in Word and PowerPoint.** Anyone downloading the measurement corpus got "Error opening the file in Word" for `format_dokument.docx` and "The file is damaged" for `format_praesentation.pptx`. Both files were already faulty before Maskuro touched them — the cleaned version merely carried the fault forward. LibreOffice opened both without complaint, which is why nobody had noticed.

- **A custom AI on the internet is now addressed encrypted.** Anyone entering an external address for their own AI without "https://" (as it often appears on the IT department's note) previously reached it via an unencrypted connection — the unredacted text went out in plain text. Such addresses are now addressed via "https://"; a server on the local network remains reachable unchanged. If the server follows a redirect to another machine, the access key no longer travels along with it.

- **A damaged image now also loses its hidden metadata.** If an embedded image could no longer be opened fully (e.g. a truncated photo), it previously kept its EXIF and GPS data — the shooting location and photographer's name remained invisible in the result. Such images are now stripped of this data even when they can no longer be displayed at all.

- **An embedded file that could not be cleaned is now reported instead of being passed along silently.** If a presentation or workbook contained an embedded object that was nested too deeply or could not be opened, it previously remained unchanged in the result without any note — the file counted as cleaned. Such cases now appear in the warning "could NOT be checked," just like an embedded legacy format.

- **Dark lists are consistently dark and legible again.** On macOS, file lists alternated between near-black and light-gray rows; in the touch-up view, this made the same green, orange, or red review value look different depending on the row. Window, lists, font, placeholder, and selection now come from a shared light/dark palette. The color-coded hit list also no longer places zebra stripes under its colors.

- **Occupation statements with "als" were falsely redacted as a name.** A sentence like "Als Koch ist er seit vier Jahren bei uns tätig." lost the occupation, not just a name — "als" introduces a role statement just as "der" or "die" does. Genuine surnames in the same position (e.g. with a salutation before them) remain unaffected.

- **A table header could pull an item number into a monetary amount** (only with the "Also remove monetary amounts" option enabled). If a line ended in a currency ("… Einzelpreis EUR") and the next began with a number, this was falsely turned into an amount spanning the line break. The separator between currency and number now stays on the same line.

- **A short uppercase abbreviation could swallow an entire sentence fragment, or attach itself in front of a correctly recognized name.** If a line contained a two-letter capitalized word like "DI," "AG," or "KG" — everyday abbreviations, not names — the whole line was tentatively searched in lowercase, and the abbreviation occasionally dragged neighboring words (including verbs) into a single supposed name. A capitalized word now only triggers this second check from three letters onward. With somewhat longer abbreviations like "CEO" or "USB," a second error remained: the already correctly found name ("Schneider") had the preceding abbreviation dragged into the result as a prefix ("CEO Schneider"). The abbreviation now stays excluded.

- **A date of birth without a space after it remained.** If there was no gap between "geb." and the date — as is common in tightly set forms ("geb.14.03.1988") — Maskuro did not recognize the field and left the date untouched. Common short forms like "Geburtsdat." or "Geb.-Dat." are now also recognized.

- **An IBAN with slashes as separators remained.** As with phone numbers ("0664/1234567"), some templates also write the IBAN in blocks with a slash ("AT48/3200/0000/1234/5864") instead of a space or hyphen. This notation is now also recognized.

- **An Austrian social security number with a hyphen, period, or slash remained, or was mislabeled.** Only a space was previously provided for between the two number blocks; notations such as "1237-010180," "1237.010180," or "1237/010180" were not recognized (or, in the slash case, recognized under the wrong type). The check digit continues to confirm every hit, regardless of the separator.

- **A name behind "c/o" in an address was not removed at all.** "c/o Max Mustermann, Hauptstraße 5, 1010 Wien" redacted the street and city but left the name after it fully intact. The name is now recognized; "c/o" itself remains visible as an address note.

- **A credit card number grouped with periods remained.** Notations like "4111.1111.1111.1111" were not recognized; numbers separated by spaces or hyphens were unaffected. The checksum continues to confirm every hit.

- **A tax identification number grouped with hyphens remained, as did an Austrian VAT ID with a hyphen or period.** Spaces, slashes, and periods were already provided for with the tax ID, the hyphen was missing; with the VAT ID ("ATU12345678") the hyphen and period after the prefix were missing. The tax ID's check digit continues to confirm every hit.

- **A field value in quotation marks remained, for example in a JSON-like line such as "vorname": "Max".** Detection via a field label ("Vorname: …") previously required that neither the label nor the value itself be in quotation marks. Such lines are now also recognized — as are field labels with a leading YAML list bullet ("- Vorname: Max") or a tab instead of a space before the colon.

- **The email header word "Sent" was itself redacted like a name.** In a header like "Sent: Huber," it previously caught both "Sent" and the actual name; related header words like "Subject" or "Betreff" had always been unaffected. "Sent" now also remains untouched.

- A name behind the headers "Errors-To:" or "Resent-From:" remained undetected when such a line stood in plain-text copy (e.g. a forwarded message or an incident report) — unlike with "Reply-To:" or "Return-Path:," the name here was dropped entirely instead of just being imprecisely delimited. It is now found.
- One and the same file sometimes produced a different result across two cleaning runs: if two detections matched exactly the same spot with the same length and the same confidence (e.g. "Sozialversicherungsnummer 1237/010180" as AT_SVNR or as a general ID number), it was down to chance which one won — the value was removed in both cases, only the placeholder label changed. The tie is now always resolved the same way.
- A job title directly before a common noun (e.g. "Behandelnder Arzt: Dr. …" or "Zuständiger Sachbearbeiter ist …") was sometimes falsely redacted as well, as if it were itself a name. Genuine surnames next to it remain unaffected.
- A genuine surname that happens to look like an adjective (e.g. "Schöne," "Lange," "Junge") and stands immediately before another common noun (e.g. "Kontaktperson: Schöne Assistentin") had, since the last fix, remained unredacted in the text — a data leak. Now only a narrowly limited list of genuine job titles (e.g. "Behandelnder," "Zuständiger") is treated as a non-name in this pattern.
- A standalone surname at the end of a multi-line name hit that happens to look like an adjective (e.g. "Schwarz," "Kurz," "Alt," "Frisch," "Gut," "Reich") remained unrecognized before an immediately following colon — cleaning mistook it for a field label like "Telefon:". A closed list of known ambiguous surnames now protects it.
- A standalone surname that happens to be an ordinary German word ("Gross"/"Grosse," "Gut," "Kurz," "Lang"/"Lange") was previously **completely** lost — even in simple sentences like "Herr Gross unterschrieb den Vertrag." The reason lay in spaCy's own stop-word list, which contains these words; a closed list of known surnames now protects them from being discarded.
- In employment, loan, surety, trust, and insolvency contracts as well as guardianship/custodianship and expert-opinion assignments, a surname that is also an ordinary word (e.g. "Bauer") was overlooked behind labels such as "Auftraggeber:," "Auftragnehmer:," "Arbeitnehmer:," "Versicherter:," "Darlehensgeber:," "Darlehensnehmer:," "Bürge:," "Sicherungsgeber:," "Treuhänder:," "Treugeber:," "Insolvenzverwalter:," "Gutachter:," "Sachverständiger:," "Vormund:," or "Pfleger:" — sometimes only the first name remained recognized, sometimes the whole name was dropped.
- In a legal notice (Impressum), a surname that is also an ordinary word (e.g. "Bauer") was overlooked behind the labels "Geschäftsführer:," "Geschäftsführerin:," "Vertretungsberechtigt:," "Inhaber:," or "Inhaberin:" — with "Geschäftsführer:"/"Inhaber:" the whole name was dropped, with "Vertretungsberechtigt:" only the first name remained recognized.
- A contact block whose label stood alone on its own line and carried the gender-neutral colon form ("Ansprechpartner:in," name below) was **completely** overlooked — the colon was read as a field separator, "in" as a (discarded) field value, and the actual name on the next line was thus never picked up. The asterisk form ("Ansprechpartner*in") was not affected by this.
- If the name and label stood in the same gender colon form on **one** line ("Ansprechpartner:in Anna Berger"), the placeholder dragged the word "in" into the replacement instead of removing only the name — the name itself continued to be fully captured.
- A name in a table column under a person column header (e.g. "Name Vorname Geburtsdatum" over "Bauer Anna 03.05.1985," as in a payslip) was completely overlooked as soon as only a single space stood between the columns and no line started with an outline number — exactly the shape in which a genuine PDF text extract delivers such lines.
- In a chat or meeting log with speaker names before the colon (e.g. "Bauer 🙂: Ich stimme dem Vorschlag zu."), the name remained completely unrecognized as soon as a reaction symbol stood between the name and the colon and the surname was also an ordinary word ("Bauer," "Koch," "Schneider," etc.) — a whole log could end up without a single recognized speaker this way.
- The same speaker-line gap also existed with other characters between the name and the colon: a status note in parentheses ("Bauer (Vorsitz): …," "Bauer (abwesend): …"), a time in square brackets ("Bauer [14:32]: …"), and a footnote mark directly attached to the name ("Bauer*: …"). Here too the speaker remained completely unrecognized as soon as the surname was also an ordinary word.
- If a person already recognized appeared, in an attached log or protocol excerpt of the same message (e.g. a support ticket), additionally as a username in the form "firstname.lastname" — lowercase, without spaces, joined by a period — that plain-text name remained legible, even though the same name in the cover letter had already been redacted.
- The same username gap also existed with an underscore instead of a period ("firstname_lastname") — an equally common format in log and protocol excerpts.
- The username also remained legible in reverse order ("lastname.firstname" or "lastname_firstname") — some systems place the surname before the first name in the log username.
- A date of death remained unrecognized if no other data stood next to it ("Herr Bauer ist am 12.03.1985 verstorben") — there was previously no dedicated detection for this at all, and the generic date does not trigger at this standard threshold.
- A date of death also remained unrecognized when the sentence used the verb form instead of the participle ("Frau Meier verstarb am 12.03.1985," "Er starb am 12.03.1985") — only "ist … verstorben"/"ist … gestorben" previously matched.
- A wedding date remained unrecognized regardless of how it was written ("Eheschließung am 12.03.2010," "Hochzeitsdatum: 12.03.2010," "Herr und Frau Bauer heirateten am 12.03.2010") — there was previously no dedicated detection for this at all, and the generic date does not trigger at this standard threshold.

- **In the touch-up editor, a second frame over a just-inserted placeholder could leave a red character remnant**, e.g. "[G" instead of "[BEG1]" — without any warning, because the remnant no longer belonged to the confidential data (that had already been removed in the first pass) but only to the placeholder itself. The reason was the coloring: a newly inserted placeholder was written into the file character by character, even with a single-color setting — a later frame over the same spot then found no contiguous wording it could locate itself against. A single-color placeholder is now written as one piece in the stream, as automatic cleaning has always done; only a genuine gradient or rainbow text still needs individual characters. The built-in cross-check now also recognizes such a remnant even when the placeholder's exact character string no longer occurs.
- A numbered name list with a hierarchical outline number ("1.1 Max Mustermann," "1.2 Huber Franz" …) lost all names to the same brake that is actually only meant to protect genuine outlines and item lists — without a column header above the list, there was no witness that could have saved a name.
- A name in an English-language login line of a system log ("Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2") was not recognized — the German language model only found it if "invalid user" stood before it, otherwise it remained. Such log excerpts are often attached unchanged to an incident report. Names behind "for" before an IP address are now reliably recognized.
- The name of the debtor in the SEPA mandate reference of a bank statement or posting journal (e.g. "MREF+Mustermann Klaus+SVWZ+Miete August") remained unclean — no spaces, no sentence structure, only uppercase fields separated by "+," and in the order "surname firstname" common there, detection did not find it by chance either. It is now recognized.
- The street with house number in the first line of an address table (e.g. "Nachname | Vorname | Straße | PLZ | Ort") remained unclean — the language model guessed a wrong but longer place spanning several columns there, which displaced the correct, shorter address hit. It is now recognized.
- The same leak occurred with a tab instead of "|" or ";" as the column separator — there the address disappeared entirely instead of merely being partially lost. It is now recognized.
- A street with house number remained unclean when directly followed, without a space, by a postal code with a comma (e.g. "Bahnhofstrasse 12,80331 München," as in a comma-separated table column) — the comma looked like a decimal place of a quantity, and the pattern therefore did not even consider the street an address. It is now recognized.
- A street with house number remained unclean when directly followed, without a comma, by the place prefix "St." (Sankt) (e.g. "Hauptstraße 5 St. Pölten," a letterhead without a preceding postal code) — "St." looked like the unit abbreviation for "piece," and the pattern therefore did not even consider the street an address. It is now recognized.
- A door/staircase addition after a house number (e.g. "Lerchenfelder Gürtel 43/12") remained visibly unclean when directly followed by a single letter that happened to match a unit of measurement (e.g. "h" for hour) — the address was then cleaned only up to the house number without its addition, instead of matching fully or not at all.
- A subject line with a surname matching an occupation before the first name ("Betreff: Bauer Anna," "Betreff: Bauer, Anna") previously remained completely unrecognized — even in the middle of a document with a full preceding sentence. It is now recognized.
- A German tax number with a space, period, or hyphen between the blocks (e.g. "Steuernummer: 30 815 08153" or "30.815.08153") previously remained unrecognized — only the slash notation was found. It is now recognized.
- A name behind a medical field label ("Patient:," "Hausarzt:," "Behandelnder Arzt:," "Überweisender Arzt:," and their female forms) previously remained unrecognized when the surname was also an ordinary German word (e.g. "Patient: Bauer Thomas"). It is now recognized.
- A name behind the field label "Zahnarzt" on its own line (e.g. "Zahnarzt," "Huber Franz" below) previously remained unrecognized — neither first nor last name. "Zahnärztin" and the simple "Arzt" form were unaffected. It is now recognized.
- A surname behind "Herr"/"Frau," followed by a bureaucratic phrase such as "zur Kenntnisnahme," "zur Unterschrift," or "zur Weiterleitung," was previously scoped too broadly and dragged the phrase into the name hit — "Frau Petra Klein zur Vertretung in allen Angelegenheiten" was replaced as "Petra Klein zur Vertretung," leaving the rest of the sentence grammatically mangled. Genuine noble particles like "von der Leyen" or "zu Guttenberg" remain unaffected.
- The same bureaucratic-phrase over-redaction also lurked behind the name in an email "To:" header, a registration code (C.1/C.1.1/C.1.2), a driving-license code, a bracketed form field ("[Vorname]: …"), and an unpunctuated closing greeting — in all of these, "zur"/"von" & co. dragged a following phrase like "zur Unterschrift" or "zur Vertretung" into the hit, and in some cases even the bare particle word itself remained stuck in the result as a name remnant. Here too, genuine noble particles remain fully preserved.
- The registration number (Matrikelnummer) behind its label was previously not recognized at all — "Matrikelnummer 7654321" fell through detection completely, neither as an ID number nor via the language model, because the number alone carries no recognizable form.
- The same applied to the participant number — "Teilnehmernummer 4471829" fell through completely, neither as an ID number nor via the language model.
- In a résumé, the name under the section heading "Persönliche Daten" often fell through detection wholly or partly when it stood directly below, without a salutation, in the form "surname firstname."
- The same applied to the section heading "Kontaktdaten" — there the name fell through completely, not just partly.
- In a registration certificate or application list with a combined "Name, Vorname" column (registration-office notation, value e.g. "Mustermann, Max" in one cell), the name fell through detection completely when a further column, such as the date of birth, followed.
- A date of birth in the form common on ID cards and registration certificates, "Geburtsdatum/-ort: 22.07.1978 / Rostock," was not recognized — only the comma form "Geburtsdatum, Geburtsort: …" matched.
- "Bürgerservice" and "Bürgerbüro" were occasionally falsely redacted as a place, especially after an en dash used as a list separator (e.g. "Wenden Sie sich an das Bürgerservice – Bürgerbüro …").
- A labeled phone number split in the middle by a line break (e.g. from a narrow letterhead column or a PDF text extraction at the column width: "Telefon: 0176 12\n34567") was sometimes only half redacted — the rest after the line break remained legible.
- A labeled ID number (customer, member, contract number, and similar) split in the middle by a line break (e.g. "Kundennummer: K903\n944" from a narrow column) was only half redacted — the rest after the line break remained legible.
- A name with an academic title before a job title after a comma (e.g. "Dipl.-Ing. Sabine Roth, Projektleiterin") previously remained completely unprotected — the line looked like a tabular column header and was falsely discarded as factual content.
- The title "Dr.-Ing." (a common German engineering degree) before a name was not included in the masked person value and remained legible — the same hyphen pitfall as with "Dipl.-Ing."
- The titles "Dipl.-Kfm.," "Dipl.-Kffr.," and "Dipl.-Psych." (Diplom-Kaufmann/-Kauffrau/-Psychologe) before a name were not included in the masked person value and remained legible — the same hyphen pitfall as with "Dipl.-Ing." and "Dr.-Ing."
- A MAC address in Cisco notation with periods instead of colons (e.g. "aabb.ccdd.eeff," as output by switch logs and support tickets) was not recognized at all and remained legible.
- A surname behind "Familie" (e.g. "Die Familie Gruber unterschreibt den Vertrag") remained unrecognized and thus legible depending on sentence structure — even with a noble particle before it ("Familie von der Leyen").

- With a Croatian address without a separating punctuation mark between postal code+city and street+house number (e.g. "10000 Zagreb Ulica Ivana Lučića 5"), the house number remained unclean.

- With a Lithuanian contact entry labeled "Kontaktinis asmuo" (e.g. "Kontaktinis asmuo: Vilkas Jonas"), the surname remained unrecognized when it was also a common noun (Vilkas = "wolf," Vanagas = "hawk").

- A country of birth or residence without further labeling in a Danish form field (e.g. "Fødeland: Tyskland" or "Bopæl: Tyskland") was not recognized.

- A country of birth or residence without further labeling in a Romanian form field (e.g. "Țara: Germania" or "Țara de reședință: Franța") was not recognized.

- A company name under the Lithuanian field label "Darbdavys:" or "Įmonės pavadinimas:" (employer/company) was not recognized.

- A company name under the Russian field label "Работодатель:" or "Наименование организации:" (employer/company) was not recognized.

- A spelled-out date with a Romanian month name (e.g. "31 decembrie 2024") was not recognized.

- A Hungarian birth name behind the abbreviation "szül." (e.g. "Nagy Éva (szül. Kovács)") was not recognized and remained openly legible.

- A saved HTML profile page (or an email with an attached web page) could leave the legal name unclean if it appeared only in the Open Graph profile fields `profile:first_name`/`profile:last_name`/`profile:username` — these carry the name broken apart rather than descriptively like `og:title`, and are now also cleaned.

- A non-delivery notification (bounce/NDR) often carried the headers of the originally undeliverable mail (sender, recipient, subject) in its own, third attachment part — this remained completely untouched in the cleaned version. This part is now cleaned like the rest of the delivery report.

- The individually named editor of a protected region in Word (Restrict Editing → Exceptions, `w:permStart`) remained in plain text even when the same name in the running text had long since been cleaned. It is now also removed.

## 0.10.42-alpha.20260827 – August 27, 2026

### New

- **Named detection profiles make different work cases reachable with one
  click.** Under *Settings → Detection → What gets removed*, the current
  selection of categories and types can be saved and instantly reapplied via
  a dropdown. The fixed *Standard* profile matches the previous shipped
  default and cannot be deleted. A profile changes only what gets removed;
  language, output type, detection depth, and custom terms and search
  patterns remain untouched.

- **The type of result is now chosen right before cleaning.** A shared
  selector in the main window sets for the whole batch whether Maskuro
  inserts readable placeholders, redacts, or removes without replacement.
  The two separate fields for PDF and Office in the settings window are
  gone; this makes the important decision visible and keeps it from
  unintentionally diverging in mixed batches. The guided tour explains the
  new selector before the first cleaning run.

- **Themes and watermarks can now clearly mark finished PDFs on request.**
  Twelve overall looks coordinate replacement texts and redaction areas with
  each other; new among them are Pride as well as Spring, Summer, Fall, and
  Winter. *Classified File* brings a diagonal `TOP SECRET` right along with
  it. Independently of that, a free marking text or a custom image, icon, or
  SVG can be chosen with color and opacity. Imported graphics are embedded
  without their metadata and stay available if the source file is moved.
  During touch-up, Maskuro replaces its previous watermark instead of
  layering it repeatedly.
  Text watermarks are drawn as the last PDF layer with a light outline, so
  they stay visible even on dark images and dense text. The touch-up editor
  ignores Maskuro's watermark entirely and no longer offers its text as a
  redaction candidate.

- **Custom output themes can be saved and shared.** The current mix of
  replacement text, redaction, and watermark gets a name, stays in
  settings, and can be exported or imported as plaintext-free JSON. The
  black-and-white print preview warns about weak contrasts; optional
  success confetti stays purely in the interface.

- **A final export check and an explanatory review layer round off the
  rendering pass.** Before final saving, Maskuro compares every
  value-precisely known PDF spot once more in the text layer and the
  rendered pixels; warnings name only page and coordinates. In the editor,
  *Why is this covered?* shows category, detection path, and safety margin,
  never the removed plaintext, and never in the final document.

- **Redaction bars are now allowed to be pretty.** Under *Settings →
  Appearance* there are color presets, free color pickers, gradients,
  rainbow, stripes, dots, flowers, stars, hearts, paw prints, clouds,
  lightning bolts, coffee beans, ducks, suns, leaves, snowflakes, paper,
  highlighter, tape, and reproducible random patterns with an immediate
  preview. Replacement texts optionally get a color, a gradient, a rainbow,
  a pill, or a label. Category colors distinguish names, addresses,
  contacts, and medical details. PDF adopts the
  full styling; Word, PowerPoint, OpenDocument, and HTML use the chosen
  solid base color. Protection itself does not change: Maskuro removes the
  confidential content first and only then draws color or pattern onto the
  empty spot.

- **Maskuro is available for Linux again — as AppImage, DEB, RPM, and a
  portable archive.** DEB and RPM register the program entry, file
  associations, terminal command, and icon into the system; the AppImage
  runs without installation. Updates stay within the same package format
  for an existing DEB or RPM installation and otherwise prefer the AppImage.

- **The visual check no longer presents ordinary PDF text a second time as
  new findings.** The final OCR look and the secure rebuild of the visible
  pages remain fully active; by default, only areas that page text and
  single-image checking have not yet read count as a new finding source.
  This means product lines are no longer turned into new names or companies
  solely because of a differing second OCR reading. Anyone who still wants
  two independent judgments over the entire visible text turns on *Check the
  entire visible PDF page for details again* in settings.

- **PDFs can now be viewed continuously, page by page, or as a spread.**
  Three compact view icons sit at the bottom right next to "Width" and
  "Page". Continuous
  scrolls to the next page at the sheet edge; single page holds the mouse
  wheel on the current sheet; spread shows an open pair, makes the clicked
  sheet editable, and moves forward/back by a whole pair. Page thumbnails
  and the comparison loupe also now open in a noticeably narrower left base
  column, leaving more room for the working page.

- **You can now see what the AI tier did.** After every run, a line appears
  under "Details" per file — "AI tier: 12 borderline cases checked, 3
  discarded" — and if it found nothing to change, that is stated too.
  Previously, the most expensive tier stayed completely silent: whether it
  was consulted at all could not be told from the outside.

  Anyone who needs more detail turns on *Log every AI query* under
  "Settings → AI". Then the log file records size, duration, and number of
  findings for every query, plus the wait time caused by a rate limit on
  the other end. The "Show log file" button next to it opens the folder —
  it lives in the application data directory, which is hidden on Windows
  and which nobody finds on their own. The file contains only sizes, never
  text from your documents.

- **Maskuro detects when your AI service caps the number of requests.**
  Hosted services often allow only a few requests per minute — four is not
  unusual. The excess ones are not rejected but have to wait, and two
  seconds per answer becomes forty. This used to look like the model was
  slow. Maskuro now reads the limit from the service's response, no longer
  sends more queries at once than are accepted, names the limit under
  "Test connection", and factors it into the duration estimate.

- **The page view now uses your Word, Excel, and PowerPoint — and is
  roughly six times faster while doing so.** Previously it needed
  LibreOffice, which sits on very few office computers; anyone without it
  saw a button that demanded a third-party install. Now: if Microsoft
  Office is installed, it is used automatically — no setup, no download, no
  checkbox to tick. LibreOffice remains the second path and, for
  OpenDocument files, even the first; if one fails, the other is tried.

  The difference is felt above all while working: after every replacement
  the page is re-laid-out, and via Office that costs roughly half a second
  instead of three. The first view of a document still takes a few
  seconds, after which it follows your actions without waiting.

  Your own open Word is left untouched in the process: Maskuro starts its
  own, invisible session, opens the file read-only, disables macros, and
  closes everything again as soon as the touch-up window closes.
  Password-protected files are rejected instead of hanging in an invisible
  dialog.

- **First-time setup now also asks about faces, codes, and signatures — and
  loads everything missing in one go.** Alongside enhanced detection, the
  first page now has the three image toggles: blur face areas, blur bar and
  QR codes, redact handwritten signatures on PDF pages. The PDF limitation
  is shown right at the checkbox; Office files are not automatically
  searched for signatures. Below the checkboxes it states how many
  megabytes clicking "Next" will cost. Loading then happens in **one**
  window with **one** progress bar over everything together, instead of in
  several dialogs one after another; a cancel stops the whole process and
  leaves nothing half-done. Anyone who wants none of it removes the
  checkmarks — then nothing is loaded either.

- **The preview can now be thinned out by review need and collapsed by
  type.** Above the list sits a slider *Hide well-supported*: the further
  right it stands, the more it hides going from green toward red; all the
  way right, only what the program guessed on its own remains. Clicking a
  type's heading collapses it. Both are reading aids, not a selection —
  whatever is hidden or collapsed stays checked and gets replaced; how many
  values that currently amounts to is shown below the slider. On short
  lists, the slider does not appear. Switching to two columns now also
  retains the *never again* toggles.

- **The image list can now open itself before every run.** Anyone who wants
  to decide on every image individually sets the new checkbox *Decide
  individually before every run* under "Images". The list with preview then
  appears on its own when cleaning, instead of you clicking "Set
  individually…" every time; canceling it also cancels the cleaning run. If
  none of the chosen files contains an image, nothing appears. The checkbox
  is off by default.
- **Maskuro finds handwritten signatures on PDF pages and removes them from
  the pixels.** Previously the signature remained under a cleaned
  document — text recognition reads print, and what it does not read is not
  replaced. The search is a separate toggle and needs a detection model
  that is loaded on demand once.

  It finds, as measured, roughly 84 out of 100 signatures and covers about
  four fifths of them. This is a help, not a guarantee: after every run the
  report states how many were found — even when there were none, since that
  can mean either that there is none or that one was missed. On 72 real
  business pages without a signature, it did not invent one.

  A **drawn** signature is found but not removed: it consists of lines, not
  pixels, and a bar over it would only be a cover under which the lines
  remained. Such spots are counted and named so they can be redacted
  manually in the touch-up window.

  Word, Excel, PowerPoint, and OpenDocument files are not automatically
  searched for signatures. Interface, first-time setup, model download,
  command line, and manual now state this limitation explicitly.

- **The tour now also walks through the preview — the window in which you
  decide.** For the sample document it opens on its own, even if you have
  otherwise turned the preview off (your setting stays as it is). It
  explains what the colors mean, why each line poses only one question — is
  there even a person here? — and what "never again" is good for. For the
  colors, the spotlight falls on a well-supported line, usually the IBAN —
  the green example the sentence names; then on the least-supported one,
  and there you may click right in the middle of the explanation: uncheck
  it, and the value stays in the document. For a long list, the tour window
  opens larger so the explanation does not sit on top of the rows. If the
  window opens a second time, the tour also explains why — the finished page
  is read once more as an image, and this produces fragments that look like
  a name.

- **The editor opens large the first time.** Original, result, toolbar, and
  finding list sit side by side and had too little room at the previous
  default size. Anyone who shrinks the window gets its size back next time
  — nobody is overridden.

- **A double-click on a placeholder brings it back** — in Word, Excel,
  PowerPoint, OpenDocument, Text, Email, and HTML. And anyone who drags
  across several placeholders and chooses "Restore selection" brings all
  the ones inside back at once. You no longer have to hit the square
  bracket exactly. Placeholders that stand for several different values
  during anonymizing are excluded from this — they are counted and named,
  not guessed.

- **The manual has a chapter "Preview before replacing".** The window is
  on by default and is the only place where you decide — in the manual it
  previously only got a subordinate clause. It now states what a checkbox
  means (it applies to **every** matching finding, not just the one shown),
  why each row only poses one question to answer, what "never again" does
  permanently, and why the window can open a second time for a PDF. In all
  eighteen languages, and the toggle is now also listed in the settings
  list.

### Changed

- **The "Replaced Values" panel has a slider over the colors, and learning
  mode no longer lives there.** With more than eight values, the same
  slider as in the preview window sits above the list: *Hide well-supported*
  thins the display down to what really needs review. This changes nothing
  in the document, and how many rows out of how many are shown is stated
  below — search field and slider count together. The *Learning mode*
  checkbox has disappeared from the panel; it remains in the *Tools* menu
  and in the toolbar.

- **The "Replaced Values" panel now shows the same colors as the
  document.** Every row in it is shaded the same way as the spot in the
  document and the value in the preview: red means "guessed alone, worth a
  second look first", green "recognized by a named pattern". Within each
  type, the least certain sits on top — you thus work through the list from
  top to bottom and see the most important item first. Previously
  everything there was equally light and sorted alphabetically.

- **Learning mode is off by default.** After a correction in the touch-up
  window, the program previously asked on its own whether it should become
  a custom rule. This question comes in the middle of the work; anyone who
  did not ask for it experiences it as an interruption. Anyone who wants
  the rules turns on the *Learning mode* button in the toolbar — the choice
  then holds permanently, in both directions.

### Fixed

- **Exported rule files are now explicitly flagged as needing protection.**
  Custom terms and exceptions can be present in them as plaintext; the file
  can also contain the hash salt used to confirm suspected values. A
  successful export therefore now shows a warning and asks that the file be
  protected and passed on deliberately only to authorized recipients.

- **The final security check no longer holds back cleaned office files
  because of their own placeholders.** A type abbreviation like "SVNR" also
  appears inside `[SVNR1]`; before, this counted as a supposed plaintext
  remnant and the finished file was discarded. At the same time, phone
  numbers and IBANs are now also followed up where Office stores the same
  detail without visible spaces in a reference or an embedded file.

- **Word, Excel, PowerPoint, and OpenDocument no longer leave a late-
  discovered field copy standing.** When a value is first recognized in a
  side store or embedded office file, a tight follow-up pass now also
  cleans up the previously read visible and hidden copies. Already-created
  reference placeholders are not replaced a second time in the process.

- **When restoring a single Word dropdown list, a neighboring selection no
  longer comes back along without being asked.** The complete original
  paragraph is only adopted once its attributes also contain no more open
  placeholders.

- **Poorly readable scans lose fewer related pieces of information
  together.** An alternative OCR reading with salutation and two-part name
  is preserved; a street fragment, house number, and postal code/city jointly
  protect the whole address line, even when it falls apart across
  neighboring OCR blocks. Invoice and item fields as well as event lines
  next to it are not swept up in the process. A valid date that falls apart
  after "born" into several OCR words and punctuation marks is also now
  fully redacted.

- **The success confetti is now visible when the editor opens
  automatically.** The confetti now sprays directly from the *Clean* button
  instead of raining from the top window edge. The editor now waits only
  for the first, 850-millisecond burst before opening automatically;
  without confetti enabled there is still no delay.

- **The page counter and zoom bar no longer jump around when hovering over
  the view icons.** Qt redistributed the free space of the status bar
  whenever a tooltip appeared there. Both control groups now keep their
  natural width and fixed position on hover.

- **Measuring the speed of a connected AI server always failed** — on every
  server, ever since custom AI has existed. It queried with a tight
  response limit and then tried to read the answer that had been cut off
  as a result; that had to fail, and what got saved was "not measured". The
  effects showed up everywhere: the duration estimate calculated your
  server using the speed of the bundled model on an office computer, and
  settings permanently stated that the speed had not yet been measured.
  Measurement is now based on the amount the server actually produced, not
  on the content of its answer.

- **"Maximum detection (AI) — slow" was shown even when it wasn't true.**
  Label and hint described the bundled model on an office computer — "a
  language model on this machine", "up to an hour for large documents".
  Anyone with a custom AI server connected read two wrong things there:
  the computation does not run on their machine, and answers come back in
  seconds instead of hours. Both now come from the measurement. If none
  exists, the application no longer claims anything, but says that it has
  not been measured yet.

- **Restoring now also works on a dragged selection.** Anyone who dragged
  across several placeholders and wanted to press *Restore selection*
  found the button greyed out: it only turned on when the selection was
  **exactly** one placeholder — dragged across a paragraph it never is. The
  path behind it already existed, nobody could just reach it. Now it is
  enough to mark the range; all placeholders inside it come back in one
  go.

- **Restoring crashed when the comparison loupe was open.** The loupe
  remembers the spot under the mouse cursor to follow along in the
  original. On reload after an undo it returned this spot in a form the
  text view could not handle — and because such an error in the middle of
  the interface ends the program, the undo had turned into a crash. The
  loupe is open by default, so this hit the ordinary path.

- **After restoring, the view no longer jumps to the start of the
  document.** In a longer letter, the spot you were just working on was
  gone after every action. It now stays at the top, whatever paragraph was
  on top before.

- **Without LibreOffice, the page view now says where it comes from,
  instead of just being missing.** The two buttons *Page View* and
  *Redact as PDF* were locked and named in the tooltip only that no
  LibreOffice was found; there was nowhere in the application leading to
  it. A click now opens a notice with the path to the free, open-source
  LibreOffice. The manual and FAQ were wrong at this point — they announced
  a downloadable component that the application does not offer.

- **Before delivery, the finished file is searched through completely one
  last time — now also for Word, Excel, PowerPoint, LibreOffice, Email,
  HTML, and Text.** Previously only the PDF got this final look. All the
  checks before it look at a spot that someone named beforehand; a storage
  location nobody thought of is therefore also checked by nobody. At the
  end, Maskuro now bluntly searches for everything that was replaced — in
  every part of the package. If anything remains, **no** result is
  produced, and the message names the value. A file believed to be cleaned
  is worse than none at all.

- **Names sitting inside `<script>` and `<style>` are now reported.** Both
  remain untouched either way — that is program code, and a replacement in
  the middle of an identifier turns a web page into a broken web page. But
  this was not stated before, and that was the bug: a style rule
  `content: "Anna Musterfrau"` is **visibly** shown to the recipient on
  screen, and in the result it stayed there while the program reported the
  page as cleaned.

- **The add-on models can be loaded and removed again in settings.** The
  button next to "Enhanced detection" and "Maximum detection (AI)" ended
  up in the error report window when pressed, instead of fetching the
  model. The second path — the checkbox in detection that asks for the
  model on its own — was never affected by this.

- **Names hiding in a spreadsheet's sheet and range names are now
  reported.** A sheet's name sits on the tab at the bottom, a named range's
  name in the name box and in every formula using it. Neither is still
  replaced — formulas refer to them, and a workbook with broken references
  helps nobody — but it is now stated there. Previously the report only
  covered an Excel workbook's sheet name: a named range "Bezuege_Brunnthaler"
  used to slip out silently, and for a LibreOffice spreadsheet the program
  stayed silent entirely. A sheet "Notizen Ortner" thus counted as cleaned,
  and the recipient's first glance fell on the name.

  Only what genuinely points to a person is reported: a word that got
  replaced elsewhere in the same workbook anyway, or a match that picks one
  out of several words. A standalone word like "Zustaendig" or
  "Bezug_Umsatz" no longer triggers a warning — before it would have, and a
  warning that appears in every second workbook is no longer read past the
  third.

- **"Restore original" now really brings everything back.** In some
  documents, individual characters went missing afterward — "Seestraße 14"
  became "Seestraße 4", "An:" became "An", "nordlicht-planung" became
  "nordlicht planung" — and individual lines did not come back at all.
  Right there, nothing could subsequently be selected with the mouse and
  nothing redacted: the text stood on the page, but the program no longer
  knew it. Affected were narrow characters — the one, the colon, the
  hyphen — in documents that set every character individually; the sample
  document is one of them.

- **And these same documents are no longer turned into an image while
  cleaning.** Because such a character remained, the verification reported
  a leftover and the page was rasterized as a precaution. The text on it
  was then only an image: no longer searchable, no longer selectable,
  larger in the file. The sample document now stays real text on both
  pages.

- **Colored marks no longer remain over restored text.** Anyone who undid
  a replacement still saw the colored rectangle hovering over the restored
  word — claiming "something was removed here" even though the original
  stood there again.

- **A bar no longer gives away how long the word underneath it was.** When
  redacting, the bar in short lines now covers the **whole** line — address
  block, header data, narrow table cell. If the whole line does not fit
  (an ordinary three-column table row), it stays at the field; in a
  running-text line it stays word-exact, since otherwise a name in the
  middle of a sentence blacked out the whole sentence. And bars standing
  one below another are made **equal length**: in an address block each
  line has a value, and three differently long bars still gave away how
  long the lines were. They only grow as far as the paper is free — the
  bar stops before a neighboring column.

- **"Whole line" now really redacts the whole line.** Before, the bar
  ended at the next larger gap — that is, at the end of the field. In
  running text this went unnoticed, since there the field is the line; in
  header data and tables it did not: "Name: Anna Musterfrau   Department:
  Sales" produced a bar ending exactly at the last letter of the name — and
  its length was thus still on the page. The bar now runs from the first
  to the last word of the line and sweeps up neighboring columns. Anyone
  who wants to hit only the value chooses "Words"; the automatic mode
  redacts by field as before.

- **Before delivery, the finished file is searched through one final
  time.** All previous checks look at a spot that someone named
  beforehand — page text, finding rectangle, image area. But a PDF has more
  storage locations than a list can cover: annotations, form values,
  bookmarks, document info, file attachments, JavaScript. At the end,
  Maskuro therefore bluntly searches the written file for everything it
  replaced — everywhere except the page text, where the same wording is
  also allowed to legitimately appear. If anything remains there, **no**
  result is produced, and the message names the value. A document believed
  to be cleaned is worse than none at all.

- **What could not be checked no longer counts as checked.** In three ways,
  a verification failure previously looked like a clean result. A page
  whose text layer could not be read used to count as especially clean —
  after all, nothing was found there; it is now rasterized. If a page with
  a remaining finding could not be rasterized as a fallback, it used to be
  delivered silently; now the cleaning run aborts instead. And the
  cross-check in the touch-up window reported "nothing left" after its own
  error — indistinguishable in the window from everything having been
  removed; now the warning appears along with a "Rasterize page" button.

- **"Reset to default" did not actually reset most settings.** Nine of
  twenty-two checkboxes remained unchanged after the action — among them
  the preview, "Open cleaned files afterward", the touch-up window,
  immediate filing, and both update checkboxes. The saved file was cleared,
  but the window held onto the old values and wrote them back in on the
  next click. Now every checkbox comes back, and the "changed" note
  disappears with it.
- **"Automatically file a review report per cleaning run" showed as on, but
  was off.** After resetting, the checkbox stayed checked while the value
  had been cleared — no report was produced anymore, without anything
  indicating it. The same applied to the review log and the custom screen
  recording; their keyboard shortcut is now also correctly enabled or
  disabled right away on reset.

- **The bars of a line now look alike.** Previously, every finding brought
  its own bar, and its height came from the font of the matched word. In a
  line with a label and a value in different sizes, this produced a thick
  and a thin stroke with offset edges side by side, and where two findings
  were separated by only a space, a light gap remained above them. Bars on
  the same line now have the same top and bottom edge, and what is
  separated by only a space becomes one bar. What is meant to remain
  between two findings — the comma after the name, a label, an amount —
  still keeps them apart. This applies to typeset pages as well as scans.

- **The tabs under "About this program" now start at the top again.**
  Privacy, license terms, and license notices used to open in the middle
  of the text — anyone reading them first had to scroll all the way up to
  see the first line.

- **The pen no longer opens a second editor window, but brings the
  existing one forward.** Previously, a new one was created on every
  click. The window has no entry of its own in the taskbar — anyone who
  minimized it could no longer reach it and clicked again; restoring the
  main window then brought all the accumulated windows forward at once.
  Further documents now land in the tab bar of the open window, and a
  document already listed there does not get a second tab.

- **"Enhanced detection" no longer carries the "changed" note while its
  model is missing.** It ships turned on, but without the loadable model it
  cannot actually be that — in settings, the row therefore appeared as
  changed on every freshly set-up machine, even though nobody had touched
  it. Why the checkbox is off is now stated solely by its own label: "Model
  not yet loaded".

- **The intro strip explained the PDF canvas inside Office and text
  files.** It said "clicking a word redacts it" — in a Word file, a click
  redacts nothing; there you select and then press a button. It now states
  what applies in the respective view.
- **The toolbar was cluttered with labels in the text view.** "Replace
  selection", "Redact selection", "Restore selection", "Page view", and
  "Redact as PDF" now appear as icons — like their siblings in a PDF. Their
  names stay in the tooltip and menu.
- **Ctrl+mouse wheel in the comparison loupe did not move its zoom
  slider along.** The font grew larger while the slider and the percentage
  next to it kept claiming the old value.
- **The update installer did not come to the foreground** — it had to be
  clicked in the taskbar first (Windows only).
- **A year at the start of a line counted as an Austrian postal code.**
  In a résumé, "2020 Sales Strategies" became a placeholder — the whole
  line vanished. A four-digit number between 1900 and 2099 now needs a
  second address signal: the street above it, a field word before it, a
  country code, or a known place name. Address blocks have that; year
  columns do not.
- **A month-year pair counted as a phone number.** "Since 08.2010
  123-Sales GmbH" became a "phone number" — month, year, and the first
  digits of the company name after it.
- **The report said "checked via text recognition" and kept silent about
  what it does not read.** If images are kept, it now also states that
  handwritten content inside them is not found — a signature or a
  handwritten name remains. Previously this sentence only appeared for
  scanned pages; an ordinary PDF with an embedded signature got no word
  about it.
- **A placeholder on a redacted image background sat at the left edge of
  its bar.** When a value is found in an image — for instance a typed name
  next to a scanned-in signature — the image area must be redacted at full
  width. The shorter placeholder left bare black next to it, which looked
  like two separate operations. It now sits centered on the bar.

## 0.10.41-alpha.20260826 – August 26, 2026

### New

- **After the trial period, a window reminds you about the license once per
  start.** It appears five minutes after startup — not immediately, so it
  does not get in anyone's way before their first action — and waits while
  a cleaning run is in progress. From there, one path leads to purchase and
  one to entering an already-purchased key; "Later" closes it once the five
  seconds in the button have elapsed. Nothing is locked: the free tier keeps
  working as before.

- **The wait before a run in the free tier now lasts ten seconds instead of
  thirty.** It is meant to remind you of the license, not hold up the work.

- **All three license notices now look alike.** The wait, the reminder in
  the last trial days, and the notice after the trial period carry the same
  banner, the same layout, and the same buttons; the remaining time now sits
  in the button instead of as a large number next to it.

- **The finding list in the preview stands in a single column again.** It
  was two-column from nine values on; when going through it, the eye jumps
  between two tracks, and here the decision is made line by line. Anyone who
  likes the two tracks turns them back on at the bottom left of the window —
  the choice stays saved, and already-deselected values remain deselected
  when switching.

- **The AI tier is now open to anyone connecting their own AI server.**
  "Settings → AI" carries everything for it: the connection, what the AI is
  allowed to do, what it gets to do — and above that, the toggle for the
  tier along with a test, as soon as a server is entered. A language model
  computing on your own workstation remains held back: it needs several
  minutes for ten pages and is thus nothing for everyday use.

- **A custom AI can be connected.** Instead of the bundled language model, a
  larger model on another machine can answer — on an in-house server or a
  workstation with a strong graphics card. What is required is a service
  with an OpenAI-compatible interface (Ollama, LM Studio, llama.cpp-server,
  vLLM, LocalAI); it is set up under "Settings → Custom AI" together with a
  connection test that actually queries the model, measures its speed, and
  determines the possible response format. Several text passages run at the
  same time instead of one after another.

- **What the AI is allowed to do and what it gets to do is now
  configurable.** Three toggles decide borderline-case review, independent
  searching, and searching in running text; the instruction given to the
  model is shown verbatim, can be extended with in-house terms, and can be
  reset to the default with one button.

- **If the text leaves your own network in the process, a warning appears
  before every run.** Maskuro recognizes from the address whether the AI
  server is in-house and names a known provider by name. The warning can be
  turned off, but only against explicit confirmation that you are
  authorized for this transmission, and only for exactly this address.
  Nothing changes about the process itself: the transmission is still
  logged and appears in every file's review report. On the command line, it
  is not asked but halted instead — there it needs `--ki-auswaerts-erlauben`.

- **The preview before replacing is now active by default for new settings
  and also applies to explicitly cleaned clipboard content as well as text
  and images pasted into the program.** For document batches, exactly one
  preview per document with all pages still appears; the silent instant
  cleaning of short copies deliberately opens no window.

- **Findings can now be toggled on and off across the whole colored line in
  the preview.** The checkbox is now large and high-contrast; in addition, a
  status field shows "Replace" or, struck through, "Replace", so that
  selected and deselected values can be told apart instantly even against
  dark confidence colors.

- **PDFs with a visible security counter-check also now open the preview
  only once per document.** Deselected terms remain deselected for the
  later page witness; its check continues to run without interrupting the
  same run with a second dialog.

- **Replacement words look alike in the touch-up editor even on rasterized
  pages.** If the red placeholder sits in the pixels rather than the PDF
  text layer, it now still gets the same confidence-colored background area
  as an ordinary PDF text placeholder.

- **The preview before replacing already shows the review need of the
  found terms.** Every row carries the same red–orange–green color as the
  replacement later does in the editor. Within a category, low confidence
  and red false-positive candidates sit on top, strong green evidence at
  the bottom; ties stay alphabetical. If the same value comes from several
  findings, its most doubtful rating counts, to be safe. Unrated edge cases
  sit neutral yellow between red and orange.

- **The result can now be copied directly out of the touch-up editor as a
  file.** "Copy result" puts the current cleaned version onto the
  clipboard, without closing the editor and looking the file up again in
  the main list. For a not-yet-saved manual edit, the full secure save path
  runs automatically beforehand; "Copy image" remains as a separate
  function for pure pixel content.

- **Replaced words now show at a glance in the editor what should be
  checked first.** Pure language-model guessing is red, even if spaCy
  reports a flat 85 percent for it. Further unsupported model judgments
  stay at most orange; strong named evidence can turn green. Manual edits
  and older assignments without an evaluable rating stay neutral yellow.
  Automatic redaction bars also carry these colors in the editor preview
  now — including when the bar is part of a rasterized PDF page. For this,
  the assignment must match and the earlier word box must be provably
  solidly black; ordinary bold text is not colored. In the saved PDF, all
  bars remain unchanged, solidly black.

- **What gets deselected in the preview can now be remembered
  permanently.** Where you remove the checkbox, you are saying: detection
  got this wrong here. Previously this only applied to this one document.
  Now a "never again" toggle appears on the row; pressed, the value goes
  permanently into the "Never remove" list and from then on counts as
  harmless in every document. Below the list it states what becomes
  permanent before you press "Replace". The reverse deliberately does not
  exist: what has been found once, detection finds again.

- **A button resets all settings to the shipped defaults.** It sits at the
  bottom left of the settings window and asks for confirmation first. Your
  files, your license, your own detection rules, and autostart remain
  untouched; whatever your administration mandates still applies. Every
  setting that deviates from the shipped default also carries the
  "changed" note — so you can see at a glance what you have adjusted.

### Changed

- **A result is no longer filed automatically — only on save.** A run from
  the window now first writes its cleaned version to a temporary location;
  the "…_cleaned" file next to the original is only created when you press
  "Save". Until then, the result can be viewed, touched up, and copied.
  Every finished row has a save button for this, "Save all" sits below the
  list, and Ctrl+S applies in the editor. Anyone who clears the list or
  quits the program is asked; what nobody files also stays nowhere. "Show
  in folder" is locked before saving — the temporary location is not a
  destination you send someone to. The mapping file travels along when
  saving.

  In settings under "Program", "File results immediately next to the
  original" restores the previous behavior. Command line, folder watcher,
  and clipboard watcher still file immediately, unchanged — nobody sits
  there who could press save.

- **The touch-up editor's toolbar is tidied up.** Learning mode now sits at
  the right end next to the comparison loupe and "Replaced Values" — the
  three toggles that switch a mode on and off now sit together. "Apply to
  all pages" has moved next to the three redaction forms, since it only
  does anything there. "Copy result", "File – Reset", and "Apply to all
  pages" come without a label; their name still appears in the tooltip and
  menu. A divider now sits between "Replace" and "Restore original": the
  two are opposite directions and looked, side by side, like two variants
  of the same tool.

- **The "Copy result" icon now shows a document.** Two sheets with a folded
  corner and lines of text instead of two identical sheets with a small
  corner arrow. "Copy image" in turn carries the image symbol, so both can
  be told apart without a label. The "Copy" button in the results list
  shows the same document icon — it files the same file.

- **Settings are sorted and given headings.** "Detection" now has four
  sections: *What gets removed*, *How it gets replaced*, *How thoroughly it
  searches*, and *Before and after the run*. Face detection and bar/QR
  codes now sit with images, where people look for them; "Program" is split
  into *Result files*, *At startup*, *Update*, *Display*, and *Feedback to
  us*, and the result file's name suffix now sits with the result files
  instead of between language and appearance.

- **Enhanced detection is on by default**, even before its language model
  is loaded. Before, the default depended on the model being present, and a
  freshly set-up machine ran permanently on the weaker tier. The setup
  window offers the model on the first page for loading and names the
  price next to it. If it is missing, the checkbox still says so instead
  of pretending a tier is running that isn't.

- **The two term lists are now named for what they do:** "Always remove"
  instead of "Custom terms" and "Never remove" instead of "Exceptions".

- **The preview window is clearer.** From nine values on, they stand in two
  columns, the rows are flatter, and the finding count sits right behind
  the term instead of at the right edge.

- **In the touch-up editor, Replace comes before Redact** — in the toolbar,
  in the "Tools" menu, and in the right-click on the page. Replace is the
  standard case: a placeholder can be clicked and restored, a bar cannot.

- **Fewer duplicate buttons in the editor.** "Save as…" and "Copy image"
  now appear only in the File menu, with their usual keyboard shortcuts.
  One of each remains in the toolbar: Save and "Copy result" — where it
  gets saved is shown in the status bar anyway and can be changed there
  with one click.

- **The clipboard watcher is no longer offered at first start.** It
  intervenes in every copy operation on the system; anyone seeing the
  program for the first time cannot judge that. It still sits in settings,
  with the clause that belongs with it next to it there.

- **The light appearance is less glaring.** The window background used to
  come from the respective system style and was thereby the one large area
  nobody had decided on — nearly white on Windows. It is now a broken
  white, the same on every system.

- **The tour and the manual explain the colors.** What red, orange, green,
  and yellow behind a replaced word mean is now its own stop in the tour
  and a paragraph in the manual — in all language editions.

### Fixed

- **The manual and FAQ showed placeholders that no longer exist.** Since
  the switch to the short form, Maskuro writes `[NAM1]`; the help still
  said `[NAME1]`, and the sentence "The default is `[NAME1]`" was thus
  simply wrong. In the seventeen translated editions, the **German** tag
  additionally appeared instead of the language's own — a Spanish reader
  saw `[NAME1]` where their program writes `[NOMB1]`. The same for the
  result file suffix: all editions promised `_cleaned` there, while the
  program creates `_limpiado`, `_nettoyé`, or `_除去済み`. Also affected was
  the numberless form (when anonymizing, everything is called `[NAM]`, not
  `[NAME]`) and the identifier derived from the value when hashing.

- **The preview window now interrupts only once per document — and a
  second time only when something genuinely new comes up.** A PDF is read
  from two sides: once from the content stream, and last from the
  rendered, visible page. Previously each of the two asked on its own. Now:
  what you decided in the first window still applies, and values that
  already stood there do not come back. If the visual check of the
  finished pages instead finds something that was nowhere before, you get
  it presented once more — alone, without the already-decided values.

- **The preview window now says what to decide by.** Instead of "Uncheck =
  the value stays" — which says what the checkbox *does*, but not when to
  remove it — it now says: uncheck it wherever no personal detail is
  present; there detection got it wrong. In addition, each window now
  names the check pass its values came from.

- **Placeholders look alike throughout the document.** On pages that are
  rebuilt as image pages in the OCR path, visible placeholders used to be
  set in a typewriter font — "[PLZ4]" then stood wide and serifed next to
  a narrow "[NAM1]" on the same page. They now carry the same sans-serif
  font as everywhere else and are no longer set wider than planned when
  fitting. The invisible search layer keeps its own font — it needs
  reliable measurements, not looks.

- **No more duplicate dividers in the editor's toolbar.** Where a whole
  tool group is dropped for the open file type — in a PDF, for instance,
  page view and rendering — both dividers around the gap used to remain.

- **Restoring no longer occasionally leaves behind just a white spot.** An
  original text already restored exactly is no longer painted white by the
  wide, merged box of its removed placeholder. For mixed text and image
  restores, text is now only inserted invisibly when the page image
  visibly already carries exactly this original state. This applies to
  frames, the finding panel, and PDF attachments.

- **"Restore original" no longer needlessly offers to rasterize the
  page.** The strict leftover-text check remains active during redacting
  and replacing. It is skipped during restoring: there, original content
  is deliberately being brought back, and unchanged neighboring words in
  the expanded restore frame were not a cleaning error but a false alarm.

- **The tour through the editor now explains "Replace" and "Restore
  original" as their own steps.** Both tools are highlighted directly in
  the toolbar and describe that a dragged frame inserts a placeholder, or
  respectively restores the original content of that spot from the source
  file.

- **Country-specific placeholders now also stay at no more than four
  letters.** These types were previously missing from the central
  abbreviation catalog and could therefore still appear spelled out, for
  instance `[UMSATZSTEUER_ID1]`. New runs now write `[UID1]` for it; all
  automatically detected German and English types remain unambiguous in
  the process. Even self-computed abbreviations of other interface
  languages no longer grow past four characters when names collide. Custom
  rule labels remain named exactly as entered.

- **Replacing now uses the whole actually free line space before it
  redacts.** The previous rigid limit at triple the original word width
  produced bars even in largely empty form fields. Findings from the
  visible OCR counter-check also now get a readable placeholder when PDF
  text is present; only pure image, annotation, and vector content, the
  chosen redaction mode, and genuine tight spots that don't even fit a
  unique short form stay black.

- **An already visible placeholder is no longer written over a second time
  in red during the security rasterization.** Rasterization now takes over
  the existing replacement from the page image and only adds an invisible
  search copy. If a security bar must cover exactly this spot, the whole
  actual placeholder box is renewed instead of just its shorter original
  anchor.

- **"Restore original" now only highlights safe targets within the dragged
  frame.** Every replaced term inside it now lights up individually and
  exactly; unchanged running text is left untouched. Genuine vector
  redaction bars are also highlighted individually if original text sits
  beneath their black PDF area. On rasterized pages, the preview
  deliberately does without a supposed bar area: the earlier pixel search
  used to join letters, underlines, and table lines there into large red
  areas at the wrong spots. Restoration itself is unaffected by this.

- **When restoring on rasterized pages, the text now comes back.** Until
  now, an empty spot with colored rectangles over it remained there. The
  restored text stood in the document but was painted over by the white
  background of a placeholder drawn later in the page layering.

- **The review colors no longer stack multiple times on top of each
  other.** The same spot used to be colored once per mapping entry — on a
  page with five real findings, each five times overpainted, until the
  pale mark became a solid block. And they no longer appear on words that
  were not replaced at all: if the original value still stands on the
  page, there is no longer a mark there either.

## 0.10.40-beta.1 – August 24, 2026

### Fixed

- **Redaction bars in the editor now have a safety margin.** Word, line, and free-form frames also cover overhanging glyphs and anti-aliased edge pixels; a render check additionally ensures that neither visible remnants nor readable original text remain.

- **Replacement texts stay legible and uniformly short.** New names, addresses, and free terms now appear, for example, as `[NAM1]`, `[ADR2]`, and `[BEG3]`. The fixed lower limit is 4.5 points; when space is tight, the text is shortened first and the usable running space is expanded. Old mappings with long placeholders remain legible and restorable.

- **Multi-word replacements from the hit panel are now safeguarded against duplicate markers and original remnants.** The regression holds with and without numbered placeholders; exactly one shared mapping remains per hit location.

- **Restored clipboard content on macOS is not immediately cleaned again.** Even when the system signature only changes with a delay after writing, Maskuro reliably recognizes its own content.

### New

- **The editor can fully reset a file to the freshly cleaned starting version.** "File – Reset" discards, after a confirmation, all touch-ups of the current tab including the replacement list and counters. The command is disabled without changes and can itself be undone with "Undo."

- **Shifted dates now reliably keep their chronology across several files.** The shared offset is now permanently anchored in the rules as soon as the strategy is turned on; in addition, the offset can no longer be zero days and thereby unnoticeably leave the real date standing.

- **Manual PDF work now covers the full professional redaction workflow.** Individual terms, lists, and regular patterns can be searched and safely redacted within the open PDF or across all PDFs in a folder; whole pages and page ranges are directly selectable. Color, neutral white area, overlay text, font, alignment, and repetition have a preview; reusable codes can be managed as well as imported and exported. PDF cleaning removes, as chosen, either all hidden content via a full rebuild or selected data classes. The safest choice is clearly recommended, invalid search patterns are explained, and folder runs write only result copies.

- **Voluntary usage statistics now show installations and version changes.** For this, Maskuro generates a random, locally stored installation ID. It contains no device, user, or license data; the server stores only its SHA-256 value. The statistics remain fully switchable off in settings.

- **The guided tour is now a guided exercise through both windows.** It places the fictional practice document itself into the list, explains the path to cleaning, and automatically continues in the editor after the run. Anyone who aborts the tour also ends this continuation.

- **Companies from fifteen further legal jurisdictions are now recognized.** Anyone cleaning documents from the Baltics, Belgium, Scandinavia, Czechia, Poland, Southeast Europe, Singapore, Brazil, or Mexico no longer loses company names because their legal form was unknown — newly included are, among others, OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s., S.K.A., Pte. Ltd. as well as S.A. de C.V. and S. de R.L.

### Changed

- **The editor toolbars now use their space more purposefully.** Unambiguous standard icons and directly recognizable tool shapes appear in the toolbar without repeating text; ambiguous actions keep their name. Under "View," "Show tool labels" can be turned off to reduce both toolbars fully to icons. Tooltips and menus remain fully labeled throughout; the choice is remembered.

- **Learning mode is now permanently visible in the toolbar.** It can be turned on and off directly there, even when the panel of replaced values is closed. Toolbar, Tools menu, and the previous checkbox in the panel always show the same state.

- **"Reset" on the comparison magnifier now only resets its zoom.** The button restores the default of 125 percent without docking the magnifier, moving it, or changing its window size. "Reset view" remains responsible for the overall layout.

- **Errors and feature requests can now also be reported via the Help button.** "Report a bug …" and "Suggest a feature …" now appear there just as in the classic Help menu; both paths open the existing secure bug report or the public feature request list, respectively.

- **The taskbar menu is shorter and more clearly organized.** The two commands with a global keyboard shortcut — clipboard cleaning and screenshot — now stand directly one below the other with a shared shortcut column on the right. "Restore last original content" is dropped there; the more understandable restore button remains available in the main window.

- **Legal pages are directly reachable under "Help → Legal."** The submenu leads to license terms, privacy policy, legal notice, and terms and conditions on maskuro.com. Withdrawal notices remain with the purchase on the website.

- **Manually redacted PDFs are fully rebuilt when saving.** What remains visible are the pages and their newly read search layer; metadata, file attachments, bookmarks, comments, form values, hidden layers, search indexes, scripts, cropped content, and content hidden inside other objects are not carried over into the output file. Text and vector graphics then consist of pixels — that is the price of a provable boundary against the foreign PDF object tree.

- **Ctrl+Shift+B now takes a screenshot with Maskuro by default on all systems.** The Print Screen key and combinations with it remain possible as a custom assignment. In the taskbar icon's menu, the global keyboard shortcuts now appear to the right of the corresponding commands. Custom saved assignments are preserved.

- **The editor now starts with pages and the comparison magnifier on the left.** The page panel sits on top, the opened original magnifier directly below it; the replaced values remain on the right. A deliberately saved custom arrangement still takes precedence.

- **The practice document no longer sits permanently in the main window.** It is part of the guided exercise and remains additionally reachable under "Help."

- **The first launch leads directly into the practical exercise.** The illustrated quick guide is no longer offered as a second, content-duplicate entry path; it remains reachable at any time under "Help → Quick guide."

- **The idle taskbar icon stays in full color.** It now shows the same bold Maskuro shield as active clipboard mode; only with active monitoring does the green indicator dot get added.

- **The practice document stays within Maskuro.** The entry button creates the fictional PDF and inserts it directly into the file list, but no longer starts an additional PDF viewer.

- **Search in the touch-up window stays smooth while typing.** The space for the hit counter is now reserved right when opening; its first text no longer changes the canvas and no longer triggers a new PDF raster run.

- **Manufacturer names in make specifications remain visible.** An entry like "Fabrikat: TRILUX oder gleichwertig" describes the required item and is no longer redacted as a company merely because of this label. Supplier, company, and manufacturer fields remain unaffected by this.

- **Corpus measurements now count over-redacted hits as false positives.** When Maskuro removes the expected name but drags a sentence fragment along with it, the false-positive count now rises. The report additionally lists such overreaches separately; earlier false-positive counts are therefore not directly comparable.

### Fixed

- **Technical and official terms from German original documents are less often redacted as names or places.** Vehicle equipment, item and total lines, procurement and privacy terms, legal references, and file names of public materials are now only braked with their documented factual context. An umlaut lost during text recognition in "Marz 2026" remains protected as a month; "Marz" without a date context can still be a genuine name or place.

- **"Restore original" now immediately takes the full required width.** If the frame only hits one word of an assigned value, Maskuro now independently expands it, based on the mapping and the original line, to the whole item — for example from "Planungs" to "Nordlicht Planungs GmbH." The subsequently graspable frame likewise shows the actually restored total width.

- **"Restore original" now shows black bars as an unambiguous target.** When hovering or dragging, the whole recognized bar now lights up red with a bright contrast outline, instead of just a barely attributable text box next to it. This also applies to rasterized pages, where the bar now consists only of pixels.

- **The editor tour no longer skips stations when panels were closed.** For the tour, Maskuro now temporarily opens and arranges the page panel, comparison magnifier, and replaced values itself. After "Done" or an abort, the personal arrangement returns. If a tool is fundamentally unavailable for a document type, its explanation is now kept as a text stop instead of unnoticeably disappearing.

- **"Replace" remains visible even during the PDF safety fallback.** When Maskuro had to rebuild a page as an image because of a remaining character or a damaged text run, the correct replacements previously stood only invisibly in the search layer, and black bars lay on the page. The actually set replacement values are now kept visibly red and searchable across all raster and OCR rebuilds.

- **The notices above the cleaned version remain legible in dark appearance.** The version heading, control line, and introduction now take their font color directly from the actually displayed Qt window.

- **Redaction frames sit above the text again on rasterized PDF pages.** The invisible word boxes were, depending on the original font, narrower than the visible letters. This created gaps in the bar, or the last letter remained legible. The boxes now keep the width, height, and direction of the visible word.

- **"What's new" starts at the top again.** The changelog dialog now explicitly places the text cursor and scrollbar at the beginning after the finished window build, instead of starting mid-way through the new items depending on the Qt state.

- **Closing during scan word recognition now stays silent.** An OCR background run just finishing no longer sends into an already-closed touch-up window.

- **Relative time expressions are no longer mistaken for names.** Fixed phrases like "heute" (today), "gestern" (yesterday), "morgen" (tomorrow), and "nächste Woche" (next week) are now known to Maskuro from the official calendar data of the respective document language.

- **Exiting during the first model load cleans up properly.** Anyone who closes Maskuro or the touch-up window immediately after opening no longer leaves a thread still working in native language recognition behind during process teardown. This prevents the sporadic crash report on exit; an already running load is finished off in an orderly way.

- **Delayed startup dialogs no longer appear after exiting.** Anyone who closes the main window shortly after startup no longer subsequently gets the question about the best detection tier, the changelog, or the introduction shown invisibly or belatedly afterward.

- **HTML and email keep their line endings.** On Windows, HTML serialization mixed LF and CRLF after cleaning and reversal. Content and formatting were correct, but the file was no longer byte-identical. HTML files and MIME messages now again take on their source's notation.

- **Company names with a preposition remain complete.** Behind a preposition, Maskuro cut off names like "Gesellschaft für Systemtechnik mbH" or "Bank für Arbeit und Wirtschaft AG" at the word "für." The whole company name is now recognized; genuine introductory sentence fragments like "Wir sind bei Alpha GmbH versichert" remain visible.

- **Chinese company names remain complete before their legal form.** A brand component that could be read as a verb could discard the entire name despite the unambiguous addition "有限公司." In scripts without upper/lowercase distinction, the official legal-form anchor now takes precedence over this unreliable part-of-speech boundary.

- **PDF pages were needlessly turned into images.** With multi-page PDFs whose pages share a font list — which common generators create this way — all pages after the first lost the reference to their fonts. The consequence was twofold: umlauts were no longer searchable in the result ("Auftragsbestätigung" could not be found), and the cross-check then considered letters overlooked that had never stood on the page — it rasterized intact text pages into images, making them no longer searchable, no longer copyable, and noticeably larger. In the test set, this affected four of seventeen pages.
- **A comma alone no longer triggers rasterization.** If a hit area ends at the word, the punctuation mark next to it still narrowly belongs inside it. But a comma or a period is not an overlooked item, and rasterization costs the whole page. Letters and digits remain, unchanged, a reason to re-sharpen.

## 0.10.38-alpha.20260824 – August 24, 2026

### New

- **Company names without a legal form are now recognized when their label names them.** "Lieferant: Kranzbichler Handels GmbH" was always already removed — the legal form gives the company away. "Lieferant: Dehner Märkte" remained, and in quotes, tenders, and orders the supplier mostly stands exactly like that. The same applies to "Firma:," "Hersteller:," "Fabrikat:," "Arbeitgeber:" and their equivalents in eight further languages, and also when the label stands alone on its own line with the name below it.

  What is *not* a company behind the label remains untouched: "Lieferant: siehe Anlage" is not redacted — otherwise it would read "Lieferant: [ORGA1]," and that would claim a name that never existed. Labels behind which a person just as often stands ("Kunde:," "Auftraggeber:") are deliberately not included.

- **An inserted image can now also be edited.** In the "Clean image" window, next to "Copy result" there is now a button *Edit in editor*: the image is cleaned and then opened for touch-up redaction, labeling, and highlighting — the same path a screenshot takes.

- **Numbers behind their label are now also found when they name a business partner.** Previously, customer, contract, and personnel numbers fell through; now also debtor, creditor, and supplier numbers, the Austrian employer number, the ANKÖ registration, and a manufacturer's WEEE, EAR, and EPR numbers — in German as well as English. Maskuro also now understands the notation of set quote headers with a space before the colon ("Kunden-Nr : K903944"). Item, order, contract, quote, and invoice numbers remain untouched, as before: they name the transaction or the goods, not the person. Anyone who wants to remove them anyway can save them as a custom search pattern.

- **You can now see how long a file took.** In the finished-file row, the duration appears next to the recognized language ("done · German · 2.4 s"), the summary shows it for the whole run, the statistics panel shows the total — and the verification report carries it as its own field. With several files, the row reveals which one took the time.

- **Scripts not supported by the system OCR can now be read as a fallback with an available language file.** Previously: if the system's own text recognition did not master a script (on the Mac, for example, Devanagari), the result showed "Image(s) were NOT checked," and the data in the image remained. Now the bundled text recognition steps in if the matching language file is present. Because an image read this way is less certain than a regularly checked one, this is stated in the result: "read via fallback method — please review." Measured against a historical interim state of the Hindi test: **ten more items found and four fewer false positives** (64% → 73%). The current final value stands further above and should not be confused with this.

- **Text recognition now asks for the correct language.** For all document languages except German and English, the English detection model was previously used, even when the matching language file was available. On Windows this affected every language — Greek, Japanese, or Hindi were read there with the English model.

- **A setup wizard on the very first start.** (Anyone who has already used Maskuro does not get it — "first start" means first start, not first start after this update.) Three questions instead of six pictures: the language of your documents, whether text in images is also read, and how you want to reach Maskuro in everyday use. At the end, the three paths remain — practice document, guided tour, or the illustrated quick guide. Everything can be skipped, and "Help → Go through setup again" brings it back.

- **F1 opens the manual at the matching chapter.** In the main window, in settings (there depending on the page), in the review window, and in language management; in the touch-up window via Shift+F1, because F1 there has always shown the keyboard shortcuts. Previously, help always started at the top, among 25 chapters.

- **New first manual chapter: "Get started in three minutes."** Four steps, that is all a document needs — in all 18 language versions.

- **A guided tour through the window.** "Help → Guided tour of the window" highlights one control after another and writes a sentence next to it — eight stations in the main window, seven in the touch-up window. Unlike the illustrated quick guide, it explains the window you are actually sitting in front of. Cancel any time with Esc.

- **A practice document for risk-free trying out.** Below the drop area there is now "Open practice document" (also in the Help menu). It creates a fictional sheet — name, address, phone number, IBAN, social security number — and the sheet itself explains what you can do with it and what you will see afterward. Not a single word belongs to a real person; the first document you send through Maskuro therefore doesn't have to be a real one.

- **"Just check …" now stands next to "Clean."** It shows where personal data is located — file, type, and count — without changing or writing anything. Anyone who has dropped a document can thus check first, before cleaning. Previously this path only existed in the File menu under "Review folder …" and worked across an entire folder rather than the dropped files.

- **If nothing was found, it now says what could be the reason.** For example: the file contains images, but "Also check text in images" is off. Or: the configured language does not match the one in the document. And if none of that applies, Maskuro says so too.

- **The touch-up window greets you the first time with three sentences:** clicking redacts a word, dragging a region, replaced values appear on the right. "Got it" removes the notice permanently; "Help → Show introduction again" brings it back.

- **Words can now also be clicked on scanned pages.** Previously, words could only be clicked where the PDF carries a text layer — with a scan that didn't work, and within the same document it could vary from page to page. Such pages are now read once by text recognition; afterward you click words like anywhere else. The status line says what is currently happening.

- **The page panel is a full surface again.** It used to stop in the middle of its column: title bar cut off, next to it a strip in a different color, and the current page was only identifiable by a colored box behind its number. It now fills its column, can be dragged wider, and the current page is highlighted as a whole tile — with an unaltered page preview inside.

- **Replaced spots glow pale yellow.** In the page view, this makes it visible at a glance where something was replaced — the same color the comparison magnifier uses over the original. The red frame when pointing with the mouse remains unchanged.

- **"Reset view" in the touch-up window** (menu "View"). Anyone who has moved, detached, or closed the page panel or hit list can use this to put everything back where it was on first launch.

### Changed

- **The placeholders are shorter.** `[SOZIALVERSICHERUNGSNR_1]` becomes `[SVNR1]`, `[ORGANISATION_1]` becomes `[ORGA1]`, `[EMAIL_1]` becomes `[MAIL1]`. The reason is not aesthetics: a placeholder longer than the value it replaces pushes the line apart and no longer fits at all into a narrow table column — previously a black bar remained there, and that no longer tells anyone that something used to stand at that spot. Where a common abbreviation exists, it is used (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Results from earlier runs remain usable: the old notation continues to be recognized, and mapping files from yesterday work unchanged.

- **The program icon now looks the same everywhere.** In the Mac menu bar, a single-color shield previously appeared that the system itself colored black or white; in the Windows taskbar, a green or gray one. Every bar now carries the same blue Maskuro shield. How to tell whether the clipboard is being monitored remains just as clear: if monitoring is running, a green dot sits on the shield; when idle, the same shield appears pale. Even at the smallest sizes, both redaction bars now appear in the shield — previously the taskbar only showed one there.

- **Faces are now recognized with a model whose training images were created with consent.** MediaPipe BlazeFace (Apache-2.0) is now shipped; the previous detector remains built in and switchable, but is no longer bundled, because its training provenance is not conclusively established. Nothing changes for detection: across 324 portraits and 143 images without a face, the new version finds the same amount with equally few misses and takes a third of the time.

- **OCR is the safety anchor for the strongest PDF guarantee.** The normal PDF run uses it and produces the full minimal rebuild. Anyone who explicitly disables OCR gets the more compatible object path; the interface, the final message, and the manual now explicitly say that this path does not offer the same architecture against unknown hidden PDF channels.

- **The sales gate now also locks the previously bundled YuNet model.** The MIT license of the exact weights remains documented but does not, given the publicly visible training-data chain via WIDER FACE, suffice as a conservative product release. Before sale, a written clarification or the exchange for a model with a solid commercial data and weight chain is required.

- **Company and organization names are now removed by default.** Previously they remained unless explicitly requested. That was the wrong default for a business letter: anyone forwarding a quote does not want the client named in it. "Kranzbichler Handels GmbH," "Institut für Bauphysik," and similar are therefore treated like a name. Anyone who needs it differently turns it off in the window; on the command line the switch is now called `--ohne-organisationen`. The old `--mit-organisationen` continues to be accepted and now does nothing, so existing scripts and shortcuts do not break. Dates and monetary amounts remain excluded as before.

- **Redaction now has three forms instead of two checkboxes.** "Words," "Whole line," and "Free frame" now stand as a single choice side by side — exactly one always applies. Previously "Text lines" and "Whole line" were two independent switches that could both be pressed, and the free frame was not a button at all, but the switched-off state of the first one. The three now appear visibly with their tool and are grayed out while a different tool is selected.

### Improved

- **The first document finishes about one second faster.** Before cleaning begins, Maskuro determines the document's language — and previously fetched the word lists of all 48 languages for this via a path that loaded far more than just the words. That was roughly half the wait time until the first result. Detection itself is unchanged: it sees the same words as before, just faster. Every further document was unaffected by this anyway.

- **Documents with very long paragraphs are checked faster.** For a paragraph without a line break, Maskuro previously re-read it in full for every hit found; now once is enough. The longer the paragraph, the bigger the difference — measured at roughly a seventh less computing time. Nothing changes in the result.

### Fixed

- **Half the sentence often disappeared along with a company.** If a company name stood in running text — "Information über die Gottwald GmbH & Co KG," "… (AGB) der Musterbetriebe GmbH" — not only was the name redacted, but everything before it back to the start of the sentence. This made the text illegible and looked as if redaction had happened at random. Company names that themselves carry a "für" or "und" ("Bank für Arbeit und Wirtschaft AG") remain unaffected and fully intact.

- **Company names remained in letterheads even though they were removed in the text.** In a quote, the company's registered seat still stood legibly in the letterhead image — the same place Maskuro had redacted in the running text; in the searchable text of the result it even remained invisibly present. What was once removed is now also removed wherever it exists only as an image. This also works for logos and word marks drawn as graphics.

- **macOS asked for screen recording permission on every start**, even when it had long since been granted. The notice at startup tried out a capture, and that is exactly what brings up the system dialog. Now only Maskuro itself asks at startup, and only once; the system only asks once you actually take a screenshot.

- **Technical factual terms were mistaken for places and companies.** "Einspeisepunkt," "Flachdach," "Verteileranlage," "Meldersockel," and dozens of similar words disappeared from quotes and bills of quantities. Maskuro now recognizes them by their base word: what ends in "-anlage," "-punkt," or "-kanal" is a thing. Place names like Berlin, Melk, or Wieselburg have no such base word and remain unaffected — as do addresses like "Der Graben" or "Alter Markt."

- **Japanese, Korean, Chinese, Thai, and Gujarati documents could crash the program.** If a document in one of these five languages contained an internet address without "https://" before it, cleaning aborted with an internal error — with the window open, the rest of the work was lost too. All forty-eight selectable document languages now run through; if the frequency dictionary is missing for a language, the item is left standing in doubt instead of disappearing.

- **Field labels only protected in German and English.** "Reference" remained, the Italian "Riferimento" and the Portuguese "Referência" were removed as a place — the same field name, the same line, a different result. Anyone not working in English was thus worse off. Maskuro now knows the same field names in all eleven maintained languages.

- **"Restore original" on scanned pages restored too much.** A frame over a redacted line of an address block re-exposed the **whole block** — and the page remained torn up: bar remnants still stood, with individual word ends sticking out of them. The reason was that stacked bars on a rasterized page touch each other and were therefore treated as a single area. Exactly the line the frame points to is now restored; the neighboring lines remain redacted, and the bar of the hit line disappears entirely.

- **Quantities in item lists were mistaken for addresses.** In a line like "1.4  Kabelgraben  100,00  m," "Kabelgraben 100" was replaced as a street with a house number. Such lines now remain; genuine addresses — including "Hauptplatz 1, 3250 Wieselburg" — continue to be recognized unchanged.

- **Half the sentence disappeared before a company name.** "Vertrag zwischen der Firma Gottwald GmbH & Co KG und dem Auftraggeber." became "[ORGANISATION_1] und dem Auftraggeber." — the start of the sentence was gone, and with it the clue as to what it was about. Now only the company name itself is removed. Where the generic word belongs to the name ("Deutsche Bank AG," "Universität Wien"), everything stays as before.

- **In a meeting record, speakers whose name is also an occupation remained.** "Bauer:," "Koch:," "Weber:" before a floor statement were overlooked, "Gruber:" next to it was not — Maskuro previously needed at least one recognized name in the document to read the lines as floor statements at all. If the document carries a heading like "Ergebnisprotokoll" or "Niederschrift," this is now enough on its own. Note lines ("Achtung: …," "Hinweis: …") remain untouched.

- **A field label disappeared along with its value.** "Projekt: Sanierung und Erweiterung Gemeindezentrum" became a single placeholder — the word "Projekt:" was gone too, and with it the clue as to what had stood at that spot. Labels now remain. Where a label belongs to the item and carries its meaning ("Durchwahl 214"), nothing changes.

- **Maximum detection did not clear away factual terms.** "Flachdach," "Einspeisepunkt," "Elektrotechnik," and similar technical words were replaced as a place or company even with the AI tier turned on — the AI was never actually given exactly these hits for judgment. It now reviews them too: across a corpus of tender and contract texts, this eliminates all 27 misses without a single genuine item remaining. Names, companies, and places continue to be recognized unchanged.

- **Generic words for facility types were mistaken for organizations.** In a contract text, "Hochschulen und Universitäten," "Staatliche und private Schulen," "Akademische Lehrkrankenhäuser," "Bildungseinrichtung," and "Zulieferfirmen" disappeared — words that don't name a specific institution but a type of institution. They now remain. If a proper noun precedes them ("EU-Kommission"), replacement still occurs, and company names are not covered by this rule at all.

- **Names in lists only fell if they were common.** In a participant or attendance list under a column header "Name," "Anna Huber" and "Thomas Müller" were removed, but "Wójcik Aleksandra" or "Kücükgöl Sinan" were not — the same line, the same structure. Anyone with a rarer name was thus less protected. The column header now decides: what stands under "Name" is a name. An item list with a factual column header remains untouched.

- **A phone number behind "Durchwahl" was cut in half.** "Durchwahl 0732 771190" became "[DURCHWAHL_1] 771190" — the second half of the number remained legible. Now the full number falls entirely, and the label remains. A genuine extension ("Durchwahl 214") continues to be replaced together with its label as before.

- **Some PDFs could no longer be cleaned at all.** If a color profile or the metadata in an image could not be provably removed, the run aborted without a result — this affected ordinary business documents such as terms-and-conditions pages, requirement specifications, and tenders. Such files are now cleaned, and a warning names the spots that remained open: they may carry a device, generator, or capture ID. The original remains unchanged as always.

- **Contract roles were mistaken for persons.** "Bieter," "Verbraucher," "Mieter," "Käufer," "Auftraggebers," and around forty other role words were replaced wherever they stood without an article — in contract headings, table columns, and signature lines. A contract text without a single item of personal data was thereby rendered partly illegible. These words now remain. If a person clue stands next to it — a salutation, a first name, a field word like "Ansprechpartner" — replacement still occurs: "Herr Bieter" and "Frau Käufer" are names. Common surnames that are also occupations (Bauer, Richter, Koch) are not covered by this rule at all.

- **An abbreviated street was overlooked when the house number stuck directly to the period.** "Schlesischestr.31" did not count as an address — and because the postal code next to it derives its hold from the address hit, it too remained. In the result, the address made of street and postal code could be reassembled — and only on some pages of the same document. Both now fall together. Factual designations with an attached number ("Kabelrinne200") remain untouched.

- **An address across two lines was merged into a single placeholder.** If a postal code stood above the street in an address block, Maskuro combined both lines into one hit: in the result the line break disappeared, and the postal code remained legible before it. Now each line is found and replaced separately, and the layout is preserved. The same cause occasionally also pulled the surname from the line above into the address.

- **The maximum PDF path no longer takes over original objects.** With text recognition enabled, Maskuro now fully rebuilds every page from the visible PDFium image. Only this image page and a newly generated search layer limited to the OCR text go into the new minimal file — not the foreign object tree with comments, attachments, actions, layers, metadata, color profiles, or private keys. This also applies to content in annotation appearances, patterns, Type 3 fonts, form objects, and soft masks. The source file remains untouched.

- **Faces and codes in nested PDF graphics were overlooked.** Both detectors now additionally see the fully rendered page image. This means portraits and QR/bar codes in annotations, patterns, Type 3 glyphs, and transparency masks now also reach the detectors; recognized areas are — when enabled — made unrecognizable before the minimal rebuild. Detection itself remains fallible.

- **A missing OCR engine ended in an internal error for PDFs.** The maximum run now aborts in a controlled way and without a target file, instead of outputting an incomplete or unchecked file.

- **Several genuine contact and business values fell through while factual text was replaced.** Name fields across line breaks, bank and company names, legal forms, labeled ID numbers, dates of birth, and phone/URL/IBAN boundaries are checked more narrowly. At the same time, countries in factual text, role and generic words, item/standard codes, number columns, and ordinary abbreviations remain untouched more often.

- **Mixed and rotated OCR lines were read incorrectly.** Uncertain vertical words are now re-read locally upright; technical Latin values in non-Latin text get an independent English witness. A standalone uncertain single digit is only corrected if two adjacent digit runs agree. Polish legal forms in the OCR form "sp. z 0.0." are read as "sp. z o.o." in the closed context.

- **Image measurement could overlook partially visible remaining values.** It now checks overlapping local crops, distinguishes white placeholder text on a black bar from original glyphs, and transfers raw image boxes also to rotated, freshly rendered minimal PDFs. The fixed synthetic main corpus thus reaches 1,392/1,392 removed target items with 0 false positives and 0 processing errors. This is a corpus result, not a general 100% promise.

- **Non-commercial language models are no longer offered.** The six Italian and Greek spaCy variants under CC BY-NC-SA 3.0 have been removed from the catalog, download, and loading path; already-present model folders are also ignored. Both languages now use the MIT-licensed multilingual model instead.

- **The name under "Ansprechpartner" was only half removed.** If the label stood alone on a line with "Nachname Vorname" below it, the first name remained whenever it was also an ordinary word — "Mayer Roman" became "[NAME_1] Roman." Such lines are now taken in full. A department at the same spot ("Technischer Innendienst") continues to remain untouched. Also fixed along the way: "Ansprechpartner" did not count as a name field at all, even though "Kontaktperson" always has.

- **The company name without a legal form remained when an industry word stood in between.** "Kranzbichler Handels GmbH" was removed, the bare "Kranzbichler" three paragraphs later was not — with "Kranzbichler GmbH" on the other hand it was. Both now match. Ordinary words are exempt from this: "Deutsche Bank AG" does not turn "deutsche" in the text into a company.

- **The same value was called a name in one place and a place in another within the same document.** "Anna Musterfrau … Musterfrau" produced "[NAME_1]" and "[ORT_1]" — at the second spot the first name is missing, and without it it became a place. Both were removed, but it read as if it were two different things. A value now keeps the label of its first occurrence.

- **Dates were no longer being removed.** A date made entirely of digits ("01.03.2026") fell, since the last version, through a check meant for names, and remained in the document — even in "shift" mode, and without a line in the verification report. This only affected anyone who had explicitly turned on date detection.

- **Countries and continents are no longer redacted.** "Die Lieferung geht in die Vereinigten Staaten," "Marktschwäche in Asien," "die Norm gilt in Rumänien" — such statements say nothing about a person and now remain. If the country name, on the other hand, belongs to an address or stands behind a label like "Wohnsitz" or "Geburtsort," it continues to be removed. **Cities are not affected** — "Ich bin gerade in Bilbao" remains a statement about a person and continues to be redacted.

- **Abbreviated words became web addresses.** If the text reads "bzw. deutsche" or "incl. der," some PDFs deliver the period without a space — this turned into "bzw.de" or "incl.de," a valid address with a country ending, and it was removed. Such word pairs now remain. Genuine addresses are unaffected, even without "www." before them.

- **Number columns from balance sheets were redacted as phone numbers.** In business reports and price tables, the previous year and the current year stand next to each other — "64.518  65.133." This counted as a phone number and was removed, as were number ranges like "12200-23200" and a date with a following number. Such numbers now remain. Conversely, a genuine phone number is now recognized more reliably: the labels "Telefon," "Fax," "Mobil," "Durchwahl," and their equivalents in the other interface languages now count too — previously the program only recognized the English words there.

- **Names in a numbered table remained.** A participant list or personnel table in the usual form — column header, below it "1.1 Auersperg Bernhard Montage 03.03.2026" — was not cleaned at all: such lines looked like the item list of a quote, where factual terms are meant to remain. If the column header carries a person label ("Name," "Nachname," "Surname," …), the lines below now count as names. Item lists remain unaffected as before — even when the letterhead says "Sachbearbeiter:."

- **A name sometimes turned into two placeholders side by side.** If a surname also stood alone elsewhere in the document, the follow-up pass at a spot like "Anna Musterfrau GmbH" replaced first the surname and then the first name — in the result this looked like two different people. Now the longest known name wins.

- **Invented values were not in any mapping.** Anyone who had chosen "invent values" got a result in which "Anna Musterfrau" had become "Greta Mayrhofer" — none of this appeared in the mapping as soon as the same document contained even a single anonymous replacement. This made no invented value restorable, and the mapping file kept the replacement secret. The trickiest part was the third consequence: anyone reading the result sees a believable name and has no clue that it is invented. Every replacement now appears in the mapping.

- **The mapping called redacted content "replaced."** An email shares a mapping with its attachments, and the attachment may be redacted while the mail text carries a placeholder. The mapping then said the same thing — "replaced" — for all three spots, and restoring searched the attachment for a placeholder that doesn't exist there: the bar remained in place. The mapping now states, per hit location, what actually happened there, and both attachments come back correctly.

- **Values that only stood in an image could not be restored.** In the hit panel they appeared twice — once as a placeholder that existed nowhere in the document ("The placeholder was not found in the document"), once as a redacted spot. The first line was pure bookkeeping and has disappeared.

- **Redacted values could only be restored once.** If the same value stands in several places, one click restores all of them — but the remaining rows stayed in the hit panel, and the next click on them reported "Not unique." They now disappear along with it.

- **Reversals were missing from the verification log when learning mode was off.** Anyone restoring a redacted value in the touch-up window did not find the action in the verification log as soon as the learning questions were switched off — the record depended on a switch that is only meant for rule suggestions. With the verification log enabled, the reason is now asked independently of that, and the line is written.

- **Dragged-in files remained uncleaned — and were not even reported.** Anyone who drags a file into a document instead of sending it as an attachment has Word or PowerPoint store it entirely inside the document. It then remained unchanged in the result, complete with its original file name and storage path — and in practice these often carry a name themselves. Such files are now cleaned like the rest of the document.

- **And where that is not possible, Maskuro says so.** If an embedded object contains an old format (Word 97, Excel 97) for which no cleaner exists, a WARNING notice with the file's name now appears. Previously it was silently passed on unchanged.

- **Torn-apart words and abbreviations were mistaken for names.** When a word is split at a line end in a PDF, reading out some files produces a fragment — "Jahresent… gelts," "Gewerbli…." Such fragments, glued-together words ("TürverschlussmitV"), and bare abbreviations ("JY," "FFB") were redacted as if they were names. They now remain. A name with the same splitting damage continues to be redacted as long as a salutation accompanies it — and names that natively carry a capital letter inside the word (McKenzie, MacDonald, LeBlanc) are unaffected by this anyway.

- **Measurements and months counted as an address.** In technical documents, "2000 Lux," "1200 Mbit," "1500 Watt," "5308 Platz," and "2022 Mrz" were redacted — four digits and a capitalized word looked like a postal code with a city. A postal code now only counts if an address signal accompanies it too: a country code, a field label, the start of a line, a street on the line above, or a place that language detection also sees there. In five bills of quantities, this eliminates 14 false redactions without a genuine address remaining.

- **The more precise detection replaced too much.** The optional "more precise detection" tier mistook factual terms for names and places in German business documents — "Photovoltaikanlage," "Einspeisepunkt," "Flachdach," "Personaleingang" — and redacted company names from running item lists. The reason was a protective exemption: their hits were excluded from the checks that recognize an item or directory line. This exemption now applies only to multi-part names, for which the tier exists — "Anna Huber" in a directory line thus remains recognized, while a single factual word in an item line falls away. In a technical tender, this halves the tier's false redactions without a single name being lost.

- **Charts brought their full source data along — unchecked.** Anyone who inserts a chart in Word or PowerPoint has the program store the table it was calculated from as a separate file inside the document. Only the handful of numbers in the chart are visible; the table contains the whole list, including rows that don't even appear in the chart. This table was previously passed on unchanged. It is now also cleaned, using the same placeholders as the rest of the document.

- **The same for embedded objects in OpenDocument files** (ODT, ODS, ODP): an inserted chart or an inserted table remained untouched.

- **Word documents: footnotes and endnotes were not cleaned.** Their text remained fully in the result — including names, addresses, and account numbers. This affected every Word document with a footnote or endnote. Likewise, an AutoText building block that travels invisibly with the document remained untouched.

- **Word: data in dropdown lists, comments, and image descriptions.** The entries of a dropdown field (visible only when expanded), the author of a comment, the description of a drawing, and the address behind a hyperlink field remained in the result.

- **Excel: the pivot table stored the source data a second time.** A workbook with a pivot table keeps a complete copy of the evaluated rows inside it — invisible, but in the file. This copy previously remained unchanged, even when everything in the sheet itself had been replaced. This affected every evaluation shared along with a pivot table.

- **Excel: threaded comments and their authors.** The text of a newer-style comment and the directory of commenters — display name and login ID, in companies usually the email address — remained in the result. The same directory in Word documents likewise.

- **Custom document properties in Word and Excel.** Fields such as "Mandant" or "Aktenzeichen," which a law firm attaches to its templates, were previously not cleaned. They are visible in no view and yet travel along with every copy anyway.

- **Spreadsheets (ODS): a cell's dropdown list.** As in Excel since the previous version, what appears when expanding a cell is now also cleaned in OpenDocument spreadsheets. References to other cells remain untouched so the list keeps working.

All these spots can be restored as usual via the mapping.

- **Outlook messages: a damaged file hard-stopped cleaning.** Certain broken `.msg` files led to an abort instead of a message; they are now read as far as they are readable.

- **The mapping file is now readable only by you.** It contains the original data in plain text and previously sat with the usual permissions next to the result — on a shared storage location, anyone could thus open it. Nothing changes about the cleaned result itself; it is, after all, meant to be shared.

- **Downloaded language models are now checked more thoroughly before unpacking.** A tampered package — for example from a company distribution serving several workstations — could place files outside the intended folder during unpacking. Nothing changes for ordinary downloading.

- **Take a screenshot — and it gets cleaned right away.** With `Ctrl+Shift+B`, via "File → Take screenshot …," or via the taskbar icon, you drag a frame across the screen. What lies inside it then takes the same path as any other file: text recognition reads the on-screen text, names, addresses, phone numbers, and email addresses are redacted, and afterward the image sits open in the editor, where you can redact by hand anything that was missed with a frame. The cleaned image lands on the desktop (or in your configured output folder); the **raw** capture is stored nowhere and is deleted on exit. Text recognition is switched on for this run even if it is otherwise off — nothing could be found in an image without it. On the Mac, the system asks for "Screen Recording" permission the first time.

- **You can now draw on images: rectangle, ellipse, arrow, text, and numbered step markers.** In six colors and three line thicknesses, selectable with keys 1 through 5. This is meant for screenshots and instructions: show what matters, without opening a second program for it. Undo and dragging the handles work like for any bar — an annotation can thus be moved and resized after it is placed.
  **Drawing is explicitly not redacting.** A drawn rectangle is a frame, not a bar: what is underneath stays legible and goes out with the file. "Redact" and "Pixelate" remain there for removing data; the drawing tools therefore stand in their own row of the toolbar, and the notice line says so as long as one of them is selected.

- **The edited image goes to the clipboard with one click.** "Copy image" in the editor (or `Ctrl+C`) places it exactly as it stands — pasting is enough to bring it into a message or an email. That makes the path from keypress to chat four steps long and needs no folder.

- **Also new: a highlighter, shadows, and gradients.** "Highlight" colors an area without covering it — the content underneath remains legible, and this is exactly what distinguishes it from a bar. "Shadow" lifts an annotation off a busy background, "Gradient" fades the color out in the direction of the drag; both apply to all six drawing tools.

- **Fixed before it hit anyone:** the new tool row would have appeared nearly empty for anyone who had already used Maskuro — the remembered window layout dated from before it and would have left it no room. An outdated layout is now discarded; the editor window then appears once in its default layout.

- **Your own screenshot capture can be turned off.** Anyone used to Greenshot, ShareX, or the Snipping Tool turns off "Take screenshot with Maskuro" under "Settings → Program." Maskuro then does not even register the keyboard shortcut — it stays with your tool — and the change takes effect immediately, without a restart. An image captured this way can still be cleaned: Ctrl+V pulls it from the clipboard into the window.

## 0.10.37-alpha.20260821 – August 21, 2026

### New

- **When anonymizing, every hit now carries its own number.** Previously, all persons were called `[NAME]`, all places `[ORT]` — this made it impossible to tell which spot belonged to which value, and there was nothing to restore. Now the numbers keep counting per occurrence: the same name appears in three places as `[NAME_1]`, `[NAME_3]`, and `[NAME_7]`. In the document it is thus still not apparent which spots belong together — but with the mapping file, each one can be individually restored. The mapping file is therefore selectable again even when anonymizing; keep it separate from the result.
- **Months, weekdays, currencies, units, and company legal forms in all 48 document languages no longer count as names or places.** The calendar and unit names come from Unicode CLDR (generated, not written by hand), the legal forms from the corporate law of the respective countries — including multi-word ones ("sp. z o.o.," "Pty Ltd") and prefixed ones ("株式会社"). Where a month name is also a first name (Juli, August, May), the pattern decides: with a day or year next to it, a date; otherwise a name. Also added: salutations and titles, whole closing phrases, document types, and street base words for 28 languages with their own language model, legal abbreviations (DSGVO, UStG, ABGB, § 6 Abs 1 Z 27 UStG), and language names as a field value ("Sprache: Deutsch"). The lists are under "Help → Word lists …."
- **India: address and PIN code are now recognized** — "15 गांधी मार्ग," "नई दिल्ली 110001" as well as "15 Gandhi Marg, New Delhi 110001." The India country package previously only knew ID numbers; addresses in Hindi documents therefore remained.
- **Every cleaned Office file is opened once more as a package before being handed over.** A text extract doesn't notice when Word, Excel, or LibreOffice would refuse the file (duplicate entry, broken XML, a missing part). And what a cleaning must never change is counted against the original: pages of a PDF, sheets, rows and cells of a table, slides of a presentation. If the check triggers, a WARNING notice appears in the result and in the verification report — the original remains unchanged.
- **Automatic mode now also redacts the whole field.** In redaction mode, the bar in short lines — address block, table cell, header data — now covers the whole line instead of just the found value: a word-length bar reveals how long the word was. Labels and amounts next to it remain, and running-text lines (longer than half the text width) continue to be redacted word-precisely, so a name in the middle of a sentence doesn't blacken the whole sentence.
- **Restored content looks like the original again.** "Restore original" and "Undo replacement" in the PDF editor now write the region back exactly from the source file — same font, same size, same color and position, on a scan the same pixels. Until now, the text was re-inserted in a substitute font and looked recognizably reconstructed. The bar of an earlier redaction now disappears entirely instead of being painted over white — a colored cell background in a table is preserved. This also applies on rotated pages, to text from embedded form objects, and to **filled-in form fields**: on the working copy rasterized for this purpose, the crop from the freshly rendered original page comes back — even where no text layer knows the field value. **Replaced images** in the PDF also come back this way — pixelated, blurred, or fully removed, whole or just the dragged crop. Only where the source file no longer sits next to the result does the previous method still apply.
- **Redacted and removed-without-replacement values can now also be restored in Word, Excel, PowerPoint, and OpenDocument.** Previously, restoring there required a placeholder in the text — a bar or a gap had no way back. Now the hit panel offers "redacted" and "removed" rows as soon as the untouched source file sits next to the result: Maskuro compares the result with the original and reinserts the value at the spot of the bar or gap — complete with formatting, a split run becomes whole again. This also applies to text, HTML, email, and the Office attachments of an email; if the mail text carries a placeholder and the attachment carries a bar, both are restored in one pass.
- **PDF attachments of an email or Outlook message can also be restored** — placeholders (numbered and anonymous), bars, and content removed without replacement. Without a canvas, the spot comes from the original attachment; the value returns glyph-precise, in the reading order of the original.
- **Masked values can be restored** — in PDF and in the text view. A mask ("**** **** **** **** 3201") is never unambiguous, two numbers carry the same one; restoring therefore never takes the literal route but asks the original which value stood at this spot. Previously these rows were not operable in the hit panel at all.
- **Embedded images in Word, Excel, PowerPoint, and OpenDocument can be restored.** A value redacted in the image comes back via its panel row — Maskuro reads the original image and retrieves exactly this spot; a blurred, removed, or face-and-code-edited image is restored as a whole via the new "Restore embedded images" entry in the Edit menu — even through the Office attachments of an email or Outlook message. An image that itself hangs as an attachment and was redacted via text recognition likewise comes back via its panel row.
- **Invented values can be restored in the text view.** Previously the panel reported "Not unique" there. Now restoring searches for the value in the original and demands exactly the invented replacement at the same spot in the result — an invented name is never replaced literally everywhere; it could genuinely stand somewhere.
- **Restoring in Word, Excel, PowerPoint, and OpenDocument now keeps the original's formatting.** If a value spanned several runs — "Anna" normal, "Musterfrau" bold and red — it previously came back entirely into the first run and lost the bold and the color. The characters now distribute again as in the original; a Word paragraph is afterward byte-for-byte the original one. The same applies to HTML pages, the HTML part of an email, and the HTML body of an Outlook message (.msg) — for email, the doctype is also preserved now, which cleaning previously silently removed.
- **Text files keep their encoding.** Cleaning and restoring now write `.txt`, `.md`, and `.csv` in the encoding they were delivered in — UTF-8 with and without a BOM, UTF-16, Windows-1252. Previously a Windows-1252 file always turned into UTF-8, and a UTF-16 file came back damaged even if there was nothing to replace in it.
- **Restored images keep their color mode.** A grayscale scan comes back as grayscale instead of a three-times-larger RGB file, a palette image as a palette, black-and-white as black-and-white — for the whole image with the same values as in the original. Applies to image files and to images in PDFs. CMYK and 16-bit remain RGB, because the PNG result cannot carry either.
- **A frame on the image now restores the whole edit it touches.** Pixelated faces carry a margin around the recognized box; anyone who only dragged the frame over the face kept a pixelated ring. The frame now grows to cover the contiguous change from the original — a frame over the eye area is enough. Separate bars next to it remain; for a fully removed or fully blurred photo, the dragged frame still applies. Applies to image files and images in PDFs.
- **Redaction bars across the whole line.** In the editor's line mode, the bar now runs from the first to the last word of the line, no longer just over the matched word — a word-length bar reveals how long the word was, and a place name can be guessed from six characters before a postal code. Labels, amounts, and table columns next to the value remain — the bar covers the field, not the invoice's line. The new "Whole line" switch next to "Text lines" switches back to word-precise when neighboring words are meant to remain; the choice is remembered.

### Fixed

- **Images in HTML pages and emails remained unchecked — the name in the logo still stood legible after cleaning.** An image embedded in the page (`data:` address) was not touched at all, only its alt text; the logo in the HTML branch of an email (inline image without a file name) fell through the attachment filter; and with a named image attachment, the image rule "blur"/"remove" had no effect. All three now take the same path as an image file: text recognition in the kept image, faces, codes, metadata, and the image rule. The report names the images — including the warning if they remain unchecked without text recognition — and "Restore embedded images" as well as restoring from the hit panel now also know these images.
- **An Office file with an image could not be cleaned at all if text recognition did not support the language.** On the Mac, the system's own text recognition reads; for Hindi, Greek, Croatian, or Lithuanian it cannot, and has recently started saying so — but with Word, Excel, PowerPoint, and OpenDocument, this aborted the **entire** cleaning, and no file was produced. Yet the text could be cleaned flawlessly; only the image was unreadable. The file is now written as with PDF and individual images, and the result states that the images were NOT checked — with the reason and a reference to "Manage languages."

- **In Excel workbooks, names remained in dropdown lists.** The list of a dropdown field (data validation) is now cleaned like any other cell content; references to cell ranges remain untouched so the workbook stays intact.
- **Where the placeholder did not fit, a black bar appeared — now a shorter notation appears there.** `[GEBU_1]` instead of `[GEBURTSDATUM_1]`, and only once even the shortest form no longer fits is it redacted. A bar no longer tells anyone that something stood there; a short placeholder does. The touch-up editor could already do this, automatic cleaning previously could not. The mapping file lists both notations under the same value, so the shortened form can be restored too.
- **The first click on "Replace" made the touch-up window pause briefly.** The detector that gives the placeholder its type (`[NAME_3]` instead of `[BEGRIFF_3]`) was only loaded at this moment — roughly two to three seconds. It is now prepared in the background when the window opens; measured, 2289 milliseconds became 193.
- **Two simultaneous cleanings could load the same language model twice** — e.g. folder monitoring and the main window. Because each model occupies several hundred megabytes, memory demand briefly doubled during this. The second run now waits for the first one's model.
- **The place in a date line is now also removed when the language model does not recognize it alone:** what is reliably found as a postal code with a city ("3335 Amstetten") now pulls its place name along throughout the whole document — like a surname from a full name. And an abbreviation with a digit before a name ("T3 Hofbauer Christian") remains legible instead of disappearing into the placeholder.
- **Three leaks from the second-reading review of a real order closed:** the clerk "T3 Hofbauer Christian" was treated as a column header because of the abbreviation "T3" and remained legible; a place that the language model read across the line break into the column header swallowed "Pos." and left the customer's first name standing; and a name with a salutation ("Herr Robert Köttel") only pulled the surname along, not the first name — and instead pulled along every "Herr." Abbreviations are now purely letters, two-word names are no longer a header, hits are cut off before a column header, and the salutation no longer counts as part of the name.
- **The place in the date line ("Melk, 05.08.2026") directly below the address block remained legible.** The language model glued it together with the place from the postal-code line into one hit, and that hit as a whole failed against the postal-code pattern. The protruding remainder now stays a hit of its own. Found through the new second reading of the result (`werkzeuge/zweitlesung.py`).
- **Mac: a scan in a language the system's own text recognition does not support (e.g. Hindi, Greek, Croatian, Lithuanian) counted as checked.** It was read with the English fallback, the foreign script remained in the image, and the report said "nothing found." It now reads "Image(s) were NOT checked" with the reason, and language management no longer promises text recognition for such languages just because a Tesseract language file happens to be present.
- **In the PDF, the punctuation mark behind a replaced value now remains.** "Aufnahme am 01.03.2026, Entlassung am 04.03.2026." previously became "Aufnahme am [DATUM_1] Entlassung am [DATUM_2]" — the comma and closing period were missing, both with placeholders and with shifted dates. Now only the recognized value is removed, not the whole word up to the next space; a comma, semicolon, period, or bracket behind it remains in place, and the placeholder does not run over it.
- **Russian and Ukrainian silently ran with the weaker multilingual model** when a helper package for word-form analysis (`pymorphy3`) was missing — their own models then could not be loaded, and "Львів" became a person. Word-form analysis is not needed for name detection; the model is now loaded without it, and places are places again.
- **The license notices in 16 languages were out of date.** They still stated that the MPL source code was provided "upon request," QPDF was listed as MPL-2.0, seven components were missing from the table (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), the spaCy paragraph was in English, and an English fallback section hung at the end. All 18 versions now match the German one: source archives permanently at maskuro.com/quellcode/oss/, QPDF Apache-2.0, the Qt LGPL path, model provenance. The English table also has the missing rows now.

- **Contract words in the genitive case ("des Angebotsinhaltes," "des Anbotes," "des Terminplanes") no longer count as a place.** A single word behind a genitive or dative article with an inflectional ending is a generic word — place names don't inflect ("nach Graz"). If the place stands elsewhere in the document without an article ("Burgenland"), "des Burgenlandes" also remains recognized.
- **Shifted, masked, and invented values rasterized the PDF page.** The verification after removal only allowed a placeholder in square brackets within the hit rectangle; a shifted date ("01.07.2026") or a masked value ("****1234") counted as an overlooked remainder, and the page was, as a precaution, converted into an image — not the case with "Replace." Such pages now remain text, and restoring from the panel or a frame again returns the original.
- **Multi-word replacement values could not be restored via the hit panel in a PDF.** An invented name ("Greta Mayrhofer") or a masked IBAN ("**** **** **** **** 3201") consists of several words; the hit search compared word by word and reported "The placeholder was not found in the document." Consecutive words of the same line are now read together.
- **After restoring a value removed without replacement, its panel row remained.** Values that the "redact" strategy removes without a replacement in placeholder mode have no placeholder against which the panel could measure a disappearance. The row is now removed as soon as the value is back in the document.

- **Abbreviation compounds such as "E-Helfer" or "U-Bahn" no longer count as a name.**
- **Hyphenation remnants ("Leis-") and overlong compounds ("Bauarbeitenkoordinationsgesetzes," "Baustellenkoordinator") no longer count as a name or place.** In a scanned tender text, this resulted in 28 fewer words being redacted.
- **Item lists of scanned quotes no longer count as a name directory.** The extra pass for directories (short lines) turned "Kälterohr" and "Außengeräte" into persons; it now stands down as soon as item numbers like "1.1.5" stand at the start of the line. Date lines in email threads don't count as item numbers for this.
- **Column headers and item numbers of scanned quotes ("Pos.," "Pos. 1.1.3," the abbreviations "E/L/S") counted as a name or place.** An abbreviation alone on its own line, a label with a number, and single letters line by line are not.
- **The page "breathed" in the touch-up window after opening the comparison magnifier** — with "Page width" and "Fit," the scale hangs on the viewport, and that changes with every scrollbar that appears or disappears; every following action shifted the page a bit further. The canvas now catches up on its own until it settles. And zoom buttons, sliders, and keyboard shortcuts now hold the image center even when a scrollbar appears while zooming in.
- **Scans saved sideways are now read upright, and small print in large scans no longer gets lost.** A 24-page scanned quote kept six bank IBANs, the company register number, and the VAT ID legible in every footer: the scan sat rotated 90° in the PDF, and text recognition dropped whole lines depending on the image size with very large images. The visible rotation is now taken into account, and large images are read in overlapping bands — the footers are now black.
- **Streets named after people with a hyphen before the base word ("Josef Admanseder-Straße 7," "Abt-Karl-Straße 8," "Dr.-Karl-Renner-Straße 12") are recognized as an address.** In the letterhead of a scanned quote, such an address remained legible because the pattern required a space before "Straße."
- **IBANs from text recognition carrying an O instead of 0 or an l instead of 1 are now recognized.** In the fine print of a scan, text recognition likes to read digits as letters; the number then had the form of an IBAN, but the checksum did not add up, and it remained. If the checksum fails, the digit reading is now tried — if it matches then, it is the IBAN. Incorrect check digits remain incorrect.
- **Sentence fragments like "folgenden Codes auf der" counted as a place.** A name or place beginning with a lowercase word is not one — except for noble particles ("van Gogh," "de Vries").
- **In the editor, the last letter remained next to the redaction bar** ("…6," "…t," "…g"), and the bar had the height of the dragged frame instead of the line. Cause: if the editor could not measure the page, it treated every frame as "no word hit" and applied it exactly — without the rule that half a word never remains. The same happened with individual text commands the editor could not locate. Now the word box next to it always counts: whatever the frame substantially overlaps falls entirely.
- **The last letter of a word protruded past the redaction bar.** The bar was sized from the advance width in the font metrics; if the font draws a glyph wider, its remainder stood next to the bar. A character's box now also takes in the drawn glyph.
- **The notice about converting a page into an image promised too much.** "The appearance stays the same" is not true after rasterizing: text and graphics then become pixels, and the file grows larger. The notice now says so — and also names the second reason rasterizing happens (the rebuild would have damaged the page).
- **The text behind a removed value shifted up to one point to the left.** When rebuilding a line, the start was measured at the glyph edge, the continuation at the pen origin — the advance width of the first letter remained as an error ("C" 0.5 pt, "I" 1.0 pt). The rebuild now consistently computes with the pen origin; the following text sits at its spot to the tenth of a point.
- **An Austrian VAT ID with spaces ("ATU 187 35901") and a company register number without "FN" under its label ("Firmenbuchnummer: 30799v") are now recognized.** Both were handwritten on a scanned tender form and remained legible even though text recognition had read them correctly.
- **Landscape PDF pages were needlessly converted into an image after redacting.** The integrity check compared the original and the result in the rotated display but calculated their redaction zones unrotated — on a page with a rotation marker, its own redaction thus sat next to its zone and counted as damage. Such pages now keep their text layer and vector graphics.
- **Even portrait pages were occasionally needlessly converted into an image**, when the text behind a placeholder shifted by one point — allowed, but the image comparison was finer than its own tolerance. It now compares in half points and thus hits its tolerance exactly: up to two points of offset, nothing triggers; beyond that, everything does.
- **Data in embedded form objects remained.** Some templates place a letterhead or letter closing as a separate form that the page merely embeds. A hit inside it was planned and counted as removed, but never written — the text remained there, and only the rasterization of the whole page caught it. The form itself is now rewritten; a form that sits on several pages, only once.
- **PDF pages were rasterized into an image even though nothing legible had remained.** A seven-page quote was hit on six pages; it grew from 73 kB to 3.3 MB and lost its text to an image. The cause was spaces that occur several times in a row in the document but are only reported once by the reader: the text behind a removed item shifted right by its width, the verification found the neighboring word inside the hit rectangle and reached for rasterization. Kept line remnants now sit exactly in place again; the same quote is cleaned without a single rasterized page (76 kB).
- **Key names and invoice headers counted as persons.** In an access file, the name of the environment variable ("AWS_ACCESS_KEY_ID") was replaced, not just its value; on an English invoice, the heading "Bill to" fell as a first name. An identifier in uppercase with underscores is never a name, and neither is a word in a line that as a whole is a field label — the recipient below it continues to be found.
- **Search in the touch-up window stuttered on large PDF pages.** Every letter in the search field made the page re-rasterize, even though only the highlighting changed. The rendered page image now stays as it is, as long as page, zoom, and view are unchanged — the original in the comparison magnifier too; paging, zooming, and a new file state still redraw fresh as before.
- **Item numbers in quotes counted as an IP address or a phone number.** An item line like "1.3.3.4 … 5-Port Gigabit Switch" turned the outline number into a network address because "Port" counted as technical context — it now only counts as a standalone item ("Port 80"), not as part of a word. And "1.3.3.6 216879" (item plus part number) is no longer redacted as a phone number. Genuine IP addresses and phone numbers in such lists continue to be recognized.
- **Item lines in quotes counted as a postal code with a city.** "35252 DIETZEL SALR" (part number with manufacturer) and "1000 AWG" (quantity with wire gauge) were redacted as an address in numbered item lines, because an uppercase word behind a number counted as a place name in capitals. This no longer applies in item lists; "1080 WIEN" in an address block and places in lowercase continue to be recognized everywhere.
- **The additional name detection redacted role lines and column headers in quotes.** "Partiestundensatz Monteur + E-Helfer" counted as a person 49 times, the column header "Pos. Bezeichnung Menge EH" as a place 19 times — a 19-page order became illegible as a result. Such hits in item lines now fall if they themselves carry characters no name has (plus sign, slash, digit, abbreviation) — even when the line ends with an amount ("Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). Names in directories and lists — what the tier is for — remain untouched.
- **"Der Kunde" turned every "Kunde" into a name in terms and conditions.** If the additional name detection took the article into the hit, it counted as a two-part name and protected all 35 further occurrences of the same word. The article is now stripped off, and "der Kunde" falls just like "des Kunden" already did.
- **Labels counted as a value.** "E-Mail" was redacted as an email address seven times, "Telefonnummer" and "Faxnummer" as a phone number. An address without @ and a phone number without digits no longer count.
- **Single-letter column abbreviations ("L: 154,50," "S: 0,00") counted as a name** — 25 times in a PV quote. A single letter is neither a name nor a place.
- **PDF pages were converted into an image far too often.** Two causes, both found in real quotes: if a PDF sets every glyph as its own command and a space glyph without a text character is hidden underneath, the mapping shifted by one from that point on — the last letter of the removed value remained ("ŠkodaTopCar**d**"), and the verification rightly rasterized the page. And a word split at the end of a line ("Datenschutz-") counted as shifted because of the reading library's hyphen marker. Both fixed: a vehicle quote went from 4 rasterized pages to 0, a 19-page order from 7 to 0 — the text stays text, the file stays small.
- **Two further rasterization causes fixed:** if a document itself brings along a font named "F1," placeholders over images were set in that font and were illegible — the built-in labeling font now gets a free name. And where the reading library is missing a space in the middle of a long text command, the spot is now proven for multi-byte fonts too (same code, same character) instead of ending up at random — previously a letter of the removed value remained standing and the rest of the text visibly shifted. Also two final cases: a command made of dozens of space glyphs let the mapping run away (the name after it remained), and a large heading with an advance width did not find its first character (the company name remained). **Of nine real quotes, not a single page is rasterized anymore** — previously it was 30 of 90.
- **Images disappeared under a black block during rasterization.** If a page must be converted into an image, it is rendered from the original — and that knows no image cleaning. Previously, *every* image area of the page fell under a bar as a result, including untouched ones. On one quote, the address and two certificate logos sat in the same letterhead image; the bar took the logos with it. The already-cleaned image is now inserted instead: the address in it is redacted, everything else remains visible. A removed image leaves white paper instead of a black box.

- **Cleaned scans became many times larger than the original.** Every image in which something was redacted went back into the file as an uncompressed raw image — for a 24-page scan, this grew it from 11.8 to 52.9 MB. Images now keep the format they came in: a photo stays a photo, a fax scan stays black-and-white, a colorless image is not stored as a color image. The same file is now 15.6 MB, with no visible difference.

- **Scanned PDF files from office equipment came back as a striped pattern.** Such scans place the text as a sharp black-and-white layer over a coarse color image — Canon, Xerox, and Kofax build their files this way. When redacting in the image, this layer was written back incorrectly; the result was illegible. On a six-page quote, this hit nine of sixteen images. It is now handled correctly, in its own color, and the redacted spots are truly gone in it.

- **"Remove all images" took a scanned page's text away.** The text layer of such a scan is technically an image — it was removed or blurred along with everything else, leaving an empty page. It now remains; logos, stamps, and signatures continue to yield.

- **The check for damaged PDF pages no longer rasterizes because of a tiny offset.** A piece of text re-anchored during cleaning may shift by up to two points; the image comparison still counted that as damage and rebuilt the page as an image — losing vector graphics such as table lines, and a bar sat over hit locations instead of a placeholder. The comparison now allows the same small offset as the word check; genuine damage continues to be caught.

- **Restoring many values one after another on Windows no longer failed with "Access denied."** Anyone restoring many panel rows in quick succession in an Office file could fail on a short-lived file lock from the virus scanner; the exchange now briefly waits out such locks.

- **The Windows path of command handover terminated the checker instead of checking.** The liveness check of the listening instance accidentally sent a real Ctrl+C to its own console group on Windows; it now asks the system without a signal.

- **Multi-word field labels had no effect, but their fragments did.** "Date of birth," "Bank account," "Cuenta bancaria," and "Numero de cliente" stood in the label list but were split there into individual words and thus never matched; what remained were word fragments like "de" and "of," which since then counted as a label — but "de" is part of a name ("Anna de Vries"). Both are fixed: the phrases now work as a whole, the fragments are gone.

- **German closing phrases with "ß" were treated as a person's name despite being listed.** Under "Herzliche Grüße" or "Mit freundlichen Grüßen," a placeholder stood in the result, even though both phrases have always been on the exception list. The cause was a spelling that never matched during comparison; eight entries across five lists were affected. All of them now work.

- **"John Staff" remained unreplaced.** A surname that is also an English column heading was discarded along with the label filter. The heading itself remains untouched as before, but the name below it is replaced again.

- **Values from labeled form fields remain protected in the AI tier.** The AI tier's local arbiter was previously also shown hits whose meaning the field label had already established ("Geburtsdatum:" above the value) — and was allowed to discard them. Such structurally documented values are no longer shown to it. The mapping file now also names the detection path ("evidence") for every replacement.

- **A PDF page whose preserved text suffered damage during cleaning is now recognized and rebuilt as an image of the original.** With some generator fonts, preserved text spots could appear as black blocks or words could merge together after cleaning, even though all data to be removed had been correctly removed. Maskuro now compares the result word by word and pixel by pixel with the original; a damaged page is replaced by its clean image — with redaction bars over the hit locations, redacted image areas, and searchable text. The page remains legible, the removal reliable.

### Changed

- **In the translated interfaces, every technical term now reads the same everywhere.** For one and the same German word, two or three translations stood side by side depending on the window: the verification log was called "Revisjonslogg" in Norwegian in some places, "Kontrollogg" in others; the free tier was "Gratisnivå" in some places, "Gratisversjon" in others — and similarly in a dozen further languages. Anyone looking for a setting found it in the next window under a different name. This has been unified to the word the interface already uses most often.

  In the process, spots came to light where one word stood for two **different** things: French, Greek, and Korean used the same term for "redact" and "mask" — of all places, exactly where the program explains the difference ("Redacting removes without replacement, masking keeps the shape"). Both are now kept apart. For Swedish this decision is still pending: there, redacting is called "maskera" — the same word as masking.

- **The question about the type of use on first launch has been dropped.** Shortly after startup, a window appeared ("Private or in business?"), and settings carried a line about it. Both are now gone — with no replacement. A field that nothing hangs on gives a wrong answer for anyone who wants the wrong license, and anyone honest doesn't need it; it cost everyone a click at a moment when nobody is thinking about license types. Which license is the right one is stated where it is decided: on the pricing page, at checkout, and in help. Organizations rolling out Maskuro centrally continue to prescribe the type of use via the policy file.

- **The license-type notices now name the case they concern.** The private license applies exclusively to private use; any professional or commercial work needs the business license — even as a sole proprietor without employees. This was stated in the license terms, but neither in the program nor in help: there, only the company domain was ever mentioned, and that does not cover exactly this case — a sole proprietor's computer belongs to no domain. The notice when reading in a private license now says so, as does the license chapter of the manual and the FAQ, which got its own entry for this. Nothing is blocked as a result.

- **The not-yet-shipped paths now sit together.** Settings gained a "Developer" page; it holds maximum detection (AI) along with its cross-check, the word-list catalog, and folder monitoring. All three are built but not tested at scale — they are therefore only visible with a developer license, and everywhere at once: the page, the menu entries, and the effect during a run all hang on the same decision. Without this license, a previously enabled AI tier remains without effect; its setting is not deleted and applies again as soon as the path is shipped.

### Improved

- **"What is searched for" shows three further lists from name detection.** The salutations after which the following word is read as a name; the titles and roles that afterward are **not yet** the name ("Herr Bürgermeister Huber"); and the eighty multilingual labels used to recognize case, transaction, and file numbers. All three have always been in effect but were not visible in the overview.

- **"What is searched for" shows two previously missing word lists.** The salutations and titles that turn a preceding word into a name ("Herr," "Frau," "Dr."), and the abbreviations of standards organizations that let Maskuro distinguish a standard reference like "ÖNORM B 2110" from a person. Both have always influenced detection but were not shown in the overview.

- **Item lists, tables of contents, equipment enumerations, and standard references remain legible.** Detection now sees the pattern of the line: a guessed name in an outline line ("1.3.1 Energieerdkabel 1kV"), a directory line with leader dots, a bullet ("- kabelloses Laden mit Magnetring"), above a quantity/price line, in a column header, or behind "mittels" is a factual term and is no longer replaced. Genuine names remain protected — through a salutation, a field label, and the evidence elsewhere in the document; on the measurement corpus, not a single item lost its protection. In the business corpus, false positives thus drop from 25 to 6.

- **Headings, form labels, and closing phrases are less often mistaken for names — in German and English.** The word lists with which Maskuro distinguishes factual words from person names have grown considerably: labels from invoices, forms, and official mail ("Aktenzeichen," "Verwendungszweck," "Kostenstelle," "Sort code," "Subtotal"), section headings of applications and reports ("WERDEGANG," "QUALIFIKATIONEN," "SUMMARY," "REFERENCES"), German and English document types ("Auftragsbestätigung," "Niederschrift," "Timesheet," "Agreement"), as well as imperative forms from instructions ("Sende…," "Select…"). The English side was previously noticeably thin here.

- **Labeled fields now also reveal what stands in them when the label is a compound.** "Lieferanschrift," "Rechnungsadresse," "Sachbearbeiterin," "Kontoinhaber," "Contact person," and "Billing address" now assign the value next to or below them to the same type as the plain "Anschrift" or "Name" — in a filled-out form with checkboxes, that is the difference between found and overlooked.

- **In the touch-up window, the mouse wheel keeps paging at the page edge.** Anyone scrolling past the end of a page lands at the top of the next one; anyone scrolling back past the start lands at the bottom of the previous one — a document can thus be scrolled from start to finish without touching the page buttons. The keyboard (Page Up/Page Down) could already do this; a brief breather between two page changes prevents a trackpad's momentum from carrying through half the document.

- **The page thumbnails in the touch-up window sit centered in the panel.** Previously they clung to the left edge, and dragging it wider only grew the empty margin on the right.

- **The toolbar of the touch-up window shows its groups.** The separator lines now have breathing room and color, "Search" and "Apply to all pages" stand as their own groups next to the tools, and "Apply" now only appears for document types where it can have an effect. Every entry in the toolbar and menus now carries an icon: "Text lines" and the comparison magnifier got their own icons (the magnifier previously shared one with "Before/After"), plus zoom, whole page, page width, rotate, paging, and the keyboard shortcuts. "Open with system program" now also appears in the toolbar next to Print — the path from the finished result into the familiar program is one click, not a menu trip.

- **The clipboard-cleaning notice again mentions that a review is needed.** In settings, the note now sits permanently next to the switch: Maskuro can overlook personal data or handle items incorrectly, and the pasted text should be reviewed before being passed on. When turning it on, the message additionally names it, and it is noted in the output area — even when no icon runs in the tray. It deliberately does not appear on every single copy: a notice that came fifty times a day would no longer be read after the third time.

## 0.10.36-beta.1 – August 20, 2026

### Improved

- **Technical business documents are no longer over-redacted.** Four detection brakes, gained from eleven real quotes and orders: outline numbers ("1.3.1.1") no longer count as IP addresses, standard references ("ÖNORM EN 62446") and identifier codes no longer count as a postal code or phone number, and role words behind articles ("der Kunde," "des Auftraggebers") no longer count as names — in the terms and conditions of a real quote, all 46 role words are thereby legible again instead of redacted. Addresses with a country code ("A 3390 Melk," "D-94032 Passau") are now removed completely, instead of leaving the postal code standing orphaned.

- **Word lists are now fully viewable.** Under "Help → Word lists …," the locally used detection and cross-check lists can be browsed together with language, purpose, source, and content. This also includes Wordfreq, medical, personal, and centrally managed lists as well as the pools for invented replacement values. The manual describes the catalog in its own section.

- **Finished file rows show the detection language used.** Behind "done" now stands, for example, "German" or "English," so an unsuitable automatic language choice is immediately noticeable. If a different installed language had to step in, an arrow shows both languages.

- **The new comparison magnifier immediately shows the matching spot in the original while reading through.** Its enlarged original crop follows the mouse cursor over the still-editable result; with text it follows the paragraph. The magnifier can be used at the window edge or dragged out as its own, maximizable window. Its zoom is directly adjustable between 50 and 300 percent and is remembered just like being turned on. "Reset" also brings a maximized or awkwardly docked magnifier back to a usable size on the left. Replaced original values are highlighted yellow in the magnifier, so the affected words immediately stand out while reading. Once activated, it opens again for future suitable documents — even after a program restart. The previous before/after toggle remains in the View menu. The manual describes it in its own section.

- **Open-source and model provenance are now release-exact.** The package build generates a machine-readable component list together with hashes of the enclosed license texts. MPL sources, model provenance, fixed revisions, changes, and SHA-256 are documented separately; downloaded models get their provenance record directly in the model folder. Moving Tesseract and spaCy reference lists have been pinned in place. Sales artifacts remain blocked until all sources and model attachments are published and verified.

- **The local wordfreq data set is fully license-documented.** The package build checks version 3.1.1, 39 unmodified small lists including CJK, and the Chinese character map against count, size, and manifest checksum. Apache-2.0 code notice, the full CC-BY-SA-4.0 license, attribution, data sources, and the omitted large, Jieba, and unsupported lists are documented in the package.

- **Common sentence words are now less often mistakenly redacted.** A local frequency dictionary serves as an additional cross-check when name detection mistakes a verb, pronoun, article, or preposition for a person. The dictionary never decides alone: common nouns, multi-part names, and names in fields, lists, and after salutations remain protected. Chinese, Japanese, and Korean use only exact token boundaries of their already-existing language models; for languages that have none, no supposedly similar dictionary language is substituted. No document text is transmitted to the internet for this.

- **Technical product and equipment terms are no longer as easily mistaken for names or places.** The local cross-check now combines frequency, part of speech, technical word formation, and factual fields. As a result, for example "Travel-Assistent," "Family-Bonus," "WLTP-Wert," "Easy-Start," and compound number, mount, or brake terms remain in the document. English components are also looked up locally in German factual text; genuine proper names, salutations, and person/place fields keep precedence. A "2-jährige Herstellergarantie" also no longer counts as an age.

- **The Qt/PySide license rights are now fully traceable.** The program package additionally contains the full GPL-3.0 text, the exact Qt versions, a source-code offer, and a German/English guide for exchanging the dynamic libraries, including local macOS re-signing. A sales build is blocked as long as the exact source archives of the shipped version are not available on the dedicated source-code page.

- **License and update status now clearly state, for every tier, what applies.** In the license window and the update settings, it now states whether updates are included, up to which day they extend, and whether the running version remains permanently usable. Private licenses no longer install a version released after the cutoff date; even a freshly downloaded installer recognizes, from its permanently built-in release date, whether the entered key covers it. The last covered private version remains permanently usable. If, on the other hand, a business subscription ends, both use and updates end; the trial period and free tier do not open as a detour.

- **Private perpetual licenses now also find the correct program version after a reinstall.** A signed version catalog lists all stable versions and their packages. If the last installer covered by the purchase is no longer available, exactly the next higher available stable version may automatically be used instead — never a beta or nightly. With an installation that is too new, the customer can install the permitted version or switch to the purchase page for a new update period; a downgrade never happens silently. This also applies to managed MSI installations.

- **Automatic face redaction is now clearly described.** Program help and the privacy text name the feature "Detect and obscure face areas" and distinguish it from identification, recognition, face comparison, biometric templates, and person or face databases. They also clearly point out that fully local detection can overlook or falsely mark areas, and that the result must therefore be visually checked. Even for an individually cleaned image file, the result report now names recognized and pixelated face areas; a missing text recognition step is no longer falsely described as a completely unchanged file.

## 0.10.36-alpha.20260820 – August 20, 2026

### Fixed

- **Anonymized data can now be fully restored regardless of order.** Earlier restoring searched for the value via visible text anchors. In dense tables, directly adjacent placeholders, and invisible Office/mail storage areas, these anchors were missing; sometimes a term only became restorable after some other plain text happened to create a new anchor. Now the result and the original are compared per genuine format carrier using the complete mapping, and only the documented spots of the chosen value are written.

- **Names, email addresses, numbers, and custom search terms remain unambiguously operable even with overlapping detection.** If the same plain value is assigned to two types, the placeholder actually standing at the hit location decides together with the clicked sidebar row. An undocumented value/placeholder pair remains safely locked.

- **Mail special cases no longer leave hidden placeholders behind.** This applies to MIME-encoded subjects, text attachments, and names split by HTML markup in EML and MSG. UTF-8 HTML without its own charset declaration is also no longer re-encoded into mojibake at every editing step in Outlook files; older results already written this way remain restorable.

### Improved

- **A new release matrix serves every anonymous sidebar row individually and deliberately in reverse.** It checks all 14 text, Office, web, and mail formats as well as PDF, and afterward also formulas, attributes, relationships, comments, mail headers, attachments, and internal secondary storage areas. The full macOS run now comprises 149/149 green test scripts.

## 0.10.35-alpha.20260820 – August 20, 2026

### Improved

- **Language measurements now genuinely compare like with like.** The regular measurement corpus contains the same 14 document cases with the same seven text and four image tasks in German and English. A full run repeats exactly this matrix for all twelve existing corpus languages. Forms, tables, chats, and other not-yet-fully-translated structural samples are preserved but are now reported separately and no longer mixed into language quotas.

- **The full run now writes its own measurement report for each language.** Without a language switch, German and English are deliberately checked; `--alle-sprachen` requests the full twelve-language corpus and aborts before the first document if a language or a case is missing. Identically named results sit in separate language folders. The overall report now names, alongside the weighted find rate, also the unweighted average of the language rates.

- **The open language comparison now also shows its actual limit.** In the regular run with text recognition, German and English remove 218/218 known items with no false positives. The full test with text recognition and the high tier removes 1,255/1,308 items with 17 false positives; eleven languages reach 100 percent, Hindi 51 percent. Earlier full rates were based on unequal document and target counts and are not comparable with the new matrix.

## 0.10.34-alpha.20260819 – August 19, 2026

### Fixed

- **Names occurring multiple times remain reachable in the sidebar after a single restoration.** Previously, the whole name row disappeared already after the first restored `[NAME]` spot. Further spots of the same name thus remained as placeholders and were sometimes even blocked until other names had been restored. The row now only disappears after the last spot; already-restored plain text is nevertheless not automatically anonymized again. This also applies to a partially successful bulk restoration and to the frame tool in PDFs.

- **"Undo replacement" also works from the Office page preview.** The visible page there is only a transient PDF preview; what now gets correctly changed is the underlying Word, spreadsheet, or presentation document, with the preview refreshed afterward.

- **Restoring now also fully retrieves the hidden counterparts of a value.** In Word, OpenDocument, Excel, and PowerPoint files, the same data can additionally sit in formulas, comments, charts, field values, alt texts, and hyperlink targets; HTML, EML, and MSG also carry them in attributes, JSON, message headers, and attachments. Previously, depending on the format, a part remained as a placeholder there. Now every item offered in the hit area can be restored independently and in any order. Deliberately removed metadata, revision histories, and transport headers remain removed for security reasons as before.

- **When restoring from images, no black border line remains anymore.** The right and bottom edges of a frame were laid out one pixel too tight each when copying from the original. The coordinates now match the redaction.

### Improved

- **The release check now sends every one of the 22 supported file extensions through a full round trip.** Content-rich files are cleaned, all offered values are restored, and then deeply checked. Added to this are genuine sidebar operation, pixel-precise image comparisons, and a visible LibreOffice render of all seven office formats. The small regression tests remain in place where they cover their own bug or security case; a demonstrably duplicate HTML check and the test of the removed black-and-white mode have been dropped.

- **The full measurement corpus of this version is available for re-measurement.** The package contains 294 synthetic documents in twelve formats and twelve languages, 2,564 known items, four machine-readable target lists, and a guide. The download on the quality page uses a content-dependent file name so browsers don't accidentally serve an older version from the cache.

## 0.10.33-alpha.20260819 – August 19, 2026

### New

- **Individual spots can now also be restored from the original in image files.** The frame tool "Restore original" copies the pixels at the same position back from the untouched source file. The path stays blocked if the source is missing or has different image dimensions; this prevents content from a shifted spot from being inserted.

### Improved

- **Manual redaction bars now snap to text lines by default.** A drag across several lines produces a uniformly high bar per line and leaves the whitespace in between free. For signatures, graphics, and other special cases, "Free frame" switches back to a self-chosen height.

- **The editor now explains the next step directly above the document.** The notice changes with document type and tool and says whether a word click, a text selection, or a frame is expected. Additionally, the tool, mouse cursor, and live preview already show what will happen before you let go.

### Removed

- **The error-prone black-and-white output has been removed.** With some PDFs, invisible text fields remained shifted relative to the rasterized page; the apparent file-size reduction was not worth this safety and display risk. Normal PDF cleaning and the targeted rasterizing of problematic pages remain.

## 0.10.32-alpha.20260819 – August 19, 2026

### New

- **Folder monitoring now really runs in the background.** Inbox, outbox, and rules sit on their own page under "Settings." It is started and stopped via the Maskuro icon in the taskbar or menu bar; the entry only appears with the license unlocked for it. The settings window can then be closed and the main window minimized to the icon without ending monitoring.

- **The touch-up editor now has a persistent learning-mode switch.** It sits in the hit area and in the "Tools" menu. When turned off, no questions about creating custom rules appear either when restoring or after manual corrections. Maskuro remembers the choice for all documents opened in the future; restoring itself works unchanged.

### Fixed

- **The large additional model can be downloaded again.** The public storage rejected Python's generic default identifier with 403. Model downloads now use the same dedicated Maskuro network path as the other in-house services; the roughly 596 MB file and its checksum remain unchanged.

- **A maximized comparison magnifier no longer gets stuck as a narrow bar at the top edge when docking.** Its free window state is normalized before docking. A saved maximized state is also returned to a resizable size the next time it opens.

- **A bulk restoration in tables and other text formats now genuinely retrieves all selected values.** With anonymized placeholders such as `[EMAIL]`, Maskuro previously wrote the values one after another. As soon as the first was replaced, the numbers of all remaining hits shifted forward, but the already-computed plan still pointed to the old numbers. As a result, only part of the selection came back. Now all chosen values of the same placeholder are written together with stable hit numbers. If a spot only becomes unambiguous through another restored value, Maskuro re-checks it in the same pass — the order of the selection no longer matters.

- **"Undo replacement" no longer skips selected values in PDFs.** If a placeholder stood very close behind another word, or a comma hung directly against the value in the original, the position check could mistakenly attribute the neighboring word or punctuation mark to the value. During joint restoration, individual placeholders and hit rows then remained. The check is now aligned to the actual start of the word and also accounts for a differing page rotation between the original and the result.

- **Restored PDF text now keeps its original size.** Previously, the already-smaller-set placeholder served as the scale; in addition, the 11-point upper limit intended for placeholders also applied to the original text. Now the original box and original font size are taken from the source file — both with the frame tool and when restoring from the hit panel.

### Improved

- **The review notice now names the residual risk more clearly.** It explicitly states that Maskuro can overlook data or handle items incorrectly, and calls for a complete review — and manual correction if necessary — before any publication or handover. This also applies to text from the clipboard and has been fully carried through in all 17 translations.

- **The verification log now also starts without a username inside its rows.** The log itself remains switched off until an organization deliberately activates it. Afterward, without an additional company policy, neither a row nor the name of a central monthly file carries a username; a non-guessable pseudonym, derived only from the random local profile secret, serves there for secure separation. The license dialog no longer recommends activation, assumes "Without log" by default, and points out in advance the works council, staff representation, and privacy considerations.

- **Replace now names what it replaces.** A marked name becomes `[NAME_3]`, a place becomes `[ORT_1]`, a phone number becomes `[TELEFON_2]` — instead of everything becoming `[BEGRIFF_n]` as before. The type is recognized on click; if it is not unambiguous — an ordinary word, or a name *and* a place within a selection — it stays with the generic term. A placeholder that claims a type that isn't correct would be worse than one that names none.

- **The tools in the touch-up window now have a key.** **S** (schwärzen) redacts, **E** (ersetzen) replaces, **Z** (zurückholen) restores the original, **V** (verpixeln) pixelates. In the text view they act immediately on the selection; in the page view they select the tool. **The letters follow the language** in which you operate the program — English B/R/O/P, Italian O/S/R/P — because a mnemonic only helps in one's own language. The key is shown on the button. Anyone currently typing in the search bar continues to type letters; they don't trigger there.

- **The program reports once a day in what state it is running — without any identifier.** This lets us count how many installations are in use and how that breaks down across trial period, free tier, and license. What goes out is state, operating system, version, channel, country, language, environment, and detection tier — **nothing about your documents and nothing by which your computer could be re-identified**. Two reports from you look to us like reports from two different people; no single path can be traced from them. What exactly is sent and how it can be turned off is stated in the privacy text under point 5.

- **Sideways-scanned pages now stand the right way up by themselves.** A sheet that was scanned crooked without recording it is detected by touch-up via the text flow, and the view is straightened. Where that isn't possible — with a pure scan with no legible text — two new entries in the "View" menu rotate it by hand (Ctrl+Shift+L and Ctrl+Shift+R). Only the display is rotated: nothing changes in the file itself, and redacting still hits exactly the spot you click.

- **The local build now carries its licenses completely and visibly.** The build determines the actually bundled Python packages, places their license texts along with a version overview under `lizenzen`, and aborts on any gap. Qt, Tesseract, and the face model also have their required texts; the terms for Maskuro itself are included as a license agreement.

- **You can now see which placeholder the caret is standing in.** Anyone clicking into a placeholder sees it light up completely — brackets and number included. The "Restore selection" button already activated on a mere click before; it just wasn't visible which marker it had caught. The glow also remains once the mouse moves to the button.

- **The mouse cursor now says which tool is selected.** Four tools share the same area and the same gesture; until now each looked the same. Crosshair means redact, closed hand means replace, open hand means restore.

- **A tampered Office document now gets rejected by the program itself.** A Word, Excel, or OpenDocument file can carry instructions that, upon opening, pull a foreign file from your computer into its text or fill up memory. Both were already rejected before — but by the built-in XML library, not by Maskuro. The program now decides this itself, independent of which version of that library sits in the package. Nothing changes for ordinary documents.

### Fixed

- **The hit panel now removes redacted placeholders.** If, say, `[NAME_1]` was redacted in the touch-up window, its value row previously remained on the right, even though no such spot existed in the document anymore. The row now disappears with the last hit; if the same placeholder still occurs at another spot, it remains.

- **When restoring on a rotated page, the neighboring word now stays put.** The redaction bar deliberately extends a little beyond the text; even this narrow margin could previously carry along an adjacent word like "im." Now only a clear overlap counts, not a touch at the edge.

- **A second replacement in the same line took the following text along with it.** Anyone who replaced "Sachbearbeitung Quaxi Blubbo übernimmt" twice in a row got "Sachbearbeitung [ORT_1] [ORT_2]" — the word after it was gone without replacement, with no notice at all. The cause was the placeholder next to it: the rest of the line begins with a space after the first replacement, and the search for its text position grabbed the neighbor's closing bracket. After that, everything was shifted by one character. This affected every line where a second replacement or redaction occurred — including when restoring next to it.

- **Replace no longer redacts when the placeholder is too long.** If there was no room next to the word for `[BEGRIFF_2]`, the area was previously painted over in black — and with that it was no longer even visible that something had once stood there, let alone restorable. A shorter notation is now written: `[BEGR_2]`, `[BE_2]`, if necessary `[B_2]`. The running number remains at every stage — restoring finds the spot again by it. Only where even the shortest form doesn't fit does it stay with the bar.

- **Replace left the text standing if the same line had already been redacted.** Anyone who, in the touch-up window, restored a name from the original, then replaced the first name from it (there was no room — a bar resulted), and afterward replaced the surname, got the placeholder inserted but the name was **not removed**. This only came to light through the review's warning. The cause was the line itself: after the first redaction, its remainder begins with a space, and the search for the text position found no foothold there. This affected every second redaction in the same line.

- **An enabled advanced-detection tier without its model now shows up.** The checkbox could be set while the model was missing — settings apply to every installation, but the model sits alongside the program. Cleaning then ran without the tier, with no word about it. The checkbox now says the model is missing, and the result carries a warning. Your once-made choice remains saved: as soon as the model is loaded, it takes effect again.

- **When anonymizing, the correct term is now restored.** Anyone who manually replaced several terms and then restored one of them always got the **first** one back — "Schmidt" became "Müller." The mapping only remembered one replacement per placeholder, and with anonymizing, all of them carry the same placeholder; the second and every further term was dropped as a result. Now every value gets its own row — including in the list of replacements, which was previously too short.

- **Restoring in tables now works too.** In a CSV or personnel list, the placeholders stand directly next to each other, separated only by a semicolon. Until now the program couldn't determine there which value had stood where, and refused — it worked with `[NAME]`, but not with `[GEBURTSDATUM]` and `[TELEFON]`. It now splits the line at all placeholders. If a spot really remains ambiguous, it still refuses: an incorrectly written-back value would be worse than a missing answer.

- **And the refusal is now visible.** It previously stood in muted gray at the bottom edge of the window, and the sentence was so long it got cut off — it looked as if nothing was happening at all. The sentences are shortened, and the row now glows in the warning color for a few seconds.

- **A restoration now also holds after the next action.** Anyone who, while anonymizing, restored several spots and then replaced something else found all the restored spots replaced again and had to start over. The cause was the mapping: it kept the value, and the automatic matching for consistent placeholders retrieved it on the next write. Now: what you restore stays restored — other spots of the same value are not touched by this.

- **In text, Word, Excel, and email files, a single click into the placeholder now really is enough.** The message about this already appeared in the previous version, but the "Restore selection" button remained locked as long as nothing was precisely selected — so you never even reached the path that would have set the selection itself.

### Fixed

- **The verification log no longer reveals the file name.** It deliberately carries files as a hash value instead of in plain text, because a file name reveals the client and the subject matter. But this hash could be confirmed by guessing — a path is not a random number. Now a random value specific to this installation goes into the calculation: counting and distinguishing within the log still work, but confirming it from the outside no longer does.

## 0.10.31-alpha.20260819 – August 19, 2026

### Improved

- **In text and table files too, the placeholder now lights up red when hovering.** Previously the red preview only existed on a PDF page. Now both views show the same thing: what is red is what the next action hits — and a click into it is enough to restore it.

- **A click on a word is enough — the editor draws the rectangle itself.** In the touch-up window, you previously had to drag a rectangle over every spot. Now a click suffices: the frame lays itself around the word and remains graspable, so it can still be resized or moved. When pointing with the mouse, the word already lights up red, so you can see beforehand what the click would hit. Where there is no word, you still drag a frame as before.

- **You no longer need to aim the rectangle precisely.** Anyone dragging a rectangle over a placeholder or a redaction always means the whole spot — never half of it. The frame therefore automatically grows to cover the whole thing it touches: the whole placeholder, the whole bar, or, on a scanned sheet, the whole redacted area. It never becomes smaller than the dragged frame.

- **Redacting now happens word by word.** A frame over half a word previously only redacted that half — and a half-redacted name is still a name. Touched words now fall entirely; the neighbor remains untouched.

- **In text and tables, a click into the placeholder is enough.** "Restore selection" previously required precisely selecting the placeholder along with its square brackets. Now it's enough to place the cursor inside it; the selection visibly jumps to the whole placeholder.

- **Belgium has been added as a country.** Selectable in settings; Belgian phone numbers, the Rijksregisternummer (with check digit), the BTW/company number (with check digit), addresses in both official languages, and the postal code with city are then recognized. Previously, Belgian phone numbers remained because the country wasn't in the catalog at all.

- **The update channel now says how early you get new things — not how far.** Anyone on "Testfassung" (test build) previously wasn't even offered a new preview or a new stable version and had to switch channels by hand just to learn about it. Now everything more reliable is also offered: test build takes test builds, previews, and stable versions; preview takes previews and stable ones. Never the other way around — a test build is never offered on preview, even if it is newer.

- **In the settings window, the rows are spaced further apart again.** The four pages used their own spacing instead of the grid that applies in the rest of the program; especially on the "Detection" page, the checkboxes were noticeably too close together as a result.

### Fixed

- **Filled-in PDF forms no longer appear empty during manual editing.** For this, Maskuro turns exclusively the transient working copy into static pages: entered values become visible and can genuinely be redacted; readable form fields no longer remain hidden in the file. The original stays interactive and unchanged. This now also applies to dynamic XFA forms: an XFA-capable PDFium first builds values and page breaks, after which a new PDF is created consisting solely of static image pages. If the XFA build fails, the file is safely rejected instead of appearing deceptively empty.

- **"Cancel" now also works during more precise detection.** Previously the button locked itself on click, but the run kept computing to the last block — for a long file that's minutes with no way out, and the button looked as if it had worked. The run now ends at the next block.

- **In CSV files, names are now also found when there is no space before them.** In `P-1000;Brunnthaler, Elisabeth`, the personnel number sticks to the name across the semicolon, and for detection this was a single word with no name inside it — in personnel lists, depending on the line, this left the whole name standing. Phone numbers, formulas, and the file's column count remain unaffected by this.

- **A name whose first and last name both carry a hyphen is now recognized.** "Marie-Luise Habsburg-Ott" remained in the middle of a sentence, while "Dragan Mitrović" in the same sentence was found — of all things, the combination of two hyphenated halves was overlooked by the language model. Hyphenated factual compounds like "Nord-Süd-Verbindung" or "Software-Entwickler" remain unaffected by this.

## 0.10.30-beta.1 – August 18, 2026

### Improved

- **The font size of the text view can now be visibly adjusted.** The slider at the bottom right, which previously only zoomed in the page view, now sets the font size (50–300%) in the touch-up window for text and Office files — as does "Zoom in"/"Zoom out" in the View menu. Ctrl+mouse wheel could always do this, but only those who had tried it knew; now the slider, the display, and the wheel work together.

- **In dark appearance, a white sheet now lies on a dark work surface.** It used to be the other way around: a bright area remained around the sheet, and the text itself stood bright on dark. The sheet now stays paper-white with black text in both appearances — like a PDF page, which doesn't turn dark in dark mode either — and the surrounding area is dark.

### Fixed

- **After a redaction in the middle of a sentence, the rest of the sentence no longer gets lost.** Anyone who went to the same spot three times in the touch-up window — replace, redact, then "Restore original" — got the start of the sentence deleted: "Rückfragen richten Sie bitte an das Rechnungswesen." became "bitte an das Rechnungswesen.," without warning. This affected every spot where something had once been removed from the middle of a line.

- **A startup error no longer takes exiting down with it.** When the main window's build process aborted, exiting via the taskbar icon afterward crashed too — and this second error hid the actual cause in the error report. The program now exits cleanly even from a half-built window, and the saved settings remain untouched.

- **"Before/After" no longer jumps back to the start of the document.** Anyone who had scrolled down in the touch-up window and switched to the original for comparison landed back at the very top — and had to find the spot by hand again. The view now stays on the same line, in both directions.

- **The last letter remained next to the redaction bar on justified lines.** When a text command draws more glyphs than the reading library reports characters — it likes to swallow a space in justified text — the mapping shifted by one, and "Dr. Michael Handler aus Willendorf" became "[NAME] r aus f": two leftover letters in the middle of the cleaned sentence (found in a real council record). The mapping is now cross-checked against the command's actual wording wherever it is readable — it is no longer guessed there.

- **"Lerchenfelder Gürtel 43/12" was only half removed.** The address patterns knew neither Gürtel, Kai, Lände, Zeile, Markt, nor Graben as a street base word, and the house number was not allowed to carry slash parts (43/12, Haus/Tür) — the number remained next to the placeholder. Both added; Viennese and Salzburg addresses now fall entirely.

- **Saved web pages remain functional after cleaning.** The addresses that lazy loading stores in data attributes (`data-lazy-src`, `data-lazy-srcset`) were replaced as links — sixteen of them on a real municipal page — and the page's images no longer loaded afterward. Web addresses now remain there, as in `src` and `href` too; names, email addresses, and phone numbers in data attributes continue to be replaced.

- **Japanese and Korean documents ran as Chinese.** Language detection lumped all three scripts together, found no function words in Japanese text (no spaces) or Korean (with attached particles) — and simply took the first CJK language of the catalog. A Japanese council record and a Korean meeting record were thus read with the Chinese model. Now the script itself decides: kana means Japanese, hangul means Korean.

- **Further misses from field testing in ten further languages:** offices such as "Primar," "Gradonačelnik," "Ordfører," "Başkanı," or "Δήμαρχος" no longer count as person names; Turkish field labels ("Adı," "Soyadı") and Greek conversational words ("Ωραία," "Βεβαίως") no longer fall; resolution and paragraph numbers with a date ("323/25-6-2008," "27 30.09.2024") are no longer phone numbers; and sentence fragments with a period ("10.An," "T.U.EE," "…pa") are no longer replaced as web addresses.

### New

- **Verification reports automatically, on request.** A checkbox in settings (page "Program") automatically saves a verification-report PDF after every cleaning — with a timestamp in the name, in its own folder, never next to the result. A sheet cannot be generated after the fact; anyone who needs it for the record thus always has it. This is off by default.

- **The verification log can now be turned on within the program.** When reading in a business license, Maskuro asks once whether the log should be kept — a record only carries weight if it runs from the very beginning. There is a switch for this in settings (page "Program," visible with a business license or during the trial period); the administration's policy file still applies and can force the value as before. A dedicated log row "enabled" records since when logging has run — this also documents and signs the start of recording. The log remains off by default.

- **The statistics panel shows what the AI tier did.** A new row states how many uncertain hits the model judged, kept, and discarded, and how many it additionally found — previously its work was invisible unless you clicked every value in the touch-up editor. Only numbers, never values or justifications; the row does not appear without AI work.

- **Restoring now also works in emails and HTML pages.** In `.eml`, `.msg,` and saved web pages, a placeholder previously could not be restored — the application said so honestly, but email is exactly the format with the most personal data. Restoring now works there just the same: from the hit panel, with a marked selection, and even with anonymized placeholders. The invisible HTML branch of an email (what Outlook actually displays) is carried along with it, so the view and the message say the same thing.

- **The hit panel now also restores anonymized values — per value.** "Undo replacement" was previously locked for anonymized files, because "[NAME]" stands for all names at once. Restoring now looks up in the original which spot belongs to which value — in a PDF via the coordinates of the hit, in the text view via comparison with the original — and retrieves exactly the spots of the chosen value. The rows of the other values remain.

- **Anonymized placeholders can now also be restored individually.** When anonymizing, all items of one type carry the same name — "[NAME]" stands for every person — and until now the rule was: restoring individually doesn't work. It now looks up in the original, which sits next to the result anyway: mark the placeholder in the text view and choose "Restore selection" — exactly this spot comes back with exactly its value. If the value cannot be read from the original beyond doubt, the application says so instead of guessing. A mapping file still does not get created in this process.

- **The touch-up window now opens by itself after cleaning.** No tool finds everything — so the reviewing glance at the result belongs to the normal case, not an extra click. Anyone who doesn't want this turns it off in settings under "Detection" ("Show result in touch-up window afterward").

### Improved

- **Country selection now defaults to "automatic."** Previously the interface's language region applied by default — so on a German-language computer, even Dutch or French documents were only cleaned with the DACH detectors, and an address like "Universiteitslaan 1" remained (found in real, public council records). Country selection now follows the document's language; anyone who has made a fixed choice in settings keeps it.

- **Less false redaction.** A number of misses, measured against the test corpus and against real meeting records in six languages, are eliminated: company names with a legal form ("Musterfirma GmbH") no longer count as a person or a place, but as an organization; closing phrases and bare salutations ("Saygılarımızla," "Buenas tardes," a standalone "Frau") are no longer names; offices ("Bürgermeister," "Sindaco," "Alcalde") remain; law and resolution numbers ("39/2015") and amounts with a thousands separator ("330.000") are no longer phone numbers; sentence starts like "Envíame" or "Estarei" no longer fall as a name; a hit spanning an empty line no longer counts as a name. An invoice's invoice number remains as a receipt item — customer number and case number continue to fall.

- **Before loading the AI model, it is now stated what it is good for.** The download dialog names the model's tasks — judging borderline hits, finding additional names, suggesting rules and profiles — and openly states that it is not a chat assistant. The FAQ answers the same question in detail ("What can the AI tier do — and what can't it?"), in all language versions.

### Fixed

- **Verification-report PDFs from the command line can now be searched.** On Windows, the headless PDF path started without a single font — every character was drawn as a placeholder box, and the sheet carried no readable text: anyone wanting to search in it or copy something out found nothing. The report now downloads the system's fonts in that case; the text is embedded and readable. Reports produced from the window were never affected.

- **"Restore original" across several lines of a scan left black stripes between the lines.** On a page converted into an image, the frame only cleared the line bands themselves; the remnants of the earlier redaction remained in the gaps between them. The dragged frame now splits fully across the lines.

- **A second frame over a placeholder left a red remnant.** The placeholder is almost always wider than the word it stands for; anyone who then redacted over the same spot only hit its beginning — a fragment like "RIFF_1]" remained in the middle of the sentence, and restoring afterward inserted the original text at its spot instead of the word's. A clipped placeholder now always falls entirely.

- **On a rotated page, redacting over a placeholder deleted an unrelated sentence.** The subsequently drawn placeholder was mistaken for the text before it when removing: it itself remained, the warning "still in the document" appeared — and elsewhere on the page, a sentence that had nothing to do with the frame disappeared without replacement. A placeholder is now re-found via its wording; the "replace, redact, restore" chain thus also works on rotated pages.

- **The manual still advised installing `python3-tk` in ten languages.** In troubleshooting, it stated that tkinter might be missing under Linux — advice from before the Qt interface that no longer helps anyone. All versions now carry the same paragraph as the German one: the missing pieces are the system libraries that Qt needs for display.

- **The license chapter of the manual was outdated in all sixteen translations.** In ten languages one could still read there that Windows Server requires a business license with server access, and that there is no free tier there — since a seat counts a person and not a machine, both statements are wrong. Also missing everywhere was information on when an occupied seat becomes free again, that the license confirms itself regularly and what is transmitted during that, and offline activation only appeared as a short version without the three steps and without the note that the computer then works for a year without a connection.

- **Seven paragraphs about touch-up were missing in ten languages.** Anyone reading help in Danish, Finnish, French, Italian, Dutch, Norwegian, Polish, Portuguese, Swedish, or Spanish found neither the page preview for Office files, nor "Manual redaction," nor the whole section about how the program learns from a correction — including the table with the three widths. In "What is detected," the same ten versions were missing the path via the label in the document.

- **With a license read in, the program no longer started.** Instead of the window, "The program could not be started" appeared — for every license, regardless of which. The cause was the line in the license display that warns shortly before the trial period expires; it accessed something that wasn't available there. Without a license — during the trial period and in the free tier — the error did not occur, which is why it only came to light now.

- **In the form, the field names now remain.** "Geburtsdatum" and "Anschrift" disappeared along with their value: the placeholder stood small and red at the spot of the *field name*, and the field below it remained empty. The field name is not part of the data — it now remains, and the placeholder appears where the value stood.

- **Document titles in foreign languages are no longer mistaken for names.** Above an Italian form stood "FATTURA," above a Spanish one "PERMISO PARENTAL" — both were replaced. The list of document-type words only knew the German equivalents.

- **No item disappears from an invoice anymore.** "Materialaufschlag 1  84,00" was mistaken for an address and replaced with a place placeholder — the receipt was afterward missing a line. A line ending in an amount is an item, not an address; genuine addresses ("Hauptstraße 1  120,00") remain unaffected.

### Changed

- **"Monitor folder …" and the command line are gone for the time being.** Both paths are built and running, but neither has been tested at scale: folder monitoring has never seen a Windows pass, and the command line hands a script two dozen switches that have never run for any user. Something that changes documents unsupervised shouldn't do so unchecked — that is why they have been withdrawn until the pass is caught up on. The menu entry is gone, and `--wache` no longer appears in `maskuro --help`.

- **What remains is what only reads and what is needed regardless.** The search run (`--suchlauf`) and the check (`--nachpruefen`) continue to work on the command line — they change no file. Likewise, launching via Explorer, the context menu, the clipboard, and the window — nothing changes there.

- **"Get from scanner" now has its own chapter in the manual.** It previously stood at the end of "Monitor folder." On the Mac, the advice there used to be to have a folder monitored; it now says to drag the scanned pages into the window.

### Fixed

- **"Restore original" across several lines destroyed the layout.** A frame over a placeholder, an unchanged job title, and a second replacement re-inserted the whole area as **one** line — three lines became one, and whatever no longer fit turned into a bar. Every line is now restored separately.

- **And unchanged text remains untouched in the process.** Anyone dragging over a replacement *and* ordinary text gets back only the replacement; the rest is not touched. The last remnant of the old placeholder also disappears in the process — previously its closing bracket remained in the middle of the sentence.

- **When replacing, no remnants of the old text remain anymore.** In a bold heading, "1. R[BEGRIFF_2]ige [BEGRIFF_1] … che" previously remained — the placeholder sat there, but syllables of the original next to it too. What is now cleared is the area you frame, not just the boxes of the words inside it.

- **An anonymous placeholder is no longer restored.** When anonymizing, every name carries the same `[NAME]`. Restoring took the first-best entry and wrote it at every hit — "Georg Aigner" became "Anna Musterfrau," a wrong name in the document. It now states that it can no longer be said which item was meant; the document remains untouched.

### New

- **"Restore original" now also works on a rasterized page.** If a page had been converted into an image, a refusal previously followed: the restored text would land underneath the page image. The spot in the image is now cleared and the text is written on top of it — like a placeholder on a scan. The content comes from the original file, and that is not rasterized.

- **"Restore selection" now stands as its own button.** It already worked before, but only if you happened to mark a placeholder and pressed "Replace selection" — a function you can only find by accident doesn't exist for the user.

### Changed

- **In plain text, CSV, and Outlook messages, there is no longer a "Redact selection."** These formats cannot carry a bar; the button there set a placeholder and said so too — but a button that does something other than its name doesn't belong there.

- **A tool now says when it has nothing to accomplish at this spot.** A placeholder cannot be replaced again, no placeholder is set over a redaction, and where the original already stands, there is nothing to restore. Previously these moves did something that looked like an effect, but wasn't one.

## 0.10.29-alpha.20260817 – August 17, 2026

### Fixed

- **In the touch-up window, every frame you drag now takes effect.** Anyone working on the same spot twice — first replace, then redact, then restore the original — had their second and third moves fizzle out silently: the still-graspable frame of the previous move caught it. The same happened when switching tools, where the old tool even kept working silently.
- **A frame dragged too narrow now says that it is too narrow.** Previously the preview lit up a word red, and letting go silently did nothing.

- **Outlook messages can finally be touched up.** A `.msg` showed "This format cannot be displayed here" in the touch-up window — it was the only supported format with no path at all for manual rework. Sender, recipient, subject, and message body now appear named in the view and can be selected and replaced like in any other text format.

- **"Replace selection" now stays with the selection in an email.** Anyone who marked a name in the running text also lost the sender and recipient from the headers, and the message named a different placeholder than the one that stood in the text. The marked value is now replaced everywhere — including in the sender field, if it stands there — and nothing else is touched.

- **A frame across several lines no longer destroys the text.** Previously a single placeholder resulted at one spot: a remnant of the clipped word stuck to it, and the text disappeared from the second line without replacement — no placeholder, no bar, just a gap. Every line now gets its own placeholder with the value that actually stood there.

- **"Restore original" now also works after a redaction.** The window reported success, and the text never came back: the black bar counted as an obstacle, so there was no longer room for the restored text. The bar now yields, and the restored text stands black like ordinary text — not red like a placeholder.

- **"Restore original" on an untouched spot no longer does anything.** Anyone who dragged the frame over text where nothing at all had been changed got the text removed and reinserted smaller and shifted — success was reported. It now states that there is nothing to restore there.

### New

- **Word, Excel, PowerPoint, OpenDocument, and text files can now also be redacted.** Previously only "Replace selection" existed there; a bar was reserved for the PDF view without any reason for it. Where a bar cannot be displayed — in plain text and in an Outlook message — the value continues to be replaced by a placeholder as before, and this is also stated in the message.

- **Marking a placeholder restores it.** In the text view (Word, Excel, PowerPoint, OpenDocument, text), it is now enough to mark the placeholder and press "Replace selection": the original value comes back. Previously the window referred to the hit panel for this.

- **Speakers in a meeting record are now recognized even when their name is also an ordinary word.** "Gruber: Die Abnahme erfolgt kommende Woche." was replaced, "Bauer: Ich stimme zu." remained — the surname looks to detection like a common noun. Note lines of the same pattern remain untouched: "Achtung: Die Anlage ist abzuschalten." does not become a name.

- **"You are using the latest version" was also stated when it wasn't even possible to check.** If the update server rejects the request — because too many requests came from the same internet address, or because it is itself disrupted at that moment — the program stood still on its old version and claimed it was the latest. This is exactly what happened on a Mac on August 17: 0.10.25 remained stuck while 0.10.28 had been ready for hours.

  The window now says what's going on, names the time of the next check — and explicitly points out that it is **not** established whether one's own version is the latest.

  Usually this isn't the fault of one's own computer: with many internet connections, numerous customers share the same address, and the server counts them together. That's why Maskuro searches the version list via a **second path** in this case and mostly still finds new versions anyway. If the refusal persists, the server is left alone until the stated time — even if the button is pressed again; nagging only extends the block.

- **Quantity statements are no longer mistaken for place names.** In a service contract, "Vier-Tage-Woche" disappeared behind a place placeholder — right in the middle of the contract's subject matter. Such word combinations of number and hyphen ("Drei-Punkte-Plan," "24-Stunden-Dienst") now remain. Addresses are excluded from this: a "Zwei-Brüder-Weg" continues to be replaced.

## 0.10.28-alpha.20260817 – August 17, 2026

### Changed

- **License seats are now genuinely counted.** Previously, not a single workstation ever registered with the license service — a ten-seat license ran on any number of computers without anyone finding out. New: the computer that starts the program takes a seat; a seat becomes free again by itself after **seven days without a launch**, so a broken device or a departed employee never permanently blocks anything.

  A small overrun is **only displayed and not blocked**: up to ten percent above the purchased number, everyone keeps working — the new laptop next to the still-registered old one shouldn't be a case for the helpline. Anyone joining beyond that falls back to the free tier and is told so; the computers that were there first notice nothing of it.

- **A purchased license confirms itself regularly.** If that fails to succeed for **30 days**, the free tier applies for as long as it keeps failing. Nothing is switched off, and starting a week beforehand the notice appears in the window. As soon as the computer reaches the internet again, this resolves itself. The trial period and free tier continue to report nothing at all — anyone who never buys never phones home.

- **"Activate without internet" finally works.** The activation was previously checked and stored, but afterward read by no one — it changed nothing about the rights. It is now the way out for computers without network access: it carries for **one year**, after which a fresh request code gets you a new one. A device with internet is needed for this once a year — the computer itself stays permanently offline.

- **Activation is now also possible from the customer account** — under "My licenses" on the website. It also states which computers are attached to your license and when their seats become free again — previously visible nowhere. The page without login remains for anyone without shop access — it additionally requires the email address from the order for this, so the license key alone is not enough.

- **And the window now states where to take the request code.** The paper instructions said "enter it on a device with an internet connection" and named no address; the activation page has existed for a while, but was linked from nowhere. **maskuro.com/lizenz-freischalten** now appears in the dialog, in the manual, and in the FAQ — and on the website below the license key.

- **The "Activate without internet …" button stays visible**, even when the license currently doesn't apply. Previously it disappeared along with it — exactly when you need it.

- **"All seats occupied" now tells the truth.** The notice ended with "The program continues to work unchanged"; that is no longer true if no seat was assigned. It now states that the free tier applies until further notice.

### New

- **When turning on clipboard cleaning, it is now noted that a review is needed.** The message has since carried the same sentence that also appears with a file's result: Maskuro does not detect all personal data in every case.

  Here it weighs heavier than elsewhere. With a file, you see the result before passing it on. Not with the clipboard — you copy, paste, and the cleaned text already sits in the mail window. The message therefore explicitly says to review the **pasted** text.

  It appears when turning it on, not on every copy operation: what would appear fifty times a day, nobody reads anymore after the third time.

- **"Copy all" below the list — and "Remove all" moves away.** The new button places all finished results into the clipboard at once, for attaching to an email or pasting into another program. Previously this only worked via the menu and even there only for the **selected** rows — anyone who meant all of them first had to press Ctrl+A.

  The button row has been reorganized in the process: on the left is what adds something, on the right, behind a gap, what removes something. "Remove all" previously stood immediately next to "Add …," and a slip cost the whole list. The same rule has applied to every finished row since August 13 already.

- **Workstations without internet now get their language models from in-house.** Cleaning there always worked without a connection — downloading a language model didn't, and a model weighs several hundred megabytes.

  Administration assembles the files once on a computer with a connection and places them on a share, in the rollout, or on a USB stick. The location is entered centrally (the `modellquelle` field in `vorgaben.json` or the `MASKURO_MODELLQUELLE` environment variable). From then on, every download serves itself there first — language models, the Japanese dictionary, and the high tier — and only reaches out to the internet if a file is missing.

  The checksums apply unchanged in this. An in-house file share is often easier to describe than a release on the internet; it should not become the more convenient path to a smuggled-in model.

  How such a stock is built and how licensing and activation work without internet is described in `OFFLINE.md`.

- **"Restore original" — a frame retrieves what was removed too much.** The touch-up window has a new tool: drag a frame over the spot, and the text stands there again as it did in the original.

  This closes the gap the hit panel left open. There, a replacement could only be undone if its placeholder was unambiguous — so not when anonymizing, where "[NAME]" stands for every item of this type, and not at all for redacted spots, where no placeholder remains. It is exactly there that the misses pile up: "Benutzer," "Inventarnummer," "Unterschrift" are gladly mistaken for names.

  The frame doesn't need the placeholder: the **spot** comes from the rectangle, the **content** from the original file — the same one the before/after toggle shows. Anonymized or pseudonymized no longer matters as a result.

  The restored text stands black, not red: it is plain text again, not a placeholder. An entry disappears from the hit list only once its placeholder no longer stands **anywhere** in the document — if the same value was replaced in several places, it remains for the others.

  On a page that was converted into an image, the tool refuses and explains why: the restored text would land underneath the page image and would not be visible.

### Fixed

- **When collapsing "Details" and "Statistics," image remnants remained on screen.** When collapsed, part of the content slid under the bottom window edge and remained there over the background until something else happened to be drawn over it.

  Both areas have a minimum height so they are usably large when open. But the collapsing animation only reduced the maximum height — and an area does not shrink below its minimum height. The content thus remained 200 points tall while the window was already contracting to 24; the difference sat below the edge. The minimum height now yields for the duration of the animation and returns afterward.

- **The window kept getting smaller with repeated expanding and collapsing.** When expanding, it grows at most to 92% of the screen height; if space is tight, it grows less than needed. When collapsing, it nevertheless subtracted the full amount again. It now gives back exactly what expanding cost.

- **A remnant of a redacted item could remain visible.** In a résumé, the characters "*30.1" from "*30.12.1991" remained legible in the result — the day and start of the month of the date of birth. The program had even noticed the remnant and therefore converted the page into an image; that made it worse, because it made the remnant no longer searchable, but still readable — and no longer fixable.

  The cause lay between two checks. The stricter of the two checks whether something that doesn't belong there still stands in the area of a removed item; it reports its finding as a character set, because the reading order shifts during replacement. The fallback that paints over such spots before converting searched for this character set as text on the page — and never found it. So nothing got painted over. The spot was known the whole time and is now passed through instead of being searched for anew.

  This affected every page whose remnant was found solely by this check — regardless of file type and language.

- **On a sideways-fed scan, text recognition found nothing.** Anyone feeding a sheet sideways into the scanner gets a file in which the text sits rotated 90 degrees. Previously Maskuro read **not a single** item in it — and the file afterward looked unremarkable: nothing was found, so nothing was reported, and the address remained legible in the image. Text recognition now straightens the page itself; on the test image, all items fall again.

  Two limits stated openly: a sheet standing **upside down** (180 degrees) still isn't read, and with a very poor scan, straightening doesn't help — there's too little legible to determine the orientation at all. Each image takes about a fifth longer for this.

### Changed

- **"Install automatically" now means what it does.** The checkbox in settings promised more than it delivered: it downloads the new version by itself and starts the installation — but that runs **visibly** and wants confirmation, on Windows including a User Account Control prompt. Anyone reading "automatically" expected a computer that updates itself overnight and stood in front of the installation wizard in the morning instead. The checkbox is now called "Download updates automatically and start the installation," with a sentence below explaining what that means. Nothing changes in behavior — that Maskuro doesn't swap itself out unnoticed is deliberate and stays that way.

## 0.10.27-alpha.20260817 – August 17, 2026

### New

- **New: `--ersetzen` for integration with legal-practice software.** The result takes the place of the source file instead of being created alongside it. This makes checking a document out of and back into legal-practice software ("Open and edit" in the e-file) work without any interface: the software hands out the file and gets it back cleaned at the same spot.

  **This switch bypasses the first core principle**, and that is why it exists only on the command line — not in the window — and only if your administration releases it (the `ersetzen` entry in the policy file). Without release, the call aborts and says why; silently creating a second file would be the worse mistake, because then the unchanged one would be checked back in.

  A neighboring file is written first; only once it is finished does it take the source's place. An abort or error therefore leaves the source **byte for byte unchanged** and leaves no fragment behind. In the verification log, the replacement appears as its own field — a reviewer needs to know that the uncleaned version no longer resides here.

- **The manual now explains the Windows warning on first launch.** New first section "Windows warns on first launch — what to do," with two images and three steps: "More info" is a small link, not a button — that's exactly where most people get stuck — then "Run anyway."

  That it says "Unknown publisher" there is the whole point of the warning: the packages are currently shipped without a certificate. We think it is better to explain that than to hide it.

- **The way back now notices when text and mapping don't belong together.** Anyone who pastes the response into a different matter previously got someone else's names in the correct text — no error, no message, just wrong. Maskuro now remembers which placeholders the last run actually produced, and reports any that don't belong. If none of them come from the last run, nothing is inserted and the window says why — instead of assuming, as before, an expired period.

  **One limit remains, and it's also stated in the manual:** placeholders are numbered per run, so the first name is called `[NAME_1]` in every document. If the foreign text carries only such placeholders, the mix-up cannot be detected.

- **PDF can now be output in black and white.** A checkbox at the output mode converts every page into a black-and-white image — with an invisible text layer underneath, so it remains readable and searchable. For sending via beA and similar channels with hard size limits: on average **68% smaller** across our measurement corpus (command line: `--monochrom`).

  **How much it helps depends on the document** — and this is also stated at the checkbox: scans and image-heavy content shrink a lot, a lean text document without embedded fonts can even get larger. Try it on one file before turning it on for a whole batch.

  The price: every page is recomputed — with a thousand pages, that takes minutes. And images lose everything between black and white; that doesn't matter for text, but it does for a photograph.

- **The hit list in the touch-up window now counts along.** Above the list it says "5 hits," and as soon as you filter, "1 of 5 hits." That's the difference between "I've filtered" and "there are five, and I've seen them all" — the move you use to check whether a name was really replaced everywhere.

- **The verification log can now be searched and filtered.** The view under "File → Verification log" previously had a table and nothing else — with a month of three thousand runs, you could see that a lot had happened, but not what.

  New are a **search field**, **three filters** (procedure, result, type), and **paging**, plus three columns that didn't exist before: **procedure** (redacted or replaced), **confidence**, and **duration**. Above the list it states how much is currently shown and how much the filter hides.

  "Save as CSV …" now exports **exactly what is displayed** — anyone who has filtered gets the filtered set, and the message names the count.

  A dash for confidence or duration means nothing was measured for that row — for example because it predates this feature. These values are **not** calculated retroactively. There is still no filter by user; a single row is nevertheless found by search.

### Removed

- **The transparency notice in the "About this program" window is gone again.** It had stood there since 0.10.22-beta.1 and said that the application was developed with the support of artificial intelligence. It was required nowhere, and of all places in an application for data protection, some read it as a statement about how it operates — as though documents went out to a service on the internet. Cleaning continues to happen exclusively on your own computer; that is stated where it belongs, in the "Privacy" tab.

### Fixed

- **The program swapped its own icon for a worse one.** Anyone who registered the context menu from within the program afterward had a different shield in the taskbar than after installation — similar, but with left-aligned instead of centered bars and visibly coarser. Behind this was a fallback: if the program cannot find the icon template, it draws itself one. This was meant for the case where **no** icons exist at all; in practice it also drew one when the bundled ones had long been present — and overwrote them. In a version installed from setup, there is no template, so it hit everyone there. Existing icons now remain untouched.

  **Already-affected installations do not get the correct icon back by themselves** — reinstall once to fix this.

- **"Objektkennung: OB-4711-22" counted as a login name.** The recognizer for usernames checked its labels without a word boundary before them — so **every** word ending in one of them matched: Objektkennung, Fahrzeugkennung, Gerätekennung. The value behind it was removed even though it has nothing to do with a login name.

  Compounds that are genuinely meant — "Benutzerkennung," "Anmeldekennung" — stand individually in the list and continue to be found.


- **In English, Greek, Japanese, and Korean, sixteen placeholders appeared in German in the result.** Anyone who had set the interface to one of these four languages got the German labels written into the document for the newer data types — a password became `[ZUGANGSDATEN_1]` instead of `[CREDENTIALS_1]`, a diagnosis code became `[DIAGNOSESCHLUESSEL_1]` instead of `[DIAGNOSIS_CODE_1]`. Affected were health, diagnosis, medication, diagnosis and drug codes, religion, union membership, political opinion, criminal law, credentials, username, card data, coordinates, occupation, amount, and characteristic.

  The remaining 44 languages never had this bug: they take their labels from the language files, where these types had been present from the start. Exactly these four languages carry their own tables for a different reason — their script doesn't survive the PDF character set, which is why Latin labels appear there — and in these tables, the new types were simply missing.

  It came to light while translating the catalog page: the website promised English readers labels the program never wrote. A test now checks the four tables against the list of all labels that can occur at all.

- **The rules window no longer opens too small for its content.** In the "Custom search patterns" tab, the wizard's explanation line ("Searching for: …") sat half-hidden behind the "Sample text" field — of all things, the sentence that lets you check, without knowing regular expressions, whether your rule searches for the right thing. The window had a fixed minimum size from a time with fewer tabs, and could therefore be dragged smaller than what fits inside it. It now sizes itself to its content and only opens as small as it can while everything stays legible.

- **Names in spreadsheet formulas no longer remain.** A cell has more than one place for text, and previously only one was cleared. If a name stood inside a formula — `="Frau "&"Sieglinde Ortner"` — or was the last-calculated result of a formula, it remained unchanged in the workbook even though the same person was replaced in the cell next to it. Anyone clicking the cell read it in the formula bar.

  Both are now replaced. Only what stands between quotation marks is touched: cell references, function names, and sheet names remain untouched, `=SUMME(K2:K6)` keeps calculating. Because the same name gets the same placeholder everywhere, `=SUMMEWENN(A:A;"Huber";B:B)` also continues to find its rows.

- **Charts no longer display names.** A chart stores its own copy of its axis labels — it keeps drawing them even once the source cells are long since empty. Underneath the bars, five person names therefore remained even though the table above was clean. This applies to spreadsheets **and** presentations.

- **Named ranges with fixed text are cleared.** A named range can contain fixed text instead of a cell reference; if a name stood there, it remained. The range's **name** itself continues to remain — formulas reference it, and renaming it would produce a reference error. As with the sheet name, it is reported, not replaced.

- **A date of birth recognized once now disappears throughout the whole document.** A date on its own says nothing — only a field word makes it a date of birth, which is exactly why an invoice date is left alone. But if the same item stood a second time in the same document without this word — in an image title, in a filled-out form field — it remained there, even though a few lines above "geboren am …" had been unambiguously recognized. Only what has already been recognized as a date of birth **in this** document is carried over; nothing is still guessed.

- **Structured data in web pages gives away its date of birth.** In the JSON-LD block for search engines, the date sits under the key `birthDate` — the key states what it is, just as a column header otherwise does. It is now read along; "Birthday" and "Birthdate" thus also count as field labels in forms.

- **Date of birth and personnel number are now also found in spreadsheets.** A cell contains only the bare value — `14.03.1988`. What it means is stated solely by the column header, which sits many rows above. In Excel this was already read along; in LibreOffice spreadsheets and in CSV files it was not, and the date of birth therefore remained there.

  Both now read the header along — **but only if it is itself a field label.** Under "Geburtsdatum" the date falls, under "Rechnungsdatum" or "Lieferdatum" it does not. This is deliberately the cautious interpretation: a header like "Name" above an arbitrary remark could once again place a placeholder over a sentence that contains no person at all.

### Fixed

- **A cleaned CSV remains a table.** Detection reads a CSV row as a sentence and therefore sometimes placed its hits across a semicolon too. The placeholder swallowed the separator, the row afterward had one column fewer, and the file could no longer be opened as a table. Hits now end at the cell boundary, and the quotation marks of the escaping remain in place. The affected cells are afterward read once more on their own — otherwise the neighboring cell that the too-long hit had covered would remain unclean.

- **Comments in presentations.** The marginal note on a slide — often exactly the spot where "Bitte Frau … vor der Sitzung anrufen" stands — remained untouched, along with the name of whoever wrote it. In Excel both had long been cleared; PowerPoint stores comment text and author differently, and that had been overlooked. This affects both formats: the older one and the one PowerPoint has written since 2019 — there also the work email address attached to the author. The initials PowerPoint shows on the speech-bubble icon are removed too.

- **LibreOffice files: formula, user field, note author.** What had already been cleared in Excel remained in the ODS spreadsheet — there, the formula isn't a separate element but a property of the cell, and the name inside it survived. On the next open, LibreOffice recalculated it right back.

  Also three further spots: the value of a **user field** in OpenDocument sits once at the top in the declaration and is merely referenced in the text — previously only the reference was replaced, so the old value came back on opening. The **author of a note** and of a tracked change remained. And in a **spreadsheet**, change tracking was not cleared at all — unlike in the text document — so deleted cell content, complete with editor names, was preserved. Cell references and sum formulas remain untouched by this.

- **Saved web pages give away their attributes.** A page shows far from everything it contains. A filled-out form field carries the input in its `value`, a JavaScript interface stores its data set in `data-…`, and the block for search engines (JSON-LD) repeats it fully and well-formed: name, date of birth, address, phone. The visible text was cleaned, all of that remained.

  These spots are now also cleared, along with `aria-…` (what a screen reader reads aloud), `placeholder`, `summary`, and the suggested file name of a link. The JSON-LD block is read as data in the process and remains valid — its keys and its vocabulary remain, only the values go. Ordinary JavaScript continues to be left untouched.

- **Images lose their secondary data even without EXIF.** A photo carries the photographer's name, capture time, and GPS coordinates of the location alongside it — for an apartment listing, this gives away the address even if none appears in the text. This was removed as long as the image had EXIF. But if the data was stored **only** as XMP (the way Lightroom and Photoshop save it) or as a text block in a PNG (`Author`, `Comment`), the image remained completely untouched. Both are now recognized and removed — even in images embedded inside a document and preserved there. Orientation still survives, and an image without secondary data is not needlessly re-saved.

- **Link targets in spreadsheets, presentations, and Word documents.** Where a link leads is not stated in the text but in a separate storage area of the file. An email address behind "Mail schreiben" therefore survived cleaning intact, while the same address in the text was replaced. `mailto:` and `tel:` are now cleared there too, just as in saved web pages.

### New

- **Doctor's letters no longer come back damaged.** Previously, name detection mistook drug substances for person names: "Metoprololsuccinat" became `[NAME]`, "Ramipril" became `[ORT]`. The medication plan was unusable afterward — while the diagnoses remained untouched, exactly backwards. Measured, this affected **63% of active ingredients** and **53% of clinical terms**, and not only in German: 74% across seven languages, all tested cases in Italian.

  Maskuro now knows the medical vocabulary and leaves it alone. What remains is 6% instead of 43% (German) and 1% instead of 74% (across languages). Where a salutation precedes it — "Sehr geehrte Frau …" — the name stays a name, even if it happens to sound like a drug substance.

- **Diseases and medications can be removed — if you want that.** New checkbox in settings: "Also remove diseases and medications" (command line: `--mit-diagnosen`). For personnel files, terminations, and expert opinions, where the diagnosis is nobody's business.

  **Off by default**, and deliberately so: a doctor's letter *consists of* diagnoses and active ingredients. Anyone anonymizing one — for research, for training, for an AI tool — mostly wants to keep exactly this content and only get rid of who it concerns. The diagnosis is the payload there, not the identifier.

  Detection finds the common designations and does not replace review: a disease list is never complete, because the doctor writes "C2-Abusus" where the classification says "disorders due to alcohol."

- **Diagnosis and drug codes are found.** ICD-10 (`I48.2`), ATC (`A10BA02`), and the German pharmacy central number are health data just like any spelled-out diagnosis — in discharge letters and billing documents even the more common form. They are on by default, like the other special categories under GDPR Art. 9.

  A diagnosis code is only recognized with supporting evidence: with "ICD" before it or in parentheses behind the diagnosis line. Without this condition, the program would mistake the function key **F10** for a substance-abuse diagnosis — in the classification, F10 is exactly that.

- **The finished file can now be copied.** Next to "View," "Touch up," and "Show in folder," every finished row now has a fourth button: **Copy**. It places the cleaned file on the clipboard — from there it goes with Ctrl+V (Mac: ⌘V) into an email, a chat window, or an AI tool, without the detour via the folder.

  The **file** is copied, not its text: page layout, images, and the redaction bars are thereby preserved. Via the list's context menu, several selected results also go onto the clipboard at once, and in the "File" menu the same path appears as **"Copy result"** for anyone who prefers the keyboard.

- **Country selection can now follow the document.** ID, social security, and tax numbers differ from country to country, and which countries are checked was previously fixed for the whole session — derived from the interface language. Anyone working in German who cleans a French letter thus searched it for German tax IDs and not for the French social security number.

  The rules window now has **"Automatically, by the document's language"** for this. The fixed selection remains available alongside it, and deliberately so: language detection is not infallible — if it misjudges, the wrong country selection kicks in. Anyone processing only documents from one country is safer with the fixed list.

  Unaffected by this are the **German** patterns (tax ID, license plate, extension): they hang on the language, not on the country selection, and continue to trigger even when a short German text is classified as English.

- **Passwords, keys, and login names are now found.** Anyone pasting an error message, a log, or a snippet from a configuration file into an AI window almost always has an access key inside it — and it previously remained unchanged there.

  Both are recognized: the common key forms that speak for themselves (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, the header of a private key), and the labeled form — "Passwort:," "API-Key =," "Token:," "Benutzername:." Only the value is replaced, never the label: "Passwort: [ZUGANGSDATEN_1]" remains legible, and anyone reviewing the result sees that a password stood there.

  Login name and password are two separate types. Anyone who only wants to remove passwords turns off one and keeps the other.

- **Bar codes and QR codes in images are made unrecognizable.** A scanned notice almost always has a code stuck to it, and it carries the case number — the same number that is removed in the text next to it. Previously the machine-readable version remained: the bar over the number is useless if a device reads it in a second from two centimeters away.

  QR code, Data Matrix, Aztec, Code 128, EAN, and the other common forms are recognized. "Unrecognizable" means pixelated, and more coarsely than for faces: a code's error correction can recover a surprising amount from just a few preserved fields, so a half-hearted veil would not amount to removal.

  The option sits next to "Make faces unrecognizable" and is likewise **on by default**. Even with the option turned off, the report states how many images carry a code — you see a face while browsing through, but you take a code for decoration.

- **Card verification number, PIN, and expiry date are found.** The program already found the credit card number; only with the three items next to it does it become usable, and on every billing statement they sit together. All three only behind their label — "123" alone is a house number, a page number, or a quantity.

- **Coordinates in text are found.** Maskuro already removed the capture location from images; if the same item stood as text in an expert report or an incident report, it remained. Decimal degrees and the degrees-minutes-seconds notation are recognized. With decimal degrees, a word like "Standort," "Fundort," or "Koordinaten" must stand nearby — otherwise any measurement series with two decimal places would be a location.

- **Monetary amounts can now also be removed.** New checkbox "Also remove monetary amounts," **off** by default like the date items above: in a contract, the amount is the content, and redacting everything protects no one. In a payslip, a settlement proposal, or a bank statement, on the other hand, it is exactly the item that says more about the person than the name next to it — only someone with the document in front of them knows which case applies.

  An amount is only recognized **with a currency indication**: "4,250.00" alone is a quantity, only "4,250.00 EUR" is money. Currency symbol, abbreviation, and spelled-out name count, before or after, including the notation "990,– CHF."

- **The special categories under GDPR Art. 9 are recognized.** Religious belief, union membership, political opinion, health data — and alongside them the criminal-law data under Art. 10. These are the data whose processing the regulation, in principle, **prohibits**; they are therefore the only new group **on** by default. Anyone who wants to keep them decides that themselves.

  The form in which they appear in practice is recognized: the form field on the personnel sheet — "Religionsbekenntnis: röm.-kath.," "Gewerkschaft: ÖGB," "Grad der Behinderung: 50," "Vorstrafen: keine" — both with a colon next to it and with the label above it, the way a filled-out sheet delivers it.

  **Running text belongs to the AI tier.** "Er engagiert sich seit Jahren in der Gewerkschaft" is the same item, and no search pattern reliably finds it. Since this version, the AI tier explicitly also searches for these categories; anyone who needs running text turns it on.

- **Personal characteristics and occupation — the data that shows who is meant even without a name.** Gender, marital status, height, eye and hair color are removed starting with this version; occupation, function, and department on request, via a dedicated checkbox ("Also remove occupation and department") or `--mit-berufen`.

  **Why one is on and the other off:** "Die Leiterin der Abteilung Einkauf" names exactly one person within a company, even if the name next to it is redacted — in an expert report or a termination, that belongs removed. A staff directory, on the other hand, *consists of* job titles; redacting them by default would return an empty sheet. Only someone with the document in front of them knows which case applies. The characteristics above appear almost only in form fields, are rare, and never carry the content — so they cost nothing.

- **Check a foreign file.** "File → Check file …" reads an already-redacted document back and reports what still stands in it — and **exactly where**: page and line, type and length. For the case where someone reviews someone else's work: a file from a law firm, information from an authority, your own outgoing mail before sending.

  **The value itself does not appear in the report.** Anyone who opens the location sees it anyway — and the report may therefore be saved and passed on without itself being a collection of personal data.

  **And the report always states what it could not see.** Images are not read; with a scan without a text layer, "no hit" means *not checked*, not *clean*. On the command line this is distinguished by the return value: `--nachpruefen` returns 0 for checked and clean, 4 for hits, and 5 for not checkable. This lets outgoing mail be automatically held back instead of waved through.

- **Verification report: one sheet per cleaning.** "File → Save verification report …" — or `--pruefbericht <folder>` on the command line — writes a one-page PDF (optionally CSV or text) with the run's data, the types found with their count, two metrics, and a review note. For the file folder and for oversight: the verification log is the solid evidence, but nobody submits a JSON Lines file.

  **New here are two figures** that previously appeared nowhere: the *average confidence* — how certain detection was about what it found — and the *masking rate*, the share of replaced characters in the text. Both appear with their limitation stated: confidence says **nothing** about what was overlooked, and next to it always stands how many hits it even covers; the rate doesn't count images and comes out too high for an image-heavy document.

  **Found values do not appear on the sheet** — the same limit as with the log and the search run. Two lines at the bottom say different things: the checksum shows that the sheet is unchanged; the log line — only with the log running — refers to the **signed** row that documents the run. Only that one proves provenance.

- **"How certain was that?" — the statistics on the result.** A "Statistics" button below the result expands what was previously visible nowhere: hits, words, and characters, the distribution per type as a bar row, plus the average confidence and the masking rate. The same figures as in the verification report, only immediately and without printing.

  **With its caveat in the same area:** next to the confidence stands how many hits it covers, and below it the sentence that it says **nothing** about what was overlooked. A percentage without this sentence reads like a hit rate — and anyone who understands it that way is worse off than without the figure.

  Calculation only happens on expanding: the denominator of the masking rate costs one read per file, and anyone who never looks at the figures shouldn't have to pay for that.

- **Build custom search patterns without writing one.** The "Custom search patterns" tab now guides you through it in three steps: *What are you looking for? → What does such an item look like for you? → Name and save.* You type in an example — e.g. `KD-004711` — the program derives the pattern from it and writes out in words what it searches for. A preview with a hit counter checks along with every keystroke.

  **No regular expression appears in this process.** Capability was never the problem: custom search patterns have existed for a long time, they just required an expression like `\bKD-\d{6}\b`, and nobody at a law firm or HR department writes one. Anyone who *wants* to write one expands expert mode.

  **The template catalog has been reorganized:** thirteen cards with a name, explanation, and example value, filterable via category tags — finance, government, contact, personnel, medicine.

  And if the derived pattern casts too wide a net, the program says so on its own: an example made only of digits matches any year and any amount, and anyone who cannot read the expression would otherwise not notice.

- **Seven tags instead of fifty-six checkboxes.** A new tab "What is searched for" bundles all recognizable types into seven groups — person, contact and place, identifiers, finance, technology, special categories, companies, and custom. A tag toggles its group; "All on" and "All off" toggle the whole list; below that, every type remains individually checkable.

  **Everything is on by default, and that stays that way.** What is turned off here is not searched for at all — the coarsest intervention the rules window allows, and it affects every document. That's why, below the list, it always states how many types are off, and only what is turned off gets saved: a new type is thus also on in a rules file from the day before yesterday, instead of silently falling out.

- **Apply a frame to all pages.** In the touch-up window, the **Apply to all pages** button takes the most recently dragged frame and redacts the same spot on every further page — for letterhead, footer, and case-number field. On a scanned file with eighty pages, this turns twenty minutes into two.

  **"The same spot" means the same *relative* spot on the sheet.** In a stack from the document feeder, one page is regularly landscape, another is A3, a third is rotated; an absolutely applied rectangle would land there next to the letterhead — and you'd see a bar and think the matter settled.

  **It redacts, not replaces**, even if the source frame was a placeholder: underneath the same rectangle, page forty holds something different from page one, and a placeholder with the same number would claim an equivalence that doesn't exist.

- **A note on the redaction bar.** In the right of access to files, a note next to every redaction states why it was redacted. The new field **Note on bar** in settings — or `--balkenvermerk` — writes a short text onto every bar: "§ 203 StGB," "GDPR," "confidential." For a document an authority hands out, that's the difference: the recipient sees the reason without having a log they never get anyway.

  **Empty by default**, because the note is visible in the released document and is itself an item of information — it tells the recipient under which title something is being withheld. It only takes effect for **redacting**; where a placeholder stands, no bar stands. On a bar too small for legible text, it is omitted — an illegible note looks like an error.

- **Activation without an internet connection — now complete.** The license window has had "Activate without internet" for a while: at the top a request code to take along, at the bottom the field for the activation that comes back. Only, until now, **nobody could issue it** — the tool for that was missing, and the code went nowhere. This is fixed.

  For authorities and law firms with sealed-off computers, this isn't a special case but the normal one — and it is exactly the audience for whom the promise "your documents never leave the computer" weighs heaviest. The code reveals nothing about documents: it contains the license ID and a hash of the computer, nothing else.

- **Get from scanner.** "File → Get from scanner …" reads in a stack directly and places the pages in the list — for a mailroom, the difference between two work steps and one. A document feeder is emptied to the last page; device, resolution, and color are chosen via the scanner's system dialog, which you already know.

  **It is not cleaned automatically.** You first see what came in, and then press "Clean" like with any other file — a scan that runs through immediately would take away your view of a stack fed in crooked.

  **This exists only under Windows**, and the menu entry says so on the Mac too: there, your scanner's software writes into a folder, and "Monitor folder …" cleans everything that lands there.

### Miscellaneous

- **The list of all detected items is now included** and is generated from the source code (`hilfe/GEFUNDENE-ANGABEN.md`): 177 types in 35 countries, 23 of them with check-digit calculation. It also states how counting was done — we count `[NAME]` once, where others list first, middle, and last names as three entries.

- **Redacting now also exists in Word, PowerPoint, OpenDocument, and HTML.** The choice between placeholder and redaction previously only applied to PDF files. Now the others can do it too: the hit is removed, and a black bar stands in its place — in the document itself, not as an image over it. Anyone passing the file on hands over a redacted file, not one where the redacted content still lies underneath as text.

  **It is decided separately**, in two choice fields: "For PDF" and "For Word, PowerPoint, OpenDocument, and HTML." People want it different — the redacted PDF goes to the authority, the same matter as a Word file continues traveling through the organization and is meant to stay legible. On the command line, correspondingly `--pdf-modus` and `--office-modus`; a saved "redact" from earlier versions continues to apply to the PDF.

  In spreadsheets, plain text, CSV, and email, the bar doesn't work — there's no surface for it to sit on there. A placeholder continues to be inserted, and the result **now states this**, instead of doing it silently.

- **New: "Remove" — the hit spot simply stays empty.** The third mode alongside placeholder and redact, and the only one that works for **every** format: leaving something out needs no surface. In the PDF, nothing is drawn; in Word and HTML, the spot stays empty; in a table, likewise.

  It is the quietest of the three: anyone reading the result doesn't see that something ever stood there — even the length of the value no longer gives it away. For a document meant for someone to review, the placeholder usually remains the better choice.

  For images, none of the three choices applies: pixels can't be replaced by a placeholder or left out. What text recognition finds there continues, as before, to always be painted over.

- **The touch-up window no longer claims replacements that don't exist.** On the right, a placeholder appeared for every value — even for a redacted file, where not a single one occurs. A click on such a row selected nothing, and "Undo" ran into nothing. It now states "redacted" or "removed" there, and the rows can't even be undone: the text is gone, there's nothing to restore. This applied to redacted PDF files, to Word and OpenDocument, and to anything found in images.

- **The text view now shows the bars as bars.** A redacted Word file looked **empty** during touch-up: gaps stood at the redacted spots, as though the program had swallowed the text. The reason was the display, not the result — in the document itself, the bar had been correct the whole time. It now also appears there in the view, black as in the result, in Word, PowerPoint, OpenDocument, and HTML.

- **Outlook messages (`.msg`) are now cleaned.** `.eml` had existed for a while — but in German companies, Outlook *is* email, and there a saved message is called `.msg`. This covers the densest PII format in its most common storage form too: subject, sender, recipient lines, message body, HTML version, recipient list, and attachments — the latter via the existing paths and with the same placeholders as the mail text.

  **A `.msg` carries the same text multiple times**, and that's the trap: as plain text, as HTML, **and** as RTF. Anyone who only cleans the plain text has done nothing — Outlook preferentially displays the RTF. The RTF version is therefore removed entirely, as are the internet headers with their Received chain and the binary search keys, which survive every text cleaning with names and addresses intact. The result still opens in Outlook and shows the text without font styling; the report states this explicitly.

- **Describe rules in your own words instead of writing regex.** The rules window can do a lot, and for that it required a regular expression pattern — the point where most people stop. Now a sentence is enough: "Our case numbers of the form 12 C 345/26 should be left alone." The AI tier suggests terms and search patterns from it.

  **Only what you check gets adopted — and nothing is checked by default.** Next to every suggestion stands a sentence explaining what it means, and the number of its hits in a sample text you can supply. What **removes** protection is marked as such: "always remove this term" and "never remove this term" would otherwise look identical in a list. Suggestions that would match everything aren't shown at all.

- **The verification log now tallies across all workstations.** If an organization places the logs via `protokoll_pfad` on a shared drive, every workstation writes its own monthly file there — previously a data protection officer with thirty seats had to look at thirty files individually. A row with the month's totals now sits above the list, and **it reports broken chains by name**: a subsequent alteration is only noticed if someone checks, and in thirty files nobody checks by hand.

  **No breakdown per person** — not even in this view. A ranking of "who cleaned how much" would be suited to monitoring conduct and performance, and that is what matters under co-determination law, not the intent. Runs, files, and hits are counted across the organization.

- **"Suggest profile from a document": ask the rules once instead of going through forty-four types.** The rules window has a new button: it shows the AI tier a document, determines what kind it is — doctor's letter, application, contract, invoice, official notice — and suggests the strategies that fit. For a doctor's letter, for example, dates are shifted instead of replaced, because in a medical record the chronology is the content.

  **The profiles live in the program, the model only picks among them** — the redaction rules don't depend on what a language model considers a good idea. Every point is suggested individually with a justification; nothing is adopted without confirmation, and what you've set yourself remains untouched. Without the AI tier, it stays with the safe default: placeholders for everything.

- **New strategy "invent": a plausible fake value instead of a placeholder.** "Frau Berger schrieb an Herrn Doppler in Fulda" instead of "[NAME_1] schrieb an [NAME_2] in [ORT_1]" — for training material, demo files, test data sets, and anything subsequently shown to an AI. Salutation, sentence structure, and readability are preserved.

  The same value gets the same fake value, across all files of a matter and on every computer with the same rules file — **without a mapping being stored anywhere** (the same mechanism as with hashing). Email addresses sit on reserved example domains, phone numbers in the range set aside for that purpose, invented IBANs carry a correctly calculated check digit. Possible for names, places, addresses, companies, email, phone, and IBAN; for other types the rule is rejected instead of remaining without effect.

  **The report explicitly states that content was invented.** A document cleaned this way reads like a real one and isn't one — it does not serve as evidence and must not be passed on as an original.

- **The cross-check: "Who remains recognizable?"** A new checkbox under the AI tier shows the **finished result** to the language model once more and asks who is still recognizable despite cleaning. What's meant is the case no detection in the world can find, because no name stands there at all: "the only midwife in the district," "the colleague who quit in March after the fire." No pattern matches, and yet everyone locally knows who is meant.

  **Nothing is removed in the process.** The spots appear in the report with a sentence of justification, and the decision is made by hand — a program that on its own removes sentences from a document because it finds them revealing turns a cleaning into a rewrite, and no one would see what's missing. At most five spots per file; whatever the model cannot literally document falls away. On the command line: `--restrisiko` together with `--ki`.

- **The way back out of the AI: "Translate response back."** Until now, only half the loop was built — copy text, paste the cleaned version, show it to the AI. The response came back with `[NAME_1]`, and anyone who needed it manually reinserted what they had manually removed. The way back now sits in the "Program" menu: copy the response, click the entry, the real names are there again.

  The mapping for this lives **only in memory**, always applies only to the most recently cleaned spot, and expires after an hour; anyone who turns off the clipboard watcher loses it immediately. Only what was replaced can be restored this way — redacted, masked, and hashed content is not reversible, and the program states how many spots it therefore had to leave standing. Managed installations can turn off the way back entirely via the `rueckweg` policy.

- **Monitor folder: what gets placed inside sits cleaned in the outbox shortly after.** For a mailroom, a shared-mailbox team, or a scan folder — set it up once, and after that nobody clicks anything. Found under "File → Monitor folder …," on the command line via `--wache <folder>`.

  The original stays where it was; on request it moves unchanged into the "Erledigt" subfolder, and nothing is ever overwritten. A file is only touched once it has finished being written — a file still being copied over the network would otherwise be read half-done and reported as cleaned. Whatever goes wrong is left in place and reported, instead of being retried endlessly. And the watcher remembers what's done without the file name: what sits in an inbox folder often already gives away what it's about, just from the name.

  **Monitoring a folder outside your own user profile — e.g. on a network drive — requires an automation license.** A folder several people can reach is a service, not a single workstation; the restriction does not apply within your own profile or during the trial period.

### Fixed

- **Settings were cut off on the right.** The window opened at a fixed size, and that was only enough for the font size it was developed with: on the Mac, "Check now," "Change …," and the notices next to them stood half outside. It now opens as wide as its pages need — in every language and at every font size, limited only by the screen.

- **"Check now" now responds visibly.** The result appeared in the main window's status line — that is, behind the settings window it was requested from. Anyone checking saw nothing. The answer now appears as a message over settings, and if a new version is available, it leads straight to installing. On program startup, it stays with the status line as before; no window opens unasked.

- **Copied files did not arrive on the clipboard on the Mac.** Placing cleaned files reported success and yet placed nothing usable — pasting produced nothing. This affected everything that writes files onto the clipboard.

- **And from the clipboard, only the first file was read on the Mac.** Anyone who copied three files in Finder and chose "Clean clipboard now" got two of them back unclean — without anything saying so. All of them now come through.

- **"Check file" now also accepts dragged-in files** — like the main window. Dropped items are added instead of discarding the previous selection; dropping the same thing twice changes nothing, and what the program cannot read is reported instead of swallowed.

- **And the window states that it is waiting for you.** It opened with an empty box and a gray "Check" button — that looks as if nothing is there, not as though a selection is missing. It now reads "No file selected yet — drag one here or choose below via 'Select files …'"

- **A long run now says that it is running.** "Loading additional model for more precise detection — one moment …" remained standing for as long as detection was computing: for a file with 47,500 words, that's eighteen minutes, even though loading was over after nine seconds. Anyone seeing that assumes the program has hung. It's now followed by "More precise detection running — this takes a few minutes for long texts," and the status line counts along: "More precise detection (7/312)." Reporting happens from the model's loop — every 250 words, roughly every six seconds — not per text block: a text block can carry twelve thousand words and take minutes.

- **An aborted run now says that it was aborted.** Anyone who pressed "Cancel" afterward read "0 of 1 file(s) cleaned." — correctly counted and yet the wrong information. The message naming which file it hit was overwritten at the same moment by the count message. And the file list still said "running …," even though nothing was running anymore; it now says "aborted."

- **The sentence about privacy was cut off.** "… no cloud, no upload. More in the priv" — at the window width the program starts with, it ended mid-word. It now takes the full width.

- **The license service could report something, and nobody was listening.** When all license seats are occupied, the license has expired, the key is unknown, or license management at the provider is switched off, the service sends exactly a reason for that — the plan from the start was that you'd be shown it **once**. It was never shown. A notice now appears that first states the program keeps working unchanged, and then what the matter is. Once per reason: anyone who has dismissed it won't see it again on the daily check — but will if the reason changes.

- **A multi-seat license bought in the shop showed "1 seat."** The shop distributes prepared keys and keeps the purchased seat count itself; but the number shown came from the key itself, and that reads one seat for every stock key. Anyone who had bought eight seats read "1 seat" — and from the second registered computer onward, the display appeared in red along with "Please contact your administration." The number the service last reported now applies; without a response it stays with the key, and it never falls below the purchased scope. The same applies to add-on purchases and renewals: those change the seat count at the provider, not your key.

- **After purchase, "Licensed for Maskuro Privatlizenz" appeared.** That's not a name, but the placeholder under which keys are prepared — your name cannot appear there because the key is signed before the purchase. Instead of showing you a stranger's name as your own, it now simply reads "Private license" and the seat count. With a license issued to you personally, your name appears there unchanged.

- **The Help menu read "Hilfe _FAQ."** The ampersand had turned into an underscore because Qt read it as a marker for a keyboard mnemonic. It now reads "Hilfe & FAQ."

- **The settings window remained standing when the program vanished into the tray icon** — and still did even when the main window was closed. It now goes along. (Affects only this version; the dedicated window is new.)

- **A rejected license request now states what's behind it.** If the license service rejected a request without sending along a reason, the license window showed, in red, "Unknown response." — a sentence neither you nor support can do anything with, and one that sends you looking for the fault in your own key. It now states what actually happened: that the service rejected it without giving a reason, and whom to contact. If license management is temporarily switched off at the provider, that too is now named — along with the note that your key is not affected by it.

- **On the Mac, configured languages suddenly counted as missing.** On startup the program reported "No language model is installed" and offered the initial setup, even though the languages had long since been loaded — anyone checking under "Document languages" found them all present. The program searched for them at two different places depending on the launch path: launched from the Applications folder, it found them; the same build launched as a plain folder, it searched next to itself, where none exist. From now on, the exact same location within the user profile applies on the Mac, regardless of how the program is packaged. Nothing needs to be reloaded.

- **"What's new" showed half the list.** The window after an update broke off mid-sentence, and the remaining points appeared as empty bullet points. The culprit was a placeholder in angle brackets — e.g. `<datei>.docx` — which the display mistook for markup and discarded everything after. Of all things, the security-related items were affected by this. Help has always shown such placeholders correctly; this window now does too.

- **Pinch with two fingers now zooms in the touch-up window.** On a trackpad that is *the* zoom gesture — in the editor it previously did nothing, and anyone wanting a closer look had to reach for the slider or Ctrl+mouse wheel. The page follows the gesture immediately and is redrawn sharp again on release.

- **Zooming now centers on the spot you're looking at.** Pinching zooms around the point between your fingers, Ctrl+mouse wheel around the point under the cursor. Buttons, keyboard shortcuts, and the zoom slider hold the center fixed — they have no spot you're pointing at. Previously, all of them only kept the scroll value in place: from a fitted page, that held the top edge, and everything below it drifted out of view when zooming in.

- **"Before/After" was a dead button in the page view.** As long as the page view was on, it could be pressed — and reported every time that the original could not be opened. There's nothing to compare there either: the page view is an image of the cleaned version; there is no counterpart to the original. The button is now disabled and, on hover, names the reason along with a way out (the text view). Its description also explicitly promised the comparison would work "regardless of whether the text view or page view is active" — that was never true.

- **The page view crashed LibreOffice.** If two page views were generated simultaneously — e.g. "Redact as PDF" while the preview was still computing — the system reported a LibreOffice crash, even though the pages did appear in the end: both runs accessed the same LibreOffice working profile, which it can't tolerate. It now always gets only one run at a time; the others switch to their own. This costs a few seconds longer, but no error message appears anymore, and none of the runs is left without a result. A second render job alongside a running one is also no longer accepted at all.

- **"Show original" could quit the program.** If the original could not be opened — because it was moved, renamed, password-protected, or sits on a disconnected drive — the touch-up window aborted without warning, and open working copies were lost. A notice now appears, the toggle springs back, and the cleaned version remains. Where the original fundamentally doesn't fit — e.g. with a PDF page preview generated from a Word file — the toggle is disabled from the outset and, on hover, names the reason, instead of showing the same notice on every press.

- **Bug reports never arrived.** Anyone trying to report a bug got "The server rejected the report" — and nobody had ever seen it. Two causes, both along the way: the program did not identify itself to the server and was therefore rejected by the mass-access protection, and the address pointed to a second name the program did not follow. Both are fixed; a report now goes out again. **The same affected license activation**: registering, deregistering, and checking also failed to reach the service — there only unnoticeably, because an unanswered request deliberately changes nothing about your license. And if a refusal remains unexplainable after all, its technical number now appears, instead of every cause looking the same.

- **A click on "Show original" could quit the program.** If the original could not be opened — moved, renamed, on a disconnected network drive, password-protected, or damaged — the touch-up window disappeared along with all open working copies. The toggle now stays on the cleaned version, and a box states what's going on; the technical reason is in the details, in case you want to report it. The same applies to a result that cannot be displayed: the window opens and says so, instead of disappearing.

- **The crash question appeared too often — and deleted the trace it was asking about.** It appeared even when nothing had crashed: the record is created as soon as an unexpected disruption occurs anywhere, even when the program survives it and exits completely normally afterward; it was never cleared away. And anyone who answered "No" destroyed the only details of the incident — the record disappeared already when the question was *displayed*. Both are fixed: an orderly exit clears the record away, only a genuine crash is asked about now, and it's only marked off after your answer. The details sit in the error log on your own computer anyway — anyone not wanting to send anything loses nothing either way. As before, only what you have fully seen and released yourself is ever sent.

- **"Clean" could remain silently locked.** If the language models got stuck while loading, the button stayed disabled — without explanation. A click on it did nothing, and the status line kept saying "Loading language models …," even after ten minutes. The cause: disruptions in background processes went to a place nobody sees when launching from the file manager; what remained was a window that looked ready to work and reacted to no click. Such disruptions now land in the error log, loading the language models reports its failure in every case instead of silently giving up, and if it still stays silent, the application says after forty-five seconds that something is wrong, with advice in the details. The disabled button names its reason on hover. A long initial download doesn't count as silence here — as long as progress is being reported, it stays calm. None of this counts as a crash: the application keeps running, and so the next launch doesn't ask about it either.

- **On the Mac, the program no longer found updates — and said it was up to date.** The Mac version didn't bundle a root certificate store; it looked for one in a place that only exists on the machine it was built on. This meant it couldn't verify who it was talking to with any server, and it aborted every connection: no updates, no license activation, no downloading language models, no bug reports. Older versions silently turned this into the message "You are using the latest version." The certificates now sit within the program itself; if it finds none there, it uses the system's, and on the Mac, as a last resort, the keychain's — and if there really are none, it says so instead of claiming to be the latest version. The check itself is never switched off in the process.

  Mac users still need to install this one update by hand: a version that can't reach the server can't update itself either.

### Changed

- **The main window has been decluttered.** At the bottom, six equally sized buttons stood side by side — "About …," "Guide," and "Help & FAQ" among them, even though the same three paths already existed in the Help menu above. They are now combined into one "Help" button that expands them; none is lost. What remains at the bottom are the two paths you actually start with: "Clean" and "Redact by hand …"

- **What the program is currently doing now has a fixed place.** The message ("Loading language models …," "(3 / 7) brief.pdf," "5 of 7 file(s) cleaned.") previously hung as gray text between two button rows. It now has its own area, with a colored dot in front: gray while nothing is running, blue during work, green after a clean run, and yellow when notices have come up. The dot says nothing that isn't already written next to it — it just says it faster.

- **Settings have become their own window.** They previously sat inside the main window — a box with four tabs you expanded under "More settings," which then was too small for its content: a scrollbar always sat inside it, and the choice between anonymizing and pseudonymizing was half out of view. The button is now called "Settings …" and opens a window with a sidebar; each of the four pages fits entirely. The main window no longer jumps to the front on opening, and you can see the file list alongside it. Only where the settings sit has changed — which ones exist and what they do is unchanged.

- **"Details" now expands instead of jumping.** The window previously grew in a single frame, and you had to search for what had changed afterward. It now moves there.

- **Font sizes and spacing follow the same measure throughout the window.** Headings were differently sized in two places, and rows of equal rank stood different distances apart. This is visible as calm, not as an individual change.

- **Anonymizing is now the default.** Pseudonymizing was previously the default: identical people got the same number (`[NAME_1]`, `[NAME_2]`), relationships remained legible — but legally this remained **personal data**. Anyone who changes nothing now gets the method that takes the data out of GDPR scope: all hits of one type are named the same (`[NAME]`). Numbering has remained a choice, it still sits in the same window unchanged; existing settings stay as they are. On the command line, `--pseudonymisieren` (also `--mit-nummerierung`) restores it.

- **Anonymized placeholders can no longer be individually undone.** Anyone anonymizing gets the same placeholder for every person — and so there is no longer a single spot that belongs to a particular name. The touch-up window nevertheless offered "Undo replacement": a click would have inserted *one* of the values at *all* spots. The rows are now dimmed as with redacted items, the click names the reason, and a manually re-marked hit no longer gets a number that appears nowhere else in the document.

  For the same reason, there is no longer a "Translate response back" after an anonymized run — it would previously have put a stranger's name at every person's spot. Anyone who needs that loop chooses "Pseudonymize"; the application now says so too, instead of pointing to an expired mapping.

  On the command line, `--zuordnung` now aborts when anonymizing, instead of writing a file that isn't actually reversible — in the window the checkbox had long been disabled. Either add `--pseudonymisieren` or drop `--zuordnung`; the message says so. No result is produced in this case at all, so a script isn't left standing with half a job done.

- **The update channel now defaults to "Stable."** Without a choice of your own, the channel previously followed whichever build the running version came from — anyone who had once tried a test build was from then on permanently offered test builds. Switching channels is a decision and should stay one; the default is therefore "Stable." Configured channels remain untouched.

### Improved

- **"Beschwerdevorgang" no longer counts as a place name.** In the heading "Aktennotiz – Beschwerdevorgang 12 C 345/26," the program redacted the case along with it: the language model took it for a place, regardless of context. What's now added is not the individual word but the **base word** of the compound — "vorgang" and "notiz" thus also cover business, posting, and payment transactions, or the phone memo. Of thirty tested administrative terms, three previously triggered a false positive, now none do; everything standing next to it continues to be found ("Beschwerdevorgang: Bernd Meisinger" loses the name, not the heading).

- **Anonymizing now keeps records again — for the follow-up pass and the log.** In anonymizing mode, the program did not remember the values it had found. Two things went silent as a result: the document-wide consistency follow-up pass (a surname that later appears alone remained standing) and the list of replacements in the verification log. As long as anonymizing was the rarer choice, this barely stood out — as the default, it would have become the normal case. Nothing changes in the document: the placeholder remains without a number.

- **"Kein personenbezogenes Datum" is now called "keine personenbezogene Angabe."** In the undo dialog and the face warning, the legal term *Datum* stood there — the singular of "Daten." It was read as a calendar date, especially since the application offers "Also remove dates" elsewhere. It is now called "Angabe" everywhere, matching the four reasons above it in the same window.

- **The provenance line now only appears in the "About" window.** "Made with ♥ in Austria" sat at the bottom of the main window right in the middle of the button row and read there like just another button. It continues to appear in the "About" window — where you'd look for it.

- **The drop area now has a visible edge.** Its dashed border was so pale that it barely stood out from the window — that didn't matter as long as the area was just an area. Since it became a control you can tab to, this line is the only thing that shows it as one; it has therefore been raised to the value the standard requires for this.

## 0.10.22-beta.1 – August 15, 2026

### New

- **When clipboard monitoring is turned off, it is really off.** The watcher keeps the last content in memory so the original can be restored — previously even when you had turned monitoring off. History is now forgotten when turning it off. This costs the ability to restore after switching off, and that is exactly the intent: off means off.
- **The error log no longer contains file paths.** It only ever sat on your own computer and was never sent automatically — but it carried paths in plain text, and a file name often reveals more than the content. "…/Scheidung_Mueller_Vergleich.docx" now becomes `<datei>.docx` when written; the extension remains, because it matters for troubleshooting. The same applies to the crash record.
- **The replacement list now warns within itself.** It is the only file in which your original data appears in plain text, and it sits next to the result — anyone handing over a folder hands it over too. The warning now appears as the first line **inside** the file, the output area names the full path instead of just the file name, and on the command line the file is now mentioned at all — previously you never learned there that it had even been created.
- **Anonymizing or pseudonymizing is now a named choice.** Previously, a checkbox stood there: "Name identical people the same — the AI can then still tell who is who." It described the benefit and concealed the consequence: numbered placeholders (`[NAME_1]`, `[NAME_2]`) are **pseudonymization**, and pseudonymized data remains personal data — anyone who believed this anonymized was mistaken. Both methods now stand side by side, each with its cost. The default remains pseudonymizing, because a document that is still meant to be read afterward, or processed by an AI, needs its relationships. When anonymizing, the replacement list is locked: it would make the result traceable again. The manual and FAQ explain the difference in all 18 languages; on the command line, the switch is now also called `--anonymisieren`.
- **The line above the drop area now says what's actually true.** It promised "100% local processing — no cloud, no account, GDPR-friendly." That's true for your documents, but not for the program in this blanket form: it checks for updates, reports errors on request, downloads models, and registers purchased seats. It now carries the narrower, defensible statement: your documents do not leave the computer.
- **The result now always states that it needs to be checked.** Previously, after a clean run, Maskuro reported "12 item(s) removed" in green and nothing else — reading like an assurance that everything was found. Notices only appeared when something specifically couldn't be checked (images, unknown attachments). Now it states unmistakably below every result that not all personal data is detected in every case, that reviewing is up to the user, and that anything missing needs to be added by hand — in the window, in the output area, and on the command line. No dismissible dialog: the sentence stays there permanently. The quick guide now says the same thing, word for word.
- **After an update, the launch shows what has changed.** Previously an update ran silently and was indistinguishable from a restart. "What's new" now appears once — and anyone who skipped a version sees the items from in between as well. Not on the very first launch: there, the quick guide continues to introduce the program.
- **Chinese and Japanese now find names.** Previously they found **none** — not few, none. Both language models lacked word segmentation, without which a sentence with no spaces counts as a single word; the program silently fell back to the multilingual substitute model. Both languages now recognize persons and places like the others. The Japanese dictionary is downloaded together with the language and does not ship with the program — on its own it would be a good 200 MB that everyone else would otherwise have carried too.
- **Romania is now selectable as a country.** It was previously missing entirely. This recognizes Romanian addresses ("Strada Victoriei 30"), postal codes with city ("010061 București"), and the Cod Numeric Personal — the latter only with a matching check digit, so not every thirteen-digit number on an invoice gets flagged. Until now, the postal code remained legible next to the redacted place name in Romanian documents.
- **"Rasterize page" in the editor.** If text cannot be removed from a PDF — this happens with files from foreign generators — the page can now, on request, be replaced by its image: the text is thereby irrevocably gone, the page remains legible and searchable. The warning reporting the case offers the step right there as a button; via "Tools → Rasterize page" it's also available on its own. Undo brings the page back.
- **The interface is now also available in Croatian, Greek, Lithuanian, Slovenian, Japanese, and Korean.** That makes eighteen languages. The manual, FAQ, and legal texts are fully present in all six. The labels in the cleaned document follow the interface: `[NAME_1]` becomes `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]`, or `[氏名_1]`. **For Greek, Japanese, and Korean, the labels are in Latin script** — `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. The interface stays in its own script; only what is written into the document is Latin. The reason is the PDF character set: there, Greek and Japanese labels previously arrived as `[??_1]`, which made it impossible to tell name from place.
- **Nine countries are added, and seven existing ones become complete.** Newly recognized are ID, tax, and social security numbers along with addresses for **Croatia, Slovenia, Greece, Lithuania, North Macedonia, Russia, Ukraine, China, and Japan**. For existing countries, gaps that weighed heavier have been closed: for the **Netherlands** and **Portugal**, there was previously no personal number at all — the Dutch BSN and the Portuguese NIF were not recognized, even though they appear on practically every document from these countries. Poland gets the tax number NIP, Denmark, Norway, and Finland their addresses, Canada its postal code. That makes **35 countries**.

### Removed

- **There is no longer a package for Linux, for the time being.** The source code runs there, but three things this guide promises are missing on Linux: automatic startup, global keyboard shortcuts, and — depending on the desktop environment — the tray icon. Shipping a package that can do less than described would be the wrong path. Windows and macOS are unaffected.

### Improved

- **Case numbers are now found in all languages.** "Aktenzeichen 12/2026-AB" was removed, "File reference 12/2026-AB" or "Sygnatura 12/2026-AB" remained: the field words by which Maskuro recognizes such a number existed only in German. It now knows the equivalents in twelve languages — and as before, only the number is replaced, the label before it remains, so the result shows what was removed there.
- **Maskuro uses about half a gigabyte less at idle.** At startup, the additional model for more precise detection was previously also loaded, so the first cleaning wouldn't have to wait for it. Measured, this cost 648 MB of memory and saved 1.9 seconds — and it cost that even if you only opened the window and closed it again. The model is now loaded the first time it's needed; the status line announces it. The language model continues to load at startup — clipboard monitoring needs it immediately.
- **The drop area can now also be operated without a mouse.** "Drag files here" was an area that reacted to clicks — you couldn't reach it with the keyboard, and a screen reader read it as a frame with text inside, not as what it is. It is now a button: the Tab key jumps to it, Space and Enter open the file picker, and anyone who has tabbed to it sees it by the edge. Via the "File → Select files" menu it already worked before, but you had to know that.
- **The name of the cleaned file is now also read aloud.** In the file list it appears as a second, smaller line below the original — but it was only drawn there, and a screen reader named only the original. Of all things, this line is built against the misconception that a run had no effect, because the untouched original sits in the folder. The line now reads aloud as "rechnung.pdf, result: rechnung_bereinigt.pdf."
- **Controls without a label now say what they are for.** The icon buttons in the file list, the drawing-tool buttons in the touch-up window, and all dropdown and input fields were nameless to screen readers — they were announced as "button" and "combo box," without saying of what. The buttons on a row now also name the file: in a list with twenty entries, you would otherwise hear the same sentence twenty times.
- **Anyone operating by keyboard sees again where they are.** The "Clean" button and the icon buttons in the file list are colored, and this made the frame the system otherwise draws around the focused control stop appearing — tabbing through, the eye landed in empty space. Both now have their own frame once they're in focus. The buttons don't change size in the process.
- **Seven text colors were too pale, in both appearances.** Re-measured against the usual standard (WCAG 2.1), the pale notice lines, the secondary text on the drop zone, the points in the guide, and, in the dark image additionally, blue and red fell below the 4.5:1 threshold — legible in good light with good eyesight, otherwise not. All are raised; the gradation remains, the texts still read as secondary text. Three more — the colors in which warnings and success are reported — only barely held the threshold and were pulled up too: anyone who can't read them can't read whether something went wrong. Only the "Clean" button in dark appearance visibly changed as a result: it now carries dark instead of white text, like the accent buttons of Windows 11 too.
- **Every row of the file list now has its own cross.** Previously you had to select the row first and then click "Remove" — two steps for a small thing. The cross sits on the right of the row and needs one. The "Remove" button below it has therefore been dropped; anyone wanting to get rid of several rows at once selects them and uses the context-menu entry, which also states how many there are. "Remove all" remains. Only the row is ever removed from the list — never a file on disk.
- **Before the AI check, it now states whether this computer is suited for it.** Previously, the window only stated how large the model is. Anyone turning it on with a weak computer only noticed on the first document that it takes very long — after a 5.4 GB download. The window now names memory and free space **beforehand** and says what that means; **afterward**, speed is measured and stated in the size that matters: "A ten-page document takes about 12 minutes on this computer." If it's too slow, the program advises against it and offers to turn the tier back off — it forbids nothing.
- **The speed measurement now runs on every computer.** Previously it only ran if graphics acceleration had additionally been set up — which only exists under Windows. On all other computers, the program therefore estimated the duration based on a different machine, and of all places where it's slow, the estimate was off.
- **Turkish addresses are now also found in a scan.** On a scanned letterhead, "34710 İstanbul" remained legible while the same item disappeared in the text next to it: text recognition reads the Turkish İ without its dot, and the pattern expected a capital letter. The same applied to "Bağdat Caddesi."
- **Spanish addresses without their own street name are found.** "Gran Vía 5" remained, because the pattern expected another name word after the street type — with "Calle Mayor" there is one, with "Gran Vía" the type itself is already the name. The same now applies to "La Rambla" and "Castellana."
- **The "About this program" window now carries a transparency notice** stating that the application was developed with the support of artificial intelligence. It concerns how the program was built, not how it operates: cleaning continues to happen exclusively on your own computer.
- **"Manage languages" now shows the usable languages first.** For half of the 48 languages there is no dedicated language model; there, a multilingual substitute model recognizes names only weakly, in some scripts not at all. Sitting side by side in one list, they all looked equivalent. The default therefore now shows only languages with their own model — via "Shown," the others can be displayed at any time, with a sentence about what they can and can't do. Nothing is removed, and anyone who has set up a restricted language keeps it.
- **The question about a missing language now names the way out.** When a language is detected for which nothing is yet set up, the program previously only offered "Load" or "Continue without." But detection can be wrong — with short forms and lists with little running text, few words decide. The window therefore now states that you can cancel and select the correct language by hand instead of using "Detect automatically." This can, in doubt, save a download of several hundred megabytes for a language that isn't even needed.
- **Placeholder labels now speak the interface language.** "[NAME_1]," "[ADRESSE_2]," and so on previously always appeared in German, regardless of which language was set or in which language the document was written. They now follow the interface language — in English, that's "[NAME_1]," "[ADDRESS_2]." Not the document language: that is guessed with "detect automatically" and sometimes wrong; the interface language never is.
- **Fewer prompts during touch-up.** Where the result is saved now appears permanently at the bottom of the bar ("→ vertrag_bereinigt.pdf," the folder in the tooltip) — a click on it chooses a different location without saving right away. The prompt on first save is thereby dropped. The question "already edited — start over?" can be remembered for the session, and two notice windows that only gave one piece of information now sit in the status line. What remains are the questions that prevent irreversible damage: unsaved work on closing, and the warning about text not removed.
- **The result now states where the scan itself was not readable.** On a scanned document, the device's text recognition doesn't read everything correctly — "Solarstraße 9" might become "Solaret^aß« B." What was misread this way can no longer be found by any check: it looks to every search pattern like letter salad. The program can't do anything about this, but now names such spots with a page number — usually stamps, letterheads, or handwritten additions sit there. A notice, not a warning: with a typeset document, it stays absent.
- **The file list now shows what the result is called.** Below the file name, after the run, the name of the cleaned file appears ("→ vertrag_bereinigt.pdf"). Previously it only appeared in the log behind "Details," and anyone checking the folder found the untouched original. The source's name remains — otherwise it would no longer be visible which file a result came from.
- **The buttons in a finished row are bigger and clearer.** View, touch up, and "Show in folder" were flat icons without an area and got lost in the list — even though, after the run, they're the only thing you still click.

### Fixed

- **On a foreign-language interface, custom rules for redacting, masking, and hashing were silently bypassed.** Anyone who had set names to be redacted instead of replaced got them replaced anyway — as soon as the program wasn't operated in German or English. The setting was there, it just had no effect, and the difference wasn't visible in the result. This affected nine of the twelve interface languages.
- **The "label language" setting had no effect outside German and English.** "German" and "English" could be chosen, but the document still carried the interface language. All three options now work; the default "same as interface" still delivers the same thing as before.
- **Names remained in short text excerpts — e.g. in a copied email quote.** Anyone cleaning an excerpt via the clipboard often got only the email address redacted there, but not the name below it. What decided it was the sheer number of lines: from six lines on, the program recognized the excerpt as a list and found the names; below that it didn't — a copied email quote has five. Any additional line, e.g. a subject, tipped the result. Four lines are now enough, and in measurement all tested names disappear instead of a third. This has no effect on longer documents or on running text.
- **The AI check's graphics acceleration was switched off again as soon as it had been set up.** After setup, the program measures whether the graphics on this computer are really faster than the processor — but this measurement always failed silently, and the result "both equally fast" decided in favor of the processor. Anyone who had downloaded the 65 MB got less than before afterward. The measurement now runs; if it fails, it no longer changes anything.
- **The time estimate computed with a foreign speed on every computer.** It relies on the same measurement; as long as that hadn't run, the development machine's value applied. "About two minutes" could thus mean half an hour on a slow computer.
- **The AI tier works with a new, significantly better language model** (Qwen3.5-9B instead of Qwen3-4B) and is no longer limited to German and English, but works in twelve languages. Measured against the test corpus: the same number of found items as without the tier, but less than half as many unnecessary redactions (75 → 31). The model is larger (5.4 instead of 2.4 GB) and needs about twice the compute time; when turning it on, it is downloaded once, removing the old one in the process.
- **Addresses in French, Italian, Spanish, Portuguese, Polish, Turkish, and Swedish are now removed completely.** Previously only the street and place name disappeared there — house number and postal code remained legible ("[ORT_1] 28, 28013 [ORT_2]"). There were no dedicated address patterns for these languages; they are now added.
- **Greek and Korean found no names at all.** For Greek it was the substitute model — with the dedicated model, which can now be downloaded, names and places are recognized cleanly. For Korean it was the program: it assumed a name begins with a capital letter, and Hangul has no capital letters. This mainly affected short units — table cells, form fields, list entries.
- **A language model that failed to load aborted cleaning.** Instead of an error message, the multilingual model now steps in, and the result points out that the weaker detection was used. Currently affects Chinese and Japanese, whose models need word segmentation not yet bundled with the program.
- **A language with its own model counted as installed as soon as any other one was loaded.** Anyone setting up, say, Turkish, thereby got the multilingual substitute model — and Chinese, Japanese, Korean, or Greek then appeared checked and at "0 MB" in the list, even though their own model was missing. This meant they could never be downloaded and permanently worked with the weaker substitute. The list now shows the actual state along with the download size.
- **A failed detection tier stayed silent.** If "Enhanced detection" or "Maximum detection (AI)" was turned on but the model could not run, the program kept working without the tier — without a word about it. The result looked like any other, and the switch still read "on": you thus took the base tier's result for the best available. The result now says so and names both — what wasn't checked and how to reload the model. This case isn't rare: on some computers the AI tier fails to load when graphics acceleration is missing.
- **An error loading the additional model aborted the whole cleaning.** With "Enhanced detection," only the model's evaluation was safeguarded, not its loading — and that's exactly where it goes wrong if the file is damaged or doesn't match the computer. Instead of an error message, there is now a base-tier result along with a notice.
- **A language could no longer be removed — and thus also not reloaded.** Anyone who unchecked it under "Manage languages" and applied the change read "German removed" but immediately saw the checkbox checked again. The cause was the take-over from the program folder: with an install for all users, the language models sit write-protected in the program folder, and the program fetches missing ones from there instead of downloading hundreds of megabytes again. This take-over ran on every access — and copied the just-deleted language right back in the same breath. It now happens once; downloaded language models are preserved in the process. The program also checks after deletion: what could not be removed is now reported as a failure instead of as "removed."
- **With an install for all users, downloaded content could not be placed.** Anyone who installs the program for all users has it in "Program Files," and nothing may be written there without administrator rights. For language models a fallback location had long been provided, for other things not:
  - The **page preview component** was unpacked into the program folder after a 290 MB download and failed there — without naming a reason. It now sits alongside the language models, where it was always intended to be.
  - **Graphics acceleration** cannot fall back: it swaps libraries within the program itself. Instead of first loading and then failing silently, the program now says beforehand that this isn't possible here and what that means — maximum detection keeps working, just via the processor.
  - A bundled **text-recognition language** could not be removed: it was immediately restored from the program folder. Same cause as with the language models, same fix.
  - When removing a language, **language data of a foreign Tesseract installation** could be deleted. Now only the program's own folder is touched.
  - The fallback location previously only applied under Windows. A Linux archive to `/opt` had the same trouble without the same way out.
- **During touch-up, a whole line disappeared even though only one word was framed.** Anyone who redacted a placeholder in an already-cleaned file lost the line it stood in: "Sehr geehrte Frau Doktor [NAME_1]" left nothing behind — and the message said "one word removed from the document." This affected every file that had already been through the program once, exactly the case touch-up exists for. The rest of the text now remains, in place.
- **"EMPLOYEES" above a name list was itself redacted.** The same case as "MITARBEITER" in 0.10.19, just in English — it had remained there. In all caps, the language model lacks its distinguishing feature, and the heading sits above nothing but real names. The names below it continue to be found. "staff" was not added: it's a documented surname, and the entry would drag along every "John Staff" — the same trade-off as previously with "Arbeiter."
- **The legal form was replaced a second time.** On a scanned letterhead, the language model read "GmbH," the address, and the postal code as **one** place. Address and postal code then cut out their pieces, and what remained was the legal form as its own hit: the result showed "[ORT_1] [ORT_2]," where "[ORT_1] GmbH" was meant. The company name continues to be replaced — only the bare suffix now remains, and the result reads like a letterhead instead of a fill-in-the-blank exercise.
- **A trimmed hit was not re-checked.** The cause of the case above, and it reaches further: the filters against guessed hits ran on what the recognizers **report** — not on what remains after overlap resolution. If a long hit gets trimmed by a stronger recognizer, the fragment is a different text from the one that was judged, and nobody looked at it again. Now they do.
- **"You are using the latest version" — even though it wasn't even possible to check.** Anyone who had set "Preview (Beta)" or "Stable — recommended" as the update channel got this message, even though nothing at all had appeared on these channels yet. The program now says exactly that — and suggests choosing a different channel in settings.
- **Closing the window during loading crashed a thread.** Anyone who started Maskuro and closed the window right away while the language models were still loading got an error report in the log: the loading process reported to a window that no longer existed. There were no visible consequences, but the log recorded a crash where someone had simply been faster than the program.
- **The result is now looked at, not just read.** Previously, a page counted as clean if the value no longer appeared in the text. On a scan, that's not proof — there the visible text is an image. At the end, it is therefore now checked whether the area in the result is really redacted; if bright paper still shows there, the report explicitly says so instead of reporting "replaced."
- **A replaced item remained in the image.** If the value sat on an image — a scanned letterhead, a stamp, a whole scanned page — it was removed from the document text but was still **visible**: what a human reads there are pixels. The report nevertheless said "replaced." The area is now redacted in the image, regardless of which strategy is set, and the placeholder appears bright on this background — ugly, but honest, and the mapping is preserved. If an image format can't be edited, the result now says so explicitly instead of looking clean.
- **On a scan, the placeholder was missing entirely.** The text layer of a scanned page is drawn invisibly, and a placeholder inserted into it inherited that: set, but not visible. Nothing then appeared at the hit location.
- **Text recognition that couldn't run at all counted as passed.** If the language file was missing or the recognition engine crashed, the report said "Image(s) … were checked via text recognition (0 hit(s))" — that is, a check that never happened. On a scan, that's the only check at all: a contract with a legible address in the page image thus counted as done. The report now states that nothing was checked, and why.
- **The language file was searched for in the wrong folder.** If languages other than the document's own sat in the language directory, the recognition engine was given exactly that directory and failed — even though the matching language was sitting right next to it. It now searches for the **language**, not the folder.
- **The warning about text not removed advised something that doesn't exist.** It referred to "Redact as PDF" — but that generates a PDF view of *Office* files and isn't available at all for a PDF. Anyone trying to follow the warning searched in vain. The button that actually does the job now appears there.
- **In the editor, bars and placeholders ended up next to the marked spot.** This affected every PDF where a line ends on a hyphen and the word continues on the next one — with scans this stands out especially, because contract texts are set with hyphenation throughout. The two line halves counted as *one* word spanning across the type area, and every frame near it took on this extent. Detection itself doesn't change as a result: the measurement corpus delivers the same result as before.
- **The editor warned that the text "is still in the document," even though it had been removed.** If the same word occurred several times on a page — the rule in contracts — the self-check reported a failure after every intervention. It now counts occurrences instead of merely checking whether the word still appears somewhere. On a genuine failure it still warns, unchanged.
- **The result file was called "_bereinigt" in every language.** The intent was always that the name suffix follows the interface language — in English it did ("_cleaned"), in the other sixteen languages it didn't. Anyone using the program in Finnish got "asiakirja_bereinigt.pdf." The file is now called "asiakirja_puhdistettu.pdf," in Japanese "書類_除去済み.pdf," and so on — each with the word the same interface uses in its completion message. Anyone who has set a custom suffix keeps it.
- **"Manage languages" always labeled itself in German.** In the list of 48 document languages, the German names appeared regardless of which interface was set: a Finnish user read "Chinesisch." The name now appears in its own language followed by the endonym — "Kiina (中文)." The endonym is deliberate: anyone who recognizes a language by its own name finds it even when the Finnish word means nothing to them.

## 0.10.19 – August 12, 2026

### Improved

- **The context-menu entry now speaks your language.** Previously it appeared in German wording on every system — even on an English Windows. It now follows the configured interface language, and anyone switching languages gets the entry renamed immediately, without reinstalling. (Windows; on macOS and Linux the menu name is also a file name — that comes later.)
- **The editor now remembers which view you last worked in.** Anyone using the page view gets it automatically for the next document — without turning it on every time. Anyone who has never used it notices nothing: it is only restored if the component needed for it is already loaded; nothing is ever downloaded for this purpose.

### Fixed

- **"MITARBEITER" above a name list was itself redacted.** In staff directories and org charts, the heading disappeared as a supposed name — it sits there above nothing but real names, and in all caps the language model lacks its distinguishing feature. The names below it continue to be found.
- **Quantities were mistaken for addresses.** In invoices, delivery notes, and inventory lists, items such as "3390 Protokoll," "1030 Betrag," or "3390 Lager" disappeared as a supposed postal code with a city — any four-digit quantity looks like an Austrian postal code. If a word the application knows as a factual word, department, activity, or field label stands after the number, it now remains. Genuine location data is unaffected, including cases that are themselves such a word ("4692 Ort"). Not solved by this: the case where a completely ordinary word stands after the number ("3390 Regal") — that would need a postal-code directory.
- **Help named a menu entry that doesn't exist.** The manual, an image, and the message at the end of installation spoke of "Clean document for AI"; but the context-menu entry is called "Remove personal data." Anyone following help searched in vain. All three spots now name the menu entry as it really is.
- **"Start with the system" could not be turned off.** Anyone who had checked "Start with Windows" during installation still saw an empty checkbox in settings — and worse: turning it on and off within the application had no effect, the program kept starting with Windows regardless. The cause was two places Windows looks for startup programs; the application only knew one of them. Both now count, the switch shows the true state and works in both directions. Also accounted for: anyone who disables the entry in Task Manager now sees this reflected in the application — and turning it back on there cancels the disabling.
- **Headings above name lists were redacted.** "TEILNEHMERLISTE WERKSTATTGESPRÄCH" or "MITARBEITERÜBERSICHT INNENDIENST" above a list of people disappeared as a supposed name. In all caps, the language model lacks its best signal, and in German every noun is capitalized — "Teilnehmerliste Werkstattgespräch" then looks like "Anna Huber." Compounds ending in `-liste`, `-dienst`, `-gespräch`, `-sitzung`, and `-besprechung` now remain. The base words alone continue to count as a name: *Liste* and *Dienst* are documented surnames, *Teilnehmerliste* is not.
- **Vertically set data got an illegible placeholder.** Case numbers in the margin, clerk initials next to the gutter, vertical table headers: such items were found and removed, but the placeholder came out sideways across the text, squeezed to one or two points, and sometimes running past the edge of the paper. It now follows the text — vertically, at legible size, and in the same direction the item stood in. The same applied to pages that were subsequently rotated (horizontally written text with a recorded page rotation, as some output programs produce); there too, the placeholder now appears the way you view the page. "Sehr geehrte Frau Doktor Anneliese Berger" only yielded "Anneliese" as a name — "Berger" remained in the document. The same affected every name with a middle name ("Frau Anna Maria Berger"). The cause was the rule for the name behind a salutation: it had two word slots, and a title or a middle name used up the first one. With "Dr." it never showed up — the period breaks the rule, and the language model caught the whole name. Titles are now skipped without costing a slot, and the name may consist of three parts. A role **after** the name still isn't included: "Frau Anna Huber Geschäftsführerin" replaces the name, not the role.
