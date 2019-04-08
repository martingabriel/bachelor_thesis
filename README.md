# A Proposed Multiplatform Mobile Application fo Fast Communication Between Students and Teachers

## What you find here

This is collection of files used to write my bachelor thesis on Tomas Bata University in Zlin. Thesis is written in czech language.

## Project architecture

Solution is based on Microsoft technologies like .NET Core, Azure, Xamarin, and many others.

Core features:

1. **.NET Core server app**
   - User autentification
   - Get data from STAG UTB server
   - API for Xamarin app
   - Send push-notifications

2. **Xamarin multiplatform App**
   - View data from .NET Core server API
   - Send messages to multiple users (server API)
   - Receive messages as push-notifications

## STAG API services

1. **getRozvrhovaAkceInfo** 

2. **getRozvrhoveAkce**

3. **getUciteleRoakce**

4. **getRozvrhByStudent**

5. **getRozvrhByUcitel**



Postup na rozeslání rychlé zprávy:

1. Přihlášení studenta a stažení jeho rozvrhu, vygenerování tokenu pro push notifikace a uložení do jeho instance
2. Přihlášení učitele a stažení jeho rozvrhu
3. Po kliku učitele na rozvrhovou akci se zobrazí seznam studentů, kteří mají tuto rozvrhovou akci - možnost označit, komu bude zpráva odeslána a komu ne, defaultně bude odeslána všem
4. Možnost výběru rychlých zpráva pro učitele
5. Pro odeslání rychlé zprávy se zavolá API služba s textem zprávy a seznamem ID studentům, kterým se má prush notifikace se zprávou doručit
6. Server přijme požadavek na odeslání zprávy, ze seznamu studentů najde tokeny pro push notifikaci a rozešle zprávu



Postup na rozeslání hodnocení vyuky

1. Přihlášení studenta a stažení jeho rozvrhu, vygenerování tokenu pro push notifikace a uložení do jeho instance
2. Přihlášení učitele a stažení jeho rozvrhu
3. Po kliku učitele na rozvrhovou akci se zobrazí seznam studentů, kteří mají tuto rozvrhovou akci - možnost označit, komu bude zpráva odeslána a komu ne, defaultně bude odeslána všem
4. Učitel vybere možnost rozeslat požadavek na hodnocení výuky a vybere heslo pro hodnocení (např smajlík)
5. Pro odeslání požadavku na hodnocení vyuky se zavolá API služba se seznamem ID studentů, kterým se má push notifikace s požadavkem doručit, vygeneruje se ID hodnocení skládající se z ID rozvrhové akce a DATA/ČASU konkrétní hodiny a vytvoří instanci hodnocení s tímto ID, které se odešle v push notifikaci
6. Server přijme požadavek na odeslání zprávy, ze seznamu studentů najde tokeny pro push notifikaci a rozešle zprávu
7. Uživatel rozklikne notifikaci a dostane se na formulář s možností hodnocení a požadavkem na zadání hesla
8. Po kliknutí na odeslat se zavolá API služba obsahující ID hodnocení, vybrané hodnocení a heslo (pokud se heslo neshoduje, tak vrátní chybu)
9. Server přijme požadavek na uložení hodnocení a uloží ho do instance hodnocení rozvrhové akce
10. Učitel po kliknutí na rozvrhovou akci může zobrazi a refreshovat odeslaní hodnocení



Co je potřeba vytvořit v API:

- [ ] Pas