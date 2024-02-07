# Testrapport

### Plan for testing
- Test prosedyren jeg bruker under er inspirert av den Cecilie lagde for Westcon prosjektet sine apper
- Data/Functions
  - Does the data display correctly?
  - If changes are made, test all functionality that might have been affected.
  - If the data is editable, ensure the view includes PrimKey and ID fields.
  - Ensure all input fields match the datatype of the column. And that only editable columns are editable in the app.
  - Are all alerts automatically closed?
  - Are all datasources sorted?
  - Are all numbers and dates formated and aligned correctly?
  - Is there a userfriendly 'no data' message?
  - Ensure that the following columns exists in aviw used in grids (For record information): ID, PrimKey, Created, CreatedBy_ID, Updated, UpdatedBy_ID

- Layout
  - Use the browsers built-in accessibility developer tools to test for any common issues
  - Check if there are any clickable surfaces on touch/mobile that are too small or closely placed, and therefore making them difficult to separate.
  - Check if all focusable elements have a proper label (with no typographical errors).
  - Remove any unused CSS, JavaScript, or other libraries.
  - Ensure apps are cross-browser compatible. As a minimum, based on latest client data, apps shall be tested for compatibility with both Chrome and Firefox latest versions.
  - Ensure all strings in the UI are localized, and that there are no typographical errors.
  - Check placements and styling of buttons.
  - Ensure that sorting is implemented on all relevant columns.

<details open>
  <summary><h3>Kode</h3></summary>

  <table>
    <tr>
      <th>App</th>
      <th>Beskrivelse</th>
      <th>Resultat</th>
    </tr>
    <tr>
      <td>dennis-magnussen-shopping-lists (Liste visning/Hoved App)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>dennis-magnussen-shopping-list (Vare visning/Detalije App)</td>
      <td></td>
      <td></td>
    </tr>
  </table>
</details>
<details open>
  <summary><h3>Hoved Side</h3></summary>

<table>
    <tr>
      <th>Funksjoner</th>
      <th>Beskrivelse</th>
      <th>Resultat</th>
      <th>Bilder</th>
    </tr>
    <tr>
      <td>Navigere rundt</td>
      <td>Sjekk om liste visningen er i henhold til universiel utforming. Sjekk at ting viser og åpner som den skal. Sjekke om knapper er for små eller for store. Tilpass appen for alle størrelse mobiler</td>
      <td>Navigering funket flott og designet funket for mange mobil størrelser. <br> Issue: Var ingen hjelpsom text når Shared Lists var tom (Fikset).</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/9dd2b8fa-289d-4d1d-9bdf-798c2791b7af" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/319bd0fd-9419-4dfb-b784-567c8eb14b0e" width="60" /></th>
        </table>
      </td>
    </tr>
    <tr>
      <td>Redigering av Liste</td>
      <td>Sjekk om en kan endre listens info. sjekk om det går an å slette listen. Sjekk om share list funksjonen fungerer</td>
      <td>Hvis en byttet kategori så ville ikke endringen vises. Trigger stoppet meg for å slette listen. Share list funket bra.</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/b5f50efb-4565-4f67-aae7-5e8c0faea1fe" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/74112c6c-1dd7-4683-8a49-53b5e4bd9b35" width="60" /></th>
        </table>
      </td>
    </tr>
    <tr>
      <td>Lage ny liste</td>
      <td>Sjekk om oppretting av ny liste funker som den skal. Modalen, Input, validering og omdirigering</td>
      <td>Funket som den skulle. Duplikat sjekk funket. Ble omdirigert til vare visning.</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/4d8b6e5f-6958-41a0-931e-b365397b2ed9" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/d9f553bb-f381-4e79-80de-ac330a442952" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/19730810-0daa-4088-8240-392f027bb483" width="60" /></th>
        </table>
      </td>
    </tr>
</table>
</details>

<details open>
  <summary>
    <h3>Detalje Side</h3>
  </summary>

<table>
    <tr>
      <th>Funksjoner</th>
      <th>Beskrivelse</th>
      <th>Resultat</th>
      <th>Bilder</th>
    </tr>
    <tr>
      <td>Navigere rundt</td>
      <td>Sjekk om vare visningen er i henhold til Univerisell utforming. Knapper for små? rett fargebruk? Størrelse?</td>
      <td>Knapper var passelig størrelse. Delete knapper burde vere rød. Ellers åpner alt fint og designet er enkelt å forstå.</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ec702b4e-e0ae-4688-ad26-b2b545fffd81" width="60" /></th>
        </table>
      </td>
    </tr>
    <tr>
      <td>Ny vare funksjon</td>
      <td>Kan en legge til varer? Funker både "select item" og "Personal Item"? Kan man justere kvantitet? Går det an å lage nye varer?</td>
      <td>Personal Item var ikke aktive (Se bilde 1). Modalen passet akkurat hele skjermen på små mobiltelefoner, Kvantitet burde være vestrestillt (se bilde 2). Duplikat vare sjekk funker på både "Create New Item" og "Add New Items(s)". Varene blir lagt inn som den skal.</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/7d3f861d-23ff-4b81-9a58-e38cc650dee5" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/0ea4f61f-ac24-475a-a9c4-57662e7c0b83" width="60" /></th>
        </table>
      </td>
    </tr>
    <tr>
      <td>Redigering av liste inni vare visning</td>
      <td>"People shared with" modal. "Edit List" modal</td>
      <td>"Edit list" funker som den skal, kunne kanskje ha fjernet scrollbaren på bunnen. samme gjelder "People shared with" (se bilde 2).</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ed3f79a1-27c3-4780-bc36-b59ec82f805a" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ffa0a464-6586-4b0c-87b9-36ed27ffb003" width="60" /></th>
        </table>
      </td>
    </tr>
    <tr>
      <td>Vare redigering og avmerkning</td>
      <td>Sjekke om vare avkryssing fungerer og er lett synlig. Sjekke om redigering av vare funker (PersonalItem og Selected Item modal). </td>
      <td>Avskrysning på varer funker flott (bilde 1). Går an å slette vare og redigere varen. Modalen forandrer seg basert på hvilke type vare det er (bilde 2 og 3). Funker bra</td>
      <td> 
        <table>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/57c64a3f-6d46-4ec6-b15a-646f2f7d7ed9" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/0331a94d-f579-48c1-9f69-dc60ab6a4aff" width="60" /></th>
          <th><img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/82739d3e-edea-4fa2-9cdf-0ae496548179" width="60" /></th>
        </table>
      </td>
    </tr>
</table>
</details>
