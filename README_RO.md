# CapeMaker — prototip Fabric 1.21.11

Acesta este un **proiect-sursa de prototip**, nu un `.jar` deja compilat sau testat pe MojoLauncher.

## Ce include acum
- mod client Fabric pentru Minecraft 1.21.11;
- meniu deschis cu tasta `K` (poate fi schimbata din Options > Controls);
- verificare pentru PNG local la `config/capemaker/cape.png`;
- workflow GitHub Actions pentru a compila proiectul online fara PC.

## Limitari importante
Aceasta prima versiune **NU afiseaza inca textura pe spatele personajului** si **NU sincronizeaza capele cu alti jucatori**. Meniul verifica doar daca PNG-ul exista si are dimensiunea recomandata 64x32. Urmatoarea etapa de dezvoltare este renderer-ul de capa, apoi serviciul online de sincronizare. Pe servere publice, fiecare jucator care vrea sa vada cape custom va trebui sa aiba clientul compatibil, iar regulile serverului trebuie respectate.

## Compilare doar de pe telefon
1. Descarca arhiva ZIP si extrage continutul.
2. Creeaza un repository GitHub nou din browserul telefonului.
3. Incarca toate fisierele si folderele proiectului (inclusiv `.github/workflows/build.yml`).
4. Deschide fila **Actions**, alege **Build CapeMaker** si apasa **Run workflow** (sau asteapta sa porneasca dupa upload).
5. Cand rularea este verde, deschide rularea si descarca artifact-ul `capemaker-jar`.
6. Extrage artifact-ul ZIP; copiaza `capemaker-0.1.0.jar` din el in folderul `mods` al instantei MojoLauncher.

## PNG pe Android
Creeaza `config/capemaker/` in folderul jocului si copiaza imaginea in acel folder cu numele exact `cape.png`. Format recomandat pentru textura classica: 64x32 PNG. Apoi porneste jocul si apasa K.

## Dependinte
Minecraft 1.21.11, Java 21, Fabric Loader, Fabric API. Fabric Loom/Yarn sunt definite in gradle.properties; daca Gradle nu gaseste o versiune de mappings, actualizeaza `yarn_mappings` la o versiune publicata pentru 1.21.11.

## Securitate
Nu incarca in repository parole, token-uri, sesiuni sau date personale. Nu este nevoie sa dai nimanui parola contului tau.
