
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
- lage støtte for å dele handlelister med andre brukere. 
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
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/d9a188fa-13fa-412b-90d7-2c03b53f38e0" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/12ae0d1a-7934-4ebb-b156-4a5ecd178299" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/12683ff7-abf1-4ea8-8a18-d3d4650ba0a2" width="60" />
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
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/14437ced-d4ee-4751-b88f-71f29f9465fe" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/28102d2f-920b-40fc-9e39-23bfa14e5b60" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/d6be6b43-2f78-4b17-8625-7208a6481a04" width="60" />
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
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/7869c0cb-9bc9-4a42-807e-36a5e1ac4956" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/278503f9-e323-46c3-889b-4a916191966d" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/fcd0d73b-6dbe-47ae-94df-ed9a3ee541be" width="60" />
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
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/10318051-acd2-4219-aa0d-47362a824ad2" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/06bc3f0a-9e6a-4dd3-a6b8-e96d2fa2f6d5" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/501494bf-a9ec-4023-8a6b-e42552d3af4e" width="60" />
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
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/eb87b287-3208-4f91-8f48-c53aa5d90ee7" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/42e3296f-ddd9-4e3f-8437-482462f97e11" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/843de8cb-0dc0-4f09-a84b-b66f981039b7" width="60" />
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
  Autentisering blir gjort med SQL eller microsoft login. Det blir også brukt Two-Factor authentication for ekstra lag med sikkerhet.
  Appframe bruker også rolle basert sikkerhet. Bruker får tildelt en rolle som har en sett med tilgang på forskjellige ting. 
  Rollen blir også koblet opp mot en Module som har utvalgte apper og tabellen du kan da få tilgang til.
  
  ![image](https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/b7349591-131d-4848-a59c-6b417c36b005)
  ![image](https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/46ef5f47-f5ac-4e8a-9fe4-e81e0538a3f8)


