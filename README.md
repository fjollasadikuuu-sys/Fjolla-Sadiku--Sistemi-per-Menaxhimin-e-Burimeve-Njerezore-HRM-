# Fjolla-Sadiku--Sistemi-per-Menaxhimin-e-Burimeve-Njerezore-HRM-
Raporti Teknik 1 – Analiza, Kërkesavt dhe Dizajni Teknik
Përshkrimi i problemit

Në shumë organizata, të dhënat e punonjësve, kontratat, pushimet, vijueshmëria dhe vlerësimet profesionale menaxhohen përmes dokumenteve fizike ose skedarëve të ndarë. Kjo mënyrë pune mund të shkaktojë përsëritje të të dhënave, vonesa në përpunim, vështirësi në kërkim dhe rrezik për humbje ose qasje të paautorizuar në informacione konfidenciale. Projekti propozon një sistem të centralizuar HRM që i organizon këto procese në një platformë të vetme, me qasje sipas rolit dhe gjurmim të veprimeve.

Qëllimi projektit

Qëllimi është projektimi i një sistemi të sigurt dhe të lehtë për përdorim, i cili e përmirëson administrimin e burimeve njerëzore, e zvogëlon punën manuale dhe ofron të dhëna të sakta për vendimmarrje. Sistemi synon të përshpejtojë regjistrimin dhe përditësimin e punonjësve, të standardizojë kërkesat për pushim dhe të krijojë raporte të qarta për menaxhmentin.

Përdoruesit e sistemit

-Administratori i sistemit: Menaxhon llogaritë, rolet, lejet dhe parametrat e sistemit.
-	Zyrtari i HR-së: Regjistron punonjësit, kontratat, pushimet dhe të dhënat e personelit.
-Menaxheri / Udhëheqësi: Shqyrton kërkesat, miraton ose refuzon pushimet dhe sheh raporte të ekipit.
-Punonjësi: Shikon profilin e vet dhe paraqet kërkesa për pushim ose përditësim të të dhënave. 
 Funksionet kryesore
-	Menaxhimi i profilit të punonjësit: të dhëna personale dhe profesionale, pozita, departamenti dhe statusi i punësimit.
-Menaxhimi i dokumenteve dhe kontratave: regjistrim, datat e vlefshmërisë dhe qasje e kontrolluar.
-Menaxhimi i pushimeve: paraqitje, shqyrtim, miratim/refuzim dhe evidencë e ditëve të mbetura.
-Evidenca e vijueshmërisë dhe orarit, nëse organizata e aktivizon këtë modul.
-Raporte dhe kërkim: lista sipas departamentit, statusit, pozitës dhe kërkesave të pushimit.
-Njoftime dhe histori veprimesh për të ndjekur ndryshimet dhe vendimet.

Kërkesat e sistemit

Kërkesat funksionale 
Sistemi duhet të lejojë hyrjen me llogari personale dhe të zbatojë leje sipas rolit.
HR-ja duhet të mund të shtojë, shikojë, ndryshojë dhe arkivojë të dhënat e punonjësve.
Punonjësi duhet të mund të paraqesë kërkesë për pushim dhe të shohë statusin e saj.
Menaxheri duhet të mund të miratojë ose refuzojë kërkesat dhe të regjistrojë arsyetimin.
Sistemi duhet të gjenerojë raporte bazë dhe të ruajë historikun e ndryshimeve kryesore.

Kërkesat jofunksionale 
Siguria: fjalëkalime të ruajtura në formë të sigurt, autorizim sipas rolit dhe mbrojtje e të dhënave personale.
Besueshmëria: validim i formularëve, parandalim i të dhënave të dyfishta dhe kopje rezervë periodike.
Përdorshmëria: ndërfaqe e qartë, gjuhë e kuptueshme dhe funksionim në shfletues modernë.
Performanca dhe mirëmbajtja: kërkim e ruajtje efikase, kod i organizuar dhe mundësi zgjerimi të moduleve.


Teknologjitë e planifikuara	

