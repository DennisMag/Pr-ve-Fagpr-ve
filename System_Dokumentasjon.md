
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
- [DrawSQL](https://drawsql.app/)
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
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/613f00a4-51e2-4428-aa4c-adeaaf9c8a0c" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_ListsItems</td>
      <td>
        View for visning av varer.<br>
        Viewet inneholder info om varen. Lagt til IsPersonalItem bitfelt for å få en annen visning for varer som ikke er lagt inn med lookup.
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/7b5bdd56-8996-4f2d-af1c-1d4942d57173" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_SharedLists</td>
      <td>
        View for vising av lister delt med deg.<br>
        Viwet inneholder info om listen og hvem det er lagd av. Lagt til ItemStatus kolonne for status på hvor mange varer er sjekket av.
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/72a0b397-73f7-4bf4-9396-c7737f917ed6" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_SharedToPersons</td>
      <td>
        View for visning av hvilket personer som lista er delt med
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/1137e0f1-1836-400f-8a60-a4f473896220" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_Categories</td>
      <td>
        View for katergorier som lister skal grupperes med.<br>
        Lagt til HasLists bitfelt for å ikke rendere inn kategorien hvis den ikke har noen lister.
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/dabf118b-50da-4b37-ba17-f7fdb884819f" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_ItemsTEMP</td>
      <td>
        View for preview av varer som skal bli lagt til.
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/e4acebed-14a1-4eef-82fa-200c333a1260" width="60" />
      </td>
    </tr>
    <tr>
      <td>aviw_DennisMagnussen_PersonsLookup</td>
      <td>
        View for lookup av personer med rollen "Test-Fagprøve".
      </td>
      <td>
       <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/bc1d21bb-5f5c-4f7d-a152-eb5d90348f51" width="60" />
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
  Authentication, Authorization. 
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
    
For å sikre kvalitet på appen(e), har jeg laget en [Testrapport](https://github.com/DennisMag/Pr-ve-Fagpr-ve/blob/main/Test_Rapport.md) der jeg har gått over funksjonene i appen.

<hr />
</details>
<details open>
  <summary>
    <h2>Grensesnittbeskrivelse</h2>
  </summary>

- For beskrivelse hvordan applikasjonen brukes se:
  [Brukerveiledning](https://github.com/DennisMag/Pr-ve-Fagpr-ve/wiki)

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
        <tr>
          <td>Opprette ny handleliste</td>
          <td>
          <p>
            Her vil bruker kunne opprette ny handeliste. <br>
            <br>
            Løser dette med å åpne en CreateNewList Modal komponent jeg har laget. importerer komponenten og gir det en ref. 
            innpå modal komponenten defineExposer jeg refen til den faktiske modal og da kan jeg hente ut den ut via den importerte komponenten. Kjører da en .Show() får å vise fram modal komponenten (Se bilde 1).<br>
            Inn i modalen har jeg lagt til noen input felt pakket inn i en form element. Da får jeg lagt inn en verifisering av inputen med å legge inn "required" (Se bilde 2).<br>
            For å lage lista bruker jeg en procedure som jeg laget i SQL. Den tar inn parameterene "ListName, Category_ID og Description" (Se bilde 3).<br>
            Proceduren sjekker først om navnet ikke er allerede brukt i valgt kategori. så inserter den inn i Lists og tar ID som var lagt inn og selecte det sånt at vi kan da hente den ut i javascript koden (Se bilde 4).<br>
            Tilslutt så åpner vi lista.
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/7dc6e07c-f738-4c62-923c-316750cbcdb9" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/9474d436-5567-43ce-9c9c-11043997b424" width="60" />
              </th>
                <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/8d4bfc0d-c3d7-4dd7-b9f5-793215052b19" width="60" />
              </th>
                <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/fef26d42-d8b7-4993-b5c3-e8f0d4bc5b0b" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/cfef533e-1451-434d-89f2-538538e47751" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/d7fdae51-854c-4bb8-8cfc-6d5029439948" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>Redigere handle liste</td>
          <td>
          <p>
            For å redigere handle liste åpner vi en omega komponent som heter ActionSheet. 
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/e4f23ce9-23ef-4a5c-9ed7-b7ece5e756b6" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/9474d436-5567-43ce-9c9c-11043997b424" width="60" />
              </th>
                <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/8d4bfc0d-c3d7-4dd7-b9f5-793215052b19" width="60" />
              </th>
                <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/fef26d42-d8b7-4993-b5c3-e8f0d4bc5b0b" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/cfef533e-1451-434d-89f2-538538e47751" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/d7fdae51-854c-4bb8-8cfc-6d5029439948" width="60" />
              </th>
            </table>
          </td>
        </tr>
      <table>
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
          <td>Opprette ny handleliste</td>
          <td>
          <p>
            Her vil bruker kunne opprette ny handeliste. <br>
            Dette er løst med å kalle på en funksjon med -1 index for å lage ny rad. (Bilde 1).<br>
            Funksjonen setter da indeksen på datasourcen til indeksen fra parameteren og setter CreateNewRef verdien til true.<br>
            Indeksen settes for å kunne redigere rett rad i modalen eller for at den ikke skal vise en annen verdi når en lager ny liste siden denne funksjonen brukes til å både opprette og redigere handeliste (bilde 2). <br>
            CreateNewRef brukes for å justere på modal tittel og lagringsknappen avhengig om bruker skal opprette eller redigere (bilde 3).
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/b947ce12-290c-414b-aceb-fc4d5aa65b3e" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/a666985a-2cd5-4afc-b32b-540a0de20924" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/188f3c55-8baa-47da-bdc3-b784847bae06" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/0e7025e5-3653-4cb3-8b30-7a2a24dc85a4" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/54504e25-327b-41a7-882f-655ba58521e8" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/084497fa-64c4-493d-aafb-babf1261a1c2" width="60" />
              </th>
              <th>
                <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/3012eb71-ba13-4c74-b8fb-398c4d633f3f" width="60" />
              </th>
            </table>
          </td>
        </tr>
      <table>
    </details>
    
<hr/>
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
      - Arvid (Dokumentasjon for fagprøven)
    </li>
  </ol>
 
<hr />
</details>


<!-- Legg til URL for tabellstruktur her -->
[tablestructure-url]: https://drawsql.app/teams/asdfasfd/diagrams/handleliste
