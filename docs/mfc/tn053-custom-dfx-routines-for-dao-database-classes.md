---
title: "TN053: Benutzereigene DFX-Routinen f&#252;r DAO-Datenbankklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dfx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte DFX-Routinen [C++]"
  - "DAO [C++], Klassen"
  - "DAO [C++], MFC"
  - "Datenbankklassen [C++], DAO"
  - "DFX (DAO-Datensatzfeldaustausch) [C++]"
  - "DFX (DAO-Datensatzfeldaustausch) [C++], Benutzerdefinierte Routinen"
  - "MFC [C++], DAO und"
  - "TN053"
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# TN053: Benutzereigene DFX-Routinen f&#252;r DAO-Datenbankklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie [OLE DB\-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
 Dieser technische Hinweis beschreibt den Mechanismus des DAO\-Datensatzfeldaustauschs \(DFX\).  Zum Schutz zu verstehen was in den DFX\-Routinen geschieht, wird die Funktion `DFX_Text` als detailliert Beispiel erläutert.  Als weitere Informationsquelle zu diesem technischen Hinweis, können Sie Code für den anderen überprüfen die einzelnen DFX\-Funktionen.  Sie benötigen wahrscheinlich keine Routine angepasster DFX so häufig, wie Sie eine benutzerdefinierte Routine der RFX benötigen \(mit ODBC\-Datenbankklassen\).  
  
 Dieser enthält technische Hinweis:  
  
-   Übersicht über DFX  
  