- Ndërfaqja - Teknologjia e propozuar: HTML, CSS, JavaScript. Përdorimi: Faqet, formularët dhe validimi fillestar.
-Logjika e aplikacionit - Teknologjia e propozuar: PHP. Përdorimi: Përpunimi i kërkesave, rregullat dhe komunikimi me databazën.
-Databaza - Teknologjia e propozuar: MySQL. Përdorimi: Ruajtja e të dhënave të strukturuara.
- Mjedisi i zhvillimit - Teknologjia e propozuar: Visual Studio Code, XAMPP. Përdorimi: Shkrimi dhe testimi lokal i aplikacionit.
-Kontrolli dhe dorëzimi - Teknologjia e propozuar: Git (opsional), dokumentim. Përdorimi: Gjurmimi i ndryshimeve dhe përgatitja e projektit.


Arkitektura e sistemit 
Propozohet arkitekturë me tri shtresa. Përdoruesi ndërvepron me ndërfaqen në shfletues; serveri i aplikacionit kontrollon hyrjet, autorizimin dhe rregullat e biznesit; databaza ruan të dhënat. Ndarja e shtresave e bën sistemin më të lehtë për testim, mirëmbajtje dhe zgjerim.
- SHTRESA E PREZANTIMIT - HTML • CSS • JavaScript; Përdoruesi / shfletuesi
- SHTRESA E APLIKACIONIT - PHP • autentikim • rregulla; Serveri i aplikacionit
-SHTRESA E TË DHËNAVE -  MySQL • tabela • relacione; Databaza


 Modeli fillestar i databazës

Modeli fillestar përdor identifikues unikë (ID) dhe lidhje përmes çelësave të huaj (FK). Ky model mund të zgjerohet gjatë implementimit sipas rregullave të organizatës.
- Departamenti - Fushat kryesore: departamenti_id (PK), emri. Lidhjet: Një departament ka shumë punonjës.
- Punonjesi - Fushat kryesore: punonjesi_id (PK), emri, mbiemri, email, telefoni, pozita, data_punesimit, departamenti_id (FK). Lidhjet: Lidhet me Departamentin dhe Kontratën.
  -Kontrata - Fushat kryesore: kontrata_id (PK), punonjesi_id (FK), lloji, data_fillimit, data_mbarimit, statusi. Lidhjet: Çdo kontratë i përket një punonjësi.
  -Perdoruesi - Fushat kryesore: perdoruesi_id (PK), punonjesi_id (FK), email_hyrje, fjalekalimi_hash, roli. Lidhjet: Llogaria lidhet me punonjësin; roli përcakton lejet.
- Pushimi - Fushat kryesore: pushimi_id (PK), punonjesi_id (FK), data_fillimit, data_mbarimit, arsyeja, statusi, miratuesi_id (FK). Lidhjet: Punonjësi paraqet kërkesa; menaxheri i shqyrton.


 Plani i punës 

-Analiza - Aktivitetet: Përcaktimi i problemit, përdoruesve dhe kërkesave.. Kohëzgjatja: 1 javë
- Projektimi - Aktivitetet: Arkitektura, diagramet dhe modeli i databazës.. Kohëzgjatja: 1 javë
-Zhvillimi - Aktivitetet: Ndërtimi i ndërfaqes, logjikës dhe funksioneve bazë.. Kohëzgjatja: 2 javë
- Testimi - Aktivitetet: Testimi i hyrjes, roleve, formularëve dhe pushimeve.. Kohëzgjatja: 1 javë
  - Dokumentimi - Aktivitetet: Përmirësimet, udhëzuesi dhe përgatitja e prezantimit.. Kohëzgjatja: 1 javë


Përfundimi 
Sistemi HRM i propozuar synon të centralizojë dhe standardizojë proceset kryesore të burimeve njerëzore. Përmes roleve të përcaktuara, databazës së strukturuar dhe raporteve bazë, organizata mund të zvogëlojë punën manuale, të përmirësojë saktësinë e të dhënave dhe të rrisë transparencën e procedurave. Hapi i ardhshëmështë realizimi i një prototipi, testimi me të dhëna shembull dhe vlerësimi i tij sipas kërkesave të përcaktuara.

           është realizimi i një prototipi, testimi me të dhëna shembull dhe vlerësimi i tij sipas kërkesave të përcaktuara.

