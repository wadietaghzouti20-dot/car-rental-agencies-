# RENDEVO Rent

A responsive French-language car-rental request frontend for GitHub Pages.

## Configure the backend
1. Create a Google Sheet for this rental business.
2. Open **Extensions → Apps Script** and install the RENDEVO Rent backend script.
3. Run `setupRENDEVO()` once and authorize it.
4. Deploy as a Web App: **Execute as Me**, **Who has access: Anyone**.
5. In `index.html`, replace `PASTE_YOUR_RENDEVO_RENT_APPS_SCRIPT_EXEC_URL_HERE` with the deployed `https://script.google.com/macros/s/.../exec` URL.
6. In the spreadsheet's `Vehicules` tab, add one vehicle per row:
   - ID véhicule (unique)
   - Marque
   - Modèle
   - Catégorie
   - Immatriculation
   - Tarif journalier (DA)
   - Disponible (Oui/Non)
   - Image URL
   - Notes

## Publish with GitHub Pages
Open **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/(root)`, then save.

## Frontend API calls
- GET `?action=vehicles`
- POST booking JSON as `text/plain` to avoid CORS preflight
- Backend should validate date ranges and overlapping reservations on the server

## Customer-facing status
The website submits a **rental request pending agency confirmation**. It does not claim that a vehicle is reserved until the agency confirms availability and terms. Add the real agency's rental conditions, required documents, insurance and deposit information before public customer launch.
