# GTM Alpha Consultation Form (historical)

This is a historical form, replaced by https://gtmalpha.gtmhelix.com/consultation.

This repository holds one file, `index.html`. The page is still published from it at https://shashwatgtm.github.io/gtm-alpha-consultation/, but it is kept only as an archive. Use the address above for a consultation.

## What index.html does

It is a single static page: HTML, CSS and one inline script, with no build step and no package. The form on it is called "GTM Alpha Consultation Form".

### The ten fields it sends

When the form is submitted, the script reads these ten fields (the names are the JSON keys it sends):

1. `client_name` (Your Name)
2. `client_designation` (Your Role/Title)
3. `company_name` (Company Name)
4. `company_description` (Company Description)
5. `gtm_challenge` (Primary GTM Challenge)
6. `business_stage` (Business Stage, a drop-down)
7. `industry` (Industry, a drop-down)
8. `current_team_size` (Current Team Size, a drop-down)
9. `budget_range` (Budget Range for GTM, a drop-down)
10. `specific_focus` (Specific Focus Area)

The form also has a required checkbox, `confirm_consultation`. It must be ticked to submit, but it is not one of the ten values sent (index.html lines 654 to 665).

### Where it posts

The backend address is set at index.html line 619: `https://web-production-0616.up.railway.app`.

- On submit, the page sends the ten fields as JSON with a POST to `https://web-production-0616.up.railway.app/api/gtm-consultation` (index.html line 669).
- It then shows the backend's reply on the page: a consultation id, a primary focus, four EPIC scores (E, P, I, C), and links that the backend returns (a report link, a console link and a dataset link). The page puts that reply into the HTML as text it receives from the backend.

### The health request on page load

As soon as the page loads, it sends a GET request to `https://web-production-0616.up.railway.app/health` (index.html lines 622 and 626). It only writes the result to the browser console: whether the reply says `healthy` and whether `apifyClientReady` is set. Nothing on the page changes because of it.

### Other things in the file

- The form tag carries the attributes `toolname`, `tooldescription` and `toolautosubmit`, which describe the form to software that can fill in and submit forms for a user.
- The page does not generate a report itself, and it has no demo mode. Any report comes from the backend.

## What this repository cannot show

- The backend's code is not in this repository. What the backend stores, where, and for how long is not documented here, and nothing in this repo proves it.
- The page itself shows the sentence "Your data is processed securely and never stored permanently." That is text written on the page. This repository cannot confirm it.
- Whether the backend address above still answers is not shown here either.

## Archive status

This repository is an archive candidate. Archiving it is an account step for the owner.

## Contact

Shashwat Ghosh: https://gtmexpert.com/contact-shashwat-ghosh
