
# System Dokumentasjon

<details>
  <summary>
    <b>Table of Contents / Innhold</b>
  </summary>
  <ol>
    <li>
      <a href="#funksjonelle-krav">Funksjonelle krav</a>
    </li>
    <li>
      <a href="#teknologier">Teknologier</a>
    </li>
    <li>
      <a href="#teknologier">Arkitektur</a>
       <ul>
        <li>
          <a href="#tabeller">Tabeller</a>
          <ul>
            <li>
              <a href="#sikkerhet-i-tabeller">Sikkerhet i Tabeller</a>
            </li>
          </ul>
        </li>
        <li>
          <a href="#views">Views</a>
        </li>
      </ul>
    </li>
    <li>
      <a href="#sikkerhet">Sikkerhet</a>
    </li>
    <li>
      <a href="#testing">Testing</a>
    </li>
    <li>
      <a href="#grensesnittbeskrivelse">Grensesnittbeskrivelse</a>
    </li>
    <li>
      <a href="#hindringer-under-utviklingen">Hindringer under utviklingen</a>
    </li>
    <li>
      <a href="#avvik-fra-plan">Avvik fra plan</a>
    </li>
    <li>
      <a href="#kilder">Kilder / Ressurser</a>
    </li>
  </ol>
</details>


<details open>
  <summary>
    <h2>Funksjonelle krav</h2>
  </summary>
    
- Mulighet for registrering og innlogging for brukere.
- Støtte for flere lister.
- Må være lett for brukeren å vite hva som er handlet, og hva som gjenstår.
<hr>
</details>
<details open>
  <summary>
    <h2>Teknologier</h2>
  </summary>

- INSERT TEKNOLOGIER HER
<hr>
</details>
<details open>
  <summary>
    <h2>Arkitektur</h2>
  </summary>
  
 <ul>
    <li>
      <details>
          <summary>
            <h4>Tabeller</h4>:
          </summary>
        
  [Tabellstruktur][tablestructure-url]
        
   <details>
      <summary>
        <h4>Sikkerhet i Tabeller</h4>:
      </summary>

  For tilgangsstyring så er sql triggere brukt.<br>
  Disse sørger for at ikke hvem som helst får lov å legge til, oppdatere eller slette rader.

  <table>
        <tr>
          <th>Tabell Navn</th>
          <th>Regler Insert</th>
          <th>Regler Update</th>
          <th>Regler Delete</th>
          <th>Bilder</th>
        </tr>
        <tr>
          <td>
            Ditt Tabellnavn her
          </td>
          <td>
            Insert regler her
          </td>
          <td>
            Update regler her
          </td>
          <td>
            Delete regler her
          </td>
          <td>
            <table>
      <th>
<img
              src="bilde_av_insert_trigger"
              width="48"
            />
</th>
      <th>
<img
              src="bilde_av_update_trigger"
              width="48"
            />
</th>
      <th>
<img
              src="bilde_av_delete_trigger"
              width="48"
            />
</th>
  </table>
          </td>
        </tr>
      </table>
  </details>
      </details>
    </li>
    <li>
      <details>
          <summary>
            <h4>Views</h4>:
          </summary>
        
  <table>
  <tr>
    <th>View Navn</th>
    <th>Beskrivelse</th>
    <th>Kode</th>
  </tr>
  <tr>
    <td>DITT_VIEW_NAVN_HER</td>
    <td>
      View for å blalblalblal
    </td>
    <td>
<table>
<th>
     <img src="bilde_av_view_her" width="60" />
</th>
</table>
    </td>
  </tr>
</table>
      </details>
    </li>
  </ul>
  
  <hr />
</details>
<details open>
  <summary>
    <h2>Sikkerhet</h2>
  </summary>
    
  Sikkerhet er løst ved hjelp av Appframe roller og moduler.
  Bruker får tildelt en rolle. Rollen er koblet til en egen modul som da gir brukeren tilgang til appen(e) og tabellene.
  
  ![image](https://github.com/ArvidWedtstein/Fagproove/assets/71834553/0a9f2864-7bc9-4ea0-9a3f-412339a1ea1f)
  ![image](https://github.com/ArvidWedtstein/Fagproove/assets/71834553/8647a516-2559-4f8b-9969-6d4cdfa02892)

<hr />
</details>
<details open>
  <summary>
    <h2>Testing</h2>
  </summary>
    
For å sikre kvalitet på appen(e), har jeg laget en [Testrapport](https://github.com/ArvidWedtstein/Fagproove-Template/blob/main/Test_Report.md) der jeg har gått over funksjonene i appen.

<hr />
</details>
<details open>
  <summary>
    <h2>Grensesnittbeskrivelse</h2>
  </summary>

- For beskrivelse hvordan applikasjonen brukes se:
  [Brukerveiledning](https://github.com/ArvidWedtstein/Fagproove-Template/wiki)

- Under finner du beskrivelse av funksjonaliteten sammen med litt kode:

    <details>
      <summary>
        <h5>Hoved Side</h5>
      </summary>
      <table>
        <tr>
          <th>Funksjoner</th>
          <th>Beskrivelse</th>
          <th>Kode</th>
          <th>Bilder</th>
        </tr>
<!-- Eksempel: -->
        <tr>
          <td>Opprette ny handleliste</td>
          <td>
          <p>
            Her vil bruker kunne opprette ny handeliste. <br>
            Rett er løst med å kalle på en funksjon med -1 index for å lage ny rad. (Bilde 1).<br>
            osv....
          </p>
          </td>
          <td>
<table>
  <th>
<img src="ditt_bilde_av_kode_her" width="60" />
</th>
</table>
          </td>
          <td>
<table>
  <th>
<img src="ditt_bilde_av_ui_her" width="60" />
</th>
</table>
          </td>
        </tr>
      </table>
    </details>

  <details>
    <summary><h5>Detalje Side</h5></summary>

    <table>
        <tr>
          <th>Funksjoner</th>
          <th>Beskrivelse</th>
          <th>Kode</th>
          <th>Bilder</th>
        </tr>
      <tr>
          <td>Legge til ny vare</td>
          <td></td>
          <td>
<table>
  <th>
<img src="ditt_bilde_av_kode_her" width="60" />
</th>
</table>
</td>
          <td> 
<table>
  <th>
<img src="ditt_bilde_av_ui_her" width="60" />
</th>
</table>
          </td>
        </tr>
      </table>
    </details>
    
<hr />
</details>
<details open>
  <summary>
    <h2>Hindringer under utviklingen</h2>
  </summary>

  <ol>
    <li>
      <p>
        Under utviklingen så møtte jeg på NT. Dette var et stort problem.
      </p>
      <table>
        <th><img src="bilde_av_nt_her" width="60"></th>
      </table>    
    </li>
  </ol>
<hr />
</details>
<details open>
  <summary>
    <h2>Avvik fra plan</h2> (Endringer under utvikling)
  </summary>

  <ol>
    <li>
      <p>
        Insert ditt avvik her.
      </p>
    </li>
  </ol>
 
<hr />
</details>
<details open>
  <summary>
    <h2>Kilder</h2>
  </summary>

  <ol>
    <li>
      Insert dine kilder her
    </li>
  </ol>
 
<hr />
</details>


<!-- Legg til URL for tabellstruktur her -->
[tablestructure-url]: https://drawsql.app/teams/asdfasfd/diagrams/handleliste
