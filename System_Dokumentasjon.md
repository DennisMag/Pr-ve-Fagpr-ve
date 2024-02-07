
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

- Appframe 365 (NT)
- Vue.js
- [Bootstrap](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
- [Bootstrap Icons](https://icons.getbootstrap.com)
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
          <td>atbl_DennisMagnussen_Lists</td>
          <td>
            Kun brukere som har tabellen i permissiontables får lov å lage ny liste.
          </td>
          <td>
            Kun brukere som har tabellen i permissiontables og har lagd lista kan redigere.
          </td>
          <td>
            Kun brukere som har tabellen i permissiontables og har lagd lista kan slette den.
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/2873e437-e421-4458-9430-ba7c4a84ec3e" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/633879f7-b9e1-4496-aa92-c3ce4f9fac41" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/d2f2a337-c603-4263-8f64-2d90ffae3293" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>atbl_DennisMagnussen_Items</td>
          <td>
          <p>
            Kun brukere som har tabellen i permissiontables får lov å legge til her. Har en sjekk som stopper deg fra å legge til en vare som allrede eksisterer.
          </p>
          </td>
          <td>
          <p>
            Kun brukere som har tabellen i permissiontables får lov til å oppdatere.<br>
          </p>
          </td>
          <td>
          <p>
            Kun brukere som har tabellen i permissiontables får lov å slette varer
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/f6b4e821-d8fc-4dd1-9c82-d10f34640797" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/ad05a4e4-7203-4428-a7f2-cc4725b8f09c" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/a336b9dd-d08b-4f91-85e5-c8fed418ea0c" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>atbl_DennisMagnussen_ListsItems</td>
          <td>
           Kun brukere som har enten lagd lista eller har blitt tildelt lista har tilgang til å legge til nye varer Må også ha tabellen i permissiontables.<br>
          </td>
           <td>
            Kun brukere som har enten lagd lista eller har blitt tildelt lista har tilgang til å Redigere. Må også ha tabellen i permissiontables.<br>
          </td>
           <td>
           Kun brukere som har enten lagd lista eller har blitt tildelt lista har tilgang til å slette. Må også ha tabellen i permissiontables.
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/45b96cc2-70db-4237-a26c-0cdef9045487" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/fafacb52-2b96-49e8-b5f6-2cbed1a1b3c2" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/dbb916e3-f86d-4276-bc18-7009d7eeaead" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>atbl_DennisMagnussen_ItemsTEMP</td>
          <td>
            Kun brukere som har tabellen i permissiontables får lov å legge til her. Hvis 
          </td>
          <td>
             Bare brukere som eier handelisten kan oppdatere hvem som skal kunne se den.
          </td>
          <td>
            Bare brukere som eier handelisten kan fjerne delte folk.
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/235ab8bc-1b15-440f-98cb-6d934c7adefd" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/07b90565-1e37-436d-812c-8bcbdfb9be80" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/dac51ae5-5540-4e60-bdb5-f7a31f3c0a78" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>atbl_DennisMagnussen_SharedLists</td>
          <td>
            Bare brukere som eier handelisten kan dele den videre. Må også ha tabellen i permissiontables.
          </td>
          <td>
             Bare brukeren som har lagd listen kan oppdatere hvem listen er delt med. Må også ha tabellen i permissiontables.
          </td>
          <td>
            Brukeren som har lagd listen kan fjerne delte folk og brukere som har blitt tildelt listen kan fjerne seg selv som delt person. Må også ha tabellen i permissiontables.
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/235ab8bc-1b15-440f-98cb-6d934c7adefd" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/07b90565-1e37-436d-812c-8bcbdfb9be80" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/dac51ae5-5540-4e60-bdb5-f7a31f3c0a78" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>atbl_DennisMagnussen_Categories</td>
          <td>
            Bare Dennis som kan legge til nye kategorier
          </td>
          <td>
             Bare Dennis som kan oppdaere kategorier
          </td>
          <td>
            Bare Dennis som kan fjerne kategorier
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/235ab8bc-1b15-440f-98cb-6d934c7adefd" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/07b90565-1e37-436d-812c-8bcbdfb9be80" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/dac51ae5-5540-4e60-bdb5-f7a31f3c0a78" width="60" />
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
      <td>aviw_DennisMagnussen_Lists</td>
      <td>
        View for visning av lister lagd av seg selv.<br>
        Viewet inneholder info om lista. Lagt til ItemStatus kolonne for status på hvor mange varer er sjekket av og IsPersonalList bitfelt for å ikke rendere inn "Select Item" når en skal legge til nye varer
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_ListsItems</td>
      <td>
        View for visning av varer.<br>
        Viewet inneholder info om varen. Lagt til IsPersonalItem bitfelt for å få en annen visning for varer som ikke er lagt inn med lookup.
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_SharedLists</td>
      <td>
        View for vising av lister delt med deg.<br>
        Viwet inneholder info om listen og hvem det er lagd av. Lagt til ItemStatus kolonne for status på hvor mange varer er sjekket av.
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_SharedToPersons</td>
      <td>
        View for visning av hvilket personer som lista er delt med
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_Categories</td>
      <td>
        View for katergorier som lister skal grupperes med.<br>
        Lagt til HasLists bitfelt for å ikke rendere inn kategorien hvis den ikke har noen lister.
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_ItemsTEMP</td>
      <td>
        View for preview av varer som skal bli lagt til.
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_PersonsLookup</td>
      <td>
        View for lookup av personer med rollen "Test-Fagprøve".
      </td>
      <td>
       <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/78e0cd7e-7fe2-4b99-acac-f2afabc8d5be" width="60" />
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