-   [Beispiele](#_mfcnotes_tn053_examples) mithilfe des DAO\-Datensatzfeldaustauschs und der dynamischer Bindung  
  
-   [Wie DFX funktioniert](#_mfcnotes_tn053_how_dfx_works)  
  
-   [Was die Routine der Gewohnheits\-DFX ausführt](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
-   [Details der DFX\_Text](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **Übersicht über DFX**  
  
 Der DAO\-Datensatzfeldaustausch\-Mechanismus \(DFX\) wird verwendet, um die Prozedur zum Abrufen und Aktualisieren von Daten zu vereinfachen, wenn die `CDaoRecordset`\-Klasse verwendet.  Der Prozess wird mithilfe der Datenmember der `CDaoRecordset`\-Klasse vereinfacht.  Wenn Sie von `CDaoRecordset` ableiten, können Sie Datenmember der abgeleiteten Klasse hinzufügen, die jedes Feld in einer Tabelle oder einer Abfrage darstellt.  Dieser Mechanismus "statischen" Bindung ist einfach, aber es ist möglicherweise nicht die Datenempfangs\-\/\-Updatemethode der Auswahl für alle Anwendungen.  DFX wird jedes gebundene Feld ab, wenn der aktuelle Datensatz geändert wird.  Wenn Sie eine LeistungSENSITIVE\-Anwendung entwickeln, die nicht das Abrufen jedes Felds erforderlich, wenn Währung geändert wird, "Dynamische Bindung" über `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue` können die Datenzugriffsmethode der Auswahl.  
  
> [!NOTE]
>  DFX und dynamische Bindung sind nicht gegenseitig aus, sodass keine hybride Verwendung statischer und dynamischer Bindung verwendet werden.  
  
 **Beispiel 1 \- Verwendung von nur DAO\-Datensatzfeldaustausch**  
  
 \(von `CDaoRecordset` abgeleitete Klasse bereits geöffneten `CMySet` \) an  
  
```  
// Add a new record to the customers table  
myset.AddNew();  
myset.m_strCustID = _T("MSFT");  
myset.m_strCustName = _T("Microsoft");  
myset.Update();  
```  
  
 **Beispiel 2 \- Verwendung nur der dynamischer Bindung**  
  
 \(nimmt mit `CDaoRecordset`\-Klasse, `rs`, und diese ist bereits geöffnet\)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 ( _T("MSFT"), VT_BSTRT );  
//Note: VT_BSTRT flags string type as ANSI, instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"), VT_BSTRT );  
rs.AddNew();  
rs.SetFieldValue(_T("Customer_ID"), varFieldValue1);  
rs.SetFieldValue(_T("Customer_Name"), varFieldValue2);  
rs.Update();  
```  
  
 **Beispiel 3 \- Verwendung des DAO\-Datensatzfeldaustauschs und der dynamischer Bindung**  
  
 \(Durchsuchenmitarbeiterdaten nimmt mit `CDaoRecordset` abgeleitete Klasse `emp`\) an  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();  
  
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
   emp.GetFieldValue(_T("photo"), varPhoto);  
  
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName, varPhoto);  
```  
  
 **Wie DFX funktioniert**  
  
 Der DFX\-Mechanismus funktioniert auf ähnliche Weise für das den Datensatzfeldaustausch \(RFX\), der über die MFC\-ODBC\-Klassen verwendet wird.  Die Managementprinzipien von RFX und DFX sind identisch, es gibt jedoch zahlreiche interne Unterschiede.  Der Entwurf der DFX\-Funktionen war so, dass virtueller der gesamte Code mit Routinen Siteebene DFX freigegeben wird.  Auf der höchsten Funktionalitätsebene DFX hat nur einige Punkte aufgeführt.  
  
-   DFX erstellt die SQL\- **AUSWÄHLEN** und SQL\- **PARAMETER**.  
  
-   DFX erstellt die verbindliche Struktur, die durch `GetRows`\-Funktion DAO verwendet wird \(weitere auf diesem höher\).  
  
-   DFX verwaltet den Datenpuffer, der verwendet wird, um geänderte Felder zu erkennen \(wenn doppelte Pufferung verwendet wird\)  
  
-   DFX verwaltet die **NULL** und **GEÄNDERT** Statusarrays und die Satzwerte ggf. auf Updates.  
  
 Im eine des DFX\-Mechanismus ist die der Funktion `CDaoRecordset``DoFieldExchange` abgeleiteten Klasse.  Diese Funktion bietet Aufrufe an einzelnen DFX\-Funktionen eines entsprechenden Vorgangstyps aus.  Bevor Sie `DoFieldExchange` die internen MFC\-Funktionen haben, legen Sie den Vorgangstyp fest.  Die folgende Liste enthält die verschiedenen Vorgangstypen und eine kurze Beschreibung ein.  
  
|Vorgang|**Beschreibung**|  
|-------------|----------------------|  
|**AddToParameterList**|Builds PARAMETERklausel|  
|**AddToSelectList**|Builds SELECT Klausel aus|  
|**BindField**|Setups, Struktur binden|  
|**BindParam**|Legt Parameterwerte fest|  
|**Fixups**|Sätze wird Status ungültig|  
|**AllocCache**|Ordnet Cache für geänderte Überprüfung zu|  
|**StoreField**|Speichert aktuellen Datensatz am Cache|  
|**LoadField**|Wiederherstellung speichert den Memberwerten zwischen|  
|**FreeCache**|Gibt Caches frei|  
|`SetFieldNull`|Satzfeld\-Statuswert zum & in NULL|  
|**MarkForAddNew**|Markierungen Felder geändert wenn nicht PSEUDOnull|  
|**MarkForEdit**|Markierungen fängt geändertes auf, wenn nicht übereinstimmen Cache Sie|  
|**SetDirtyField**|Legt die Feldwerte fest, die markiert werden, z geändert|  
  
 Im nächsten Abschnitt wird jeder Vorgang ausführlicher für den `DFX_Text` erklärt.  
  
 Die wichtigste Funktion, die über den DAO\-Datensatzfeldaustausch\-Prozess zu kennen ist, dass der `GetRows`\-Funktion des `CDaoRecordset`\-Objekts verwendet.  Die Funktion DAO `GetRows` kann auf verschiedene Weise funktionieren.  Dieser technische Hinweis nur kurz `GetRows` beschreibt, der außerhalb des Umfangs diesem technischen Hinweises ist.  
  
 DAO `GetRows` kann auf verschiedene Weise funktionieren.  
  
-   Es kann mehrere Datensätze und mehrere Datenfelder gleichzeitig abgerufen.  Dadurch können für einen schnelleren Datenzugriff mit der Komplikation des Beschäftigens eine große Datenstruktur und der entsprechenden Offsets zu jedem Feld und jeden Datensatz von Daten in der Struktur zu.  MFC verfügt nicht diesen abrufenden mehreren RekordMechanismus.  
  
-   Eine andere Methode, die `GetRows` bearbeiten kann, ist, Programmierern zu ermöglichen, Bindungsadressen für die abgerufenen Daten jedes Felds einen Datensatz von Daten angeben.  
  
-   DAO ruft auch "wiedergegeben" in den Aufrufer für Spalte variable Länge auf, um dem Aufrufer zuzulassen, um Speicher zu belegen.  Diese zweite Funktion hat den Vorteil Minimierens der Anzahl der Kopien von Daten sowie das Erlaubens der direkten Datenspeicherung in Member einer Klasse \(die `CDaoRecordset` abgeleitete Klasse\).  Dieser zweite Mechanismus kann die Verwendung der Methode MFC, an Datenmember in `CDaoRecordset` abgeleiteten Klassen zu binden.  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Was die Routine der Gewohnheits\-DFX ausführt  
 Es ist dieser Diskussion deutlich, dass der wichtigste Vorgang, der in einer beliebigen DFX\-Funktion implementiert wird, die Fähigkeit sein, die erforderlichen Datenstrukturen zu installieren, um `GetRows` erfolgreich aufrufen.  Es gibt mehrere andere Vorgänge, die eine DFX\-Funktion auch unterstützen muss, aber keine als wichtiges oder sehr komplex, wie ordnungsgemäß, Vorbereiten für den Aufruf `GetRows`.  
  
 Die mit DFX wird in der Onlinedokumentation beschrieben.  Im Wesentlichen werden zwei Anforderungen.  Zuerst müssen Member der `CDaoRecordset` abgeleiteten Klasse für jedes gebundene Feld und Parameter hinzugefügt werden.  Nach diesem `CDaoRecordset::DoFieldExchange` sollte überschrieben werden.  Beachten Sie, dass der Datentyp des Members wichtig ist.  Außerdem sollte die Daten des Felds in der Datenbank übereinstimmen oder mindestens in diesen Typ konvertierbar sein.  Beispielsweise kann ein numerisches Feld in der Datenbank, z eine lange ganze Zahl, immer konvertiert werden, die einem `CString`\-Member auf Text und springen, ein Textfeld in einer Datenbank nicht unbedingt wird an eine numerische Darstellung, z langer ganzzahligen und Grenze zu einem langen Ganzzahlmembern konvertiert werden.  DAO und das Microsoft Jet\-Datenbankmodul sind für die Konvertierung verantwortlich \(anstatt MFC\).  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> Details der DFX\_Text  
 Wie bereits erwähnt, die beste Möglichkeit, zu erläutern, wie DFX\-Arbeiten, durch ein Beispiel umgehen.  Für diesen Zweck sollte das Durchlaufen die internen Daten von `DFX_Text` zusammenwirken recht wohl, um zu helfen, Grundkenntnisse über mindestens DFX bereitzustellen.  
  
 **AddToParameterList**  
 Dieser Vorgang erstellt die SQL\- **PARAMETER** \("`Parameters <param name>, <param type> ... ;`"\) erforderlich von Jet enthalten.  Jeder Parameter wird mit und die Eingabe \(z im RFX\-Aufruf angegeben wurde\).  Siehe die **CDaoFieldExchange::AppendParamType**\-Funktion, um die Namen der einzelnen Typen zu finden.  Für `DFX_Text` ist der verwendete Typ `text`.  
  
 **AddToSelectList**  
 Erstellt die SQL\- **AUSWÄHLEN**.  Dies ist recht einfach, da der Spaltenname, der durch den DFX\-Aufruf angegeben, einfach GetLanguage \("`SELECT <column name>, ...`"\).  
  
 **BindField**  
 Der gängigste Komplexität der Vorgänge.  Wie zuvor erwähnt diesem ist, wo die DAO\-Bindungsstruktur, die von `GetRows` verwendete, installiert ist.  Wie Sie dem Code in `DFX_Text` die Typen von Informationen im Struktur finden können, wurde der DAO\-Typ \(**DAO\_CHAR** oder **DAO\_WCHAR** im Fall von `DFX_Text`\).  Außerdem wird der Typ von Bindung verwendet ebenfalls installiert.  In einem vorherigen Abschnitt wurde `GetRows` nur kurz beschrieben, aber es wurde genügend, erläutern, dass der Typ von Bindung durch MFC verwendet stets Bindung der direkten Adresse \(**DAOBINDING\_DIRECT**\) ist.  Außerdem können Sie für Rückrufbindung der Bindung der Spalte mit variabler Länge \(wie `DFX_Text`\) wird verwendet, damit die Speicherbelegung MFC steuern und der richtigen Adresse einer Länge angeben kann.  Was bedeutet, diese kann dieses MFC DAO immer mitteilen "wo" die Daten platziert und so das Binden direkt auf Membervariablen können.  Der Rest der verbindlichen Struktur wird mit Aufgaben wie der Adresse der Speicherbelegungsrückruffunktion und des Spaltenbindung gefüllt \(Bindung von Spaltennamen.\)  
  
 **BindParam**  
 Dies ist ein einfacher Vorgang, der `SetParamValue` mit dem Parameterwert aufruft, der im Parametermember angegeben wird.  
  
 **Fixup**  
 Füllt den **NULL** Status für jedes Feld aus.  
  
 `SetFieldNull`  
 Diese Operation markiert nur jeden Feldstatus als **NULL** und legt den Wert der Membervariable auf **PSEUDO\_NULL** fest.  
  
 **SetDirtyField**  
 Ruft `SetFieldValue` für jedes Feld markierte geänderte auf.  
  
 Alle übrigen Vorgänge verarbeiten nur dem Datencache.  Im Datencache wird ein zusätzlicher Puffer der Daten im aktuellen Datensatz, der verwendet wird, um bestimmte Aktionen zu vereinfachen.  Durch "geänderte" Felder können automatisch erkannt werden.  Wie in der Onlinedokumentation beschrieben kann er im Feld vollständig oder deaktiviert werden.  Die Implementierung des Puffers wird eine Zuordnung.  Diese Zuordnung wird verwendet, um die dynamisch zugeordnete Kopien der Daten mit der Adresse des "gebundenen Felds" \(oder eines abgeleiteten Datenmembers `CDaoRecordset` \) entspricht.  
  
 **AllocCache**  
 Ordnet dynamisch dem zwischengespeicherten Feldwert zu und der Zuordnung hinzu.  
  
 **FreeCache**  
 Löscht den zwischengespeicherten Feldwert und entfernt sie aus der Zuordnung.  
  
 **StoreField**  
 Kopiert den aktuellen Feldwert in den Datacache.  
  
 **LoadField**  
 Kopiert den zwischengespeicherten Wert im Feldmember.  
  
 **MarkForAddNew**  
 Überprüft, wenn als aktueller Feldwert **NULL** ist und markiert sie geändert.  
  
 **MarkForEdit**  
 Vergleicht aktuellen Feldwert mit Datencache und markiert geändertes.  
  
> [!TIP]
>  Modellieren Sie die Routinen angepasster DFX auf den vorhandenen DFX\-Routinen für Standarddatentypen.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)