<hr />
</details>
<details open>
  <summary>
    <h2>Testing</h2>
  </summary>
  
  For testing brukte jeg denne test prosedyren [Testrapport](https://github.com/DennisMag/Pr-ve-Fagpr-ve/blob/main/Test_Rapport.md).

<hr />
</details>
<details open>
  <summary>
    <h2>Grensesnittbeskrivelse</h2>
  </summary>

- For beskrivelse hvordan applikasjonen brukes se:
  [Brukerveiledning](https://github.com/DennisMag/Pr-ve-Fagpr-ve/blob/main/Brukerveiledning.md)

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
            <br>"Edit List" åpner en "Bottom Sheet" som inneholder noen inputs med en save og cancel button (se bilde 1). 
            Knappene er omega komponenter som trenger bare å ta inn propen :dataObject og "Bottom Sheet" er også en omega komponent (se bilde 2).
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/c5c3b555-5d10-4c74-88b1-fcfd13623b05" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/e4f175fb-5939-4ca9-8a81-9ed6dd1d9d71" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ed56ecf1-dbbc-484f-9c47-60b111066493" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ec826914-8044-47e9-9028-7d66be58b1f4" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>Share List</td>
          <td>
          <p>
            "Share List" åpner en "Bottom sheet" (bilde 1) som inneholder data fra dsSharedToPersons. Det blir lagt i en v-for som som lager en person for hver rad i datasourcen. 
            For å slette Personen kjører jeg bare en row.Delete() (Bilde 2).<br>
            For å legge til person bruker jeg en persons lookup ned #target template. denne gjør at jeg kan bruke en knapp med ref på scope som da vil kunne kjøre lookupen sin .open<br>
            Blir da kjørt "addPerson" etter å ha valt en person som kjører .CreateNew() og legger til sel.ID som er verdien jeg hentet ut fra :bind for å da lage ny rad i dsSharedToPersons. (se bilde 3)
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/c5c3b555-5d10-4c74-88b1-fcfd13623b05" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/3ac34732-9d08-46bc-98a0-4a327e844154" width="60" />
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/b2957546-ea23-4c5d-8b97-86b27268f1fd" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/39d3aa98-7931-4fdb-90fd-99b3c25b10a5" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>Delete List</td>
          <td>
          <p>
            "Delete List" kjører bare funkjsonen deleteList() som bruker omega sin confirm control. Kjører dsLists.current.delete() for å slette lista og da gir de en alert toast og loader datasources.
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ee89cc1a-cc9c-4ea0-91e5-7367bd40c4cc" width="60" />
              </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/683cd144-8f7e-426f-a4d3-11baaea2d8a8" width="60" />
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
          <td>Redigering av list</td>
          <td>
          <p>
            Knappene på toppen til høyre. Fungerer helt likt som "Share List" og "Edit List" på hoved siden.
          </p>
          </td>
          <td>
            <table>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/cf1f59de-73c2-4b76-9ab9-5cf51af5b00c" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>New Items</td>
          <td>
          <p>
            Åpner modal. Inneholder 2 tabs. En med lookup til Items og en med fritekst. Har en v-if på Select Item for å hjemme den hvis IsPersonalList = 1 (bilde 1)
            Begge tabsa har en "Add" knapp som kjører en .CreateNew() funksjon. 
            Eneste forskjelle er at "Personal Item" tar inn parameter "PeronalItem" og "PersonalUnit", mens "Select Item" tar bare inn Item_ID(se bilde 2)
            "Items to be added" er bare en v-for med dsTempItems datasourcen. Kjører dsTempItems.deleteItem(row) hvor "row" er dsTempItems.data med x index.
            "Add" knappen helt nede til høyre kjører en SQL procedure med parameter "List_ID" (bilde 4)
            Proceduren kjører en Insert inni listsItems og filtrerer ut items som allerede eksisterer. Kjører en Delete på slutten for å rydde ut temp tabellen. (bilde 5)
          </p>
          </td>
          <td>
            <table>
                <th>
                  <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/4f8c5fa6-577e-448a-b77a-ec110ac1d583" width="60px">
                </th>
                <th>
                  <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/32753340-d378-4477-a447-44906476da25" width="60px">
                </th>
                  <th>
                  <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/9544b67f-5211-49c0-887d-88ebda50a3db" width="60px">
                </th>
                <th>
                  <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/58a8b7ce-bf21-4281-9b81-b34ba3abb07b" width="60px">
                </th>
                <th>
                  <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/e1c3e0e6-84e5-40af-a796-c0ebf35d9a16" width="60px">
                </th>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/f252706a-ed83-4837-91ae-2b6b70668e08" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>Redigering av Items</td>
          <td>
          <p>
            3 dottene til høyre for en item. Åpner en "Bottom sheet" som har input felter med en v-if på IsPersonalItem. for å bytte mellom lookup og fritekst.
          </p>
          </td>
          <td>
            <table>
            </table>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/cf1f59de-73c2-4b76-9ab9-5cf51af5b00c" width="60" />
              </th>
            </table>
          </td>
        </tr>
        <tr>
          <td>Search Input</td>
          <td>
          <p>
            Komponent fra omega. Trenger bare å lage en funksjon som kjører en dsDatasource.recordSource.filterString hvor "ItemName" inneholder pSearchString (bilde 2) som jeg hentet ut fra @onSearch (bilde 1)
          </p>
          </td>
          <td>
            <table>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/70ec80bb-4d30-4511-89c0-21b82870fe4e" width="60">
              </th>
              <th>
                <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/0d87e62d-8f56-4ea7-8624-fa7bb3506a7b" width="60">
              </th>
            </table>
          </td>
          <td>
            <table>
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
      En veldig stor hindring var at jeg måtte publisere appen hver gang jeg ville se endringer. Dette strekket seg helt ut til tirdagen da jeg fant ut at jeg hadde brukt feil URL.
      Noe som også stoppet meg var at Appframe ikke ville ta inn endringene jeg gjorde på et view. Endte opp med å måtte kjøre "Restart application" på cache siden.
      Denne triggeren stoppet meg når jeg skulle slette en liste. var en feil i tabellen. hadde cascade på.
      <img src="https://github.com/DennisMag/Pr-ve-Fagpr-ve/assets/108458368/ec77d4f5-cd64-446f-a4aa-2d1d7f808440">
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
        Tabell strukturen ble forandret ganske mye på. Ble aldri helt sikker på meg selv.
        Shared Lists ble introdusert som en scope change på fredagen. Den fikk meg til å endre litt på data modellen.<br>
        Fikk litt store ideer for Add Items funksjonen. skulle originalt bare ha en lookup med items, men endte opp med å ha Personal Items og en temp tabell for å previewe hvilke items jeg skulle legge til.
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
      <a href="https://vuejs.org/guide/introduction.html" title="Vue Docs">Vue Docs</a>
    </li>
    <li>
      <a href="https://getbootstrap.com/docs/5.0/getting-started/introduction/">Bootstrap Docs</a>
    </li>
    <li>
      <a href="https://docs.omega365.com/nt/docs?Area-ID=10004">Omega GPT</a>
    </li>
    <li>
      Code Snippets (Omega 365)
    </li>
  </ol>
 
<hr />
</details>


<!-- Legg til URL for tabellstruktur her -->
[tablestructure-url]: https://drawsql.app/teams/asdfasfd/diagrams/handleliste
