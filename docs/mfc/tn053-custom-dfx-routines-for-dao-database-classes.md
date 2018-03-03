---
title: "TN053: Benutzereigene DFX-Routinen für DAO-Klassen-Datenbank | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.dfx
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6935e4b3f2c8159677d1d322f6f875246160da2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: Benutzereigene DFX-Routinen für DAO-Datenbankklassen
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützt nicht DAO (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
 In diesem technischen Hinweis beschreibt die DAO-Datensatzfeldaustausch (DFX)-Mechanismus. Zum besseren Verständnis der DFX-Routinen, woran der `DFX_Text` Funktion wird beispielhaft ausführlich erläutert werden. Als Quelle für Weitere Informationen zu diesen technischen Hinweis können Sie dem Code für die anderen einzelnen DFX-Funktionen untersuchen. Wahrscheinlich benötigen nicht Sie eine benutzerdefinierte DFX-Routine beliebig oft benötigen Sie eine benutzerdefinierte RFX-Routine (mit ODBC-Datenbankklassen verwendet).  
  
 In diesem technischen Hinweis enthält:  
  
-   DFX (Übersicht)  
  
- [Beispiele für](#_mfcnotes_tn053_examples) mithilfe von DAO-Datensatzfeldaustausch und dynamische Bindung  
  
- [Funktionsweise von DFX](#_mfcnotes_tn053_how_dfx_works)  
  
- [Was bewirkt, dass Ihre benutzerdefinierte DFX-Routine](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
- [Details der DFX_Text](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **DFX (Übersicht)**  
  
 In den Austauschmechanismus für DAO-Datensatzfeldaustausch (DFX) wird verwendet, um die Prozedur abrufen und Aktualisieren von Daten bei Verwendung zu vereinfachen die `CDaoRecordset` Klasse. Verwenden von Datenelementen, der der Prozess vereinfacht die `CDaoRecordset` Klasse. Durch Ableiten von `CDaoRecordset`, Sie können Daten Mitglieder hinzufügen, der abgeleiteten Klasse jedes Feld in einer Tabelle oder Abfrage darstellt. Diesem "statischen" Bindungsmechanismus ist einfach, aber möglicherweise nicht die Fetch-Update Datenmethode Wahl für alle Anwendungen. DFX Ruft alle gebundenes Feld jedes Mal, wenn der aktuelle Datensatz geändert wird. Wenn Sie eine leistungsabhängigen-Anwendung, die keine erfordert jedes Feld abrufen entwickeln, wenn die Währung geändert wird, "dynamische Bindung" über `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue` kann die Datenzugriffsmethode Wahl sein.  
  
> [!NOTE]
>  DFX und dynamische Bindung sind nicht gegenseitig aus, damit eine hybride statische und dynamische Bindung verwendet werden können.  
  
## <a name="_mfcnotes_tn053_examples"></a>Beispiel 1: Verwendung von DAO-Datensatzfeldaustausch nur  
  
 (geht davon aus `CDaoRecordset` – abgeleitete Klasse `CMySet` bereits geöffnet)  
  
```  
// Add a new record to the customers table  
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```  
  
 **Beispiel 2 – Für die Verwendung der dynamischen Bindung**  
  
 (ausgegangen, dass `CDaoRecordset` -Klasse, `rs`, und es ist bereits geöffnet)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```  
  
 **Beispiel 3: Verwenden von DAO Record Field Exchange und dynamische Bindung**  
  
 (geht davon aus browsing Mitarbeiterdaten mit `CDaoRecordset`-abgeleitete Klasse `emp`)  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();

 
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
    emp.GetFieldValue(_T("photo"),
    varPhoto);

 
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName,
    varPhoto);
```  
  
## <a name="_mfcnotes_tn053_how_dfx_works"></a>Funktionsweise von DFX  
  
 Der DFX-Mechanismus funktioniert in ähnlicher Weise wie Datensatzfeldaustausch (RFX) Austauschmechanismus von den MFC-ODBC-Klassen verwendet. Die Prinzipien des DFX und RFX sind identisch, aber es gibt zahlreiche interne Unterschiede. Das Design der DFX-Funktionen war, nahezu alle Code von den einzelnen DFX-Routinen gemeinsam verwendet wird. Führt Sie auf der höchsten Ebene DFX nur wenige Aufgaben aus.  
  
-   DFX erstellt der SQL- **wählen** -Klausel als auch SQL **Parameter** -Klausel, wenn erforderlich.  
  
-   DFX erstellt der Bindungsstruktur von DAO verwendeten `GetRows` Funktion (mehr dazu später).  
  
-   DFX verwaltet den Datenpuffer verwendet, um dirty Felder erkennen (falls es sich um eine doppelte Pufferung verwendet wird)  
  
-   DFX verwaltet die **NULL** und **DIRTY** Status arrays und ggf. legt Werte für Updates fest.  
  
 Das Herzstück der DFX-Mechanismus ist die `CDaoRecordset` abgeleitete Klasse des `DoFieldExchange` Funktion. Diese Funktion sendet Aufrufe der einzelnen DFX-Funktionen eines entsprechenden Vorgang-Typs. Vor dem Aufruf `DoFieldExchange` internen MFC-Funktionen legen Sie den Vorgangstyp. Die folgende Liste zeigt die verschiedenen Vorgangstypen und eine kurze Beschreibung.  
  
|Vorgang|Beschreibung|  
|---------------|-----------------|  
|**AddToParameterList**|Parameter-Klausel erstellt|  
|**AddToSelectList**|Builds SELECT-Klausel|  
|**BindField**|Richtet Bindungsstruktur|  
|**BindParam**|Legt Parameterwerte|  
|**Fixup**|Legt die NULL-status|  
|**AllocCache**|Ordnet der Cache für fehlerhafte Überprüfung|  
|**StoreField**|Speichert aktuellen Datensatz cache|  
|**LoadField**|Wiederherstellungen Cache Elementwerten|  
|**FreeCache**|Cache frei|  
|`SetFieldNull`|Legt das Feld Status & Wert auf NULL|  
|**MarkForAddNew**|Kennzeichnet Felder dirty anderenfalls PSEUDO-NULL|  
|**MarkForEdit**|Markierungen Felder dirty If stimmen nicht überein. cache|  
|**SetDirtyField**|Legt Feldwerte als geändert markiert|  
  
 Im nächsten Abschnitt wird jeder Vorgang werden werden ausführlicher für `DFX_Text`.  
  
 Die wichtigste Funktion, über den DAO-Datensatzfeldaustausch Exchange-Prozess zu verstehen ist, verwendet der `GetRows` Funktion der `CDaoRecordset` Objekt. Die DAO `GetRows` Funktion kann auf verschiedene Weise funktionieren. In diesem technischen Hinweis wird nur eine kurze Beschreibung `GetRows` unverändert außerhalb des Bereichs dieser technischen Hinweis.  
  
 DAO `GetRows` können auf verschiedene Weise funktionieren.  
  
-   Es kann mehrere Datensätze und mehrere Datenfelder gleichzeitig abgerufen werden. Dadurch kann für schnelleren Datenzugriff mit Problemen Umgang mit großen Datenstruktur und die geeigneten Offsets für jedes Feld und für jeden Datensatz von Daten in der Struktur. MFC ist nicht dieser mehrere Datensatz abrufen Mechanismus nutzen.  
  
-   Eine weitere Möglichkeit `GetRows` können Arbeit ist, können Programmierer Bindung Adressen für die abgerufenen Daten der einzelnen Felder für einen Datensatz der Daten angeben.  
  
-   DAO wird auch "in der Aufrufer für Spalten variabler Länge Rückruf" damit den Aufrufer belegt werden kann. Diese zweite Funktion hat den Vorteil der Minimierung der Anzahl von Kopien der Daten als auch ermöglicht direkte Speicherung von Daten in die Member einer Klasse (die `CDaoRecordset` abgeleitete Klasse). Diese zweite Mechanismus besteht die Methode MFC verwendet-Datenmember in binden `CDaoRecordset` abgeleitete Klassen.  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>Was bewirkt, dass Ihre benutzerdefinierte DFX-Routine  
 Ist es offensichtlich, aus dieser Diskussion, die der wichtigste Vorgang, der in jeder DFX-Funktion implementiert die Möglichkeit, die gegebenenfalls Datenstrukturen einzurichten, erfolgreich aufgerufen werden muss, `GetRows`. Es gibt diverse andere Vorgänge, die eine DFX-Funktion sowie unterstützen muss, jedoch keine als wichtige oder komplex wie ordnungsgemäß Vorbereiten für die `GetRows` aufrufen.  
  
 Die Verwendung von DFX wird in der Onlinedokumentation beschrieben. Es gibt im Wesentlichen zwei Anforderungen. Zunächst müssen Elemente hinzugefügt werden, um die `CDaoRecordset` abgeleiteten Klasse jedes gebundenen Feld und die Parameter. Befolgen Sie diese `CDaoRecordset::DoFieldExchange` sollte außer Kraft gesetzt werden. Beachten Sie, dass der Datentyp des Elements wichtig ist. Sie sollten die Daten aus dem Feld in der Datenbank übereinstimmen oder mindestens auf diesen Typ konvertiert werden. Z. B. ein numerisches Feld in der Datenbank, z. B. eine lange ganze Zahl kann immer in Text umgewandelt und an gebunden eine `CString` Member, aber ein Textfeld in einer Datenbank kann nicht unbedingt in eine numerische Darstellung, wie z. B. long integer-Wert konvertiert und an eine lange Integ gebunden er Mitglied. DAO und das Microsoft Jet-Datenbankmodul sind verantwortlich für die Konvertierung (anstelle von MFC-).  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a>Details der DFX_Text  
 Wie bereits erwähnt, ist die beste Möglichkeit zur Erläuterung der Funktionsweise von DFX über ein Beispiel zu arbeiten. Zu diesem Zweck im Rahmen der durchlaufen `DFX_Text` sollte sehr gut funktionieren, so mindestens ein grundlegendes Verständnis der DFX bereitzustellen.  
  
 **AddToParameterList**  
 Dieser Vorgang erstellt die SQL **Parameter** -Klausel ("`Parameters <param name>, <param type> ... ;`") von Jet erforderlich. Jeder Parameter ist mit dem Namen und eingegeben haben (gemäß der RFX-Aufruf). Finden Sie im Funktion **CDaoFieldExchange::AppendParamType** Funktion, um die Namen der einzelnen Typen finden Sie unter. Im Fall von `DFX_Text`, ist der verwendete Typ `text`.  
  
 **AddToSelectList**  
 Erstellt die SQL **wählen** Klausel. Dies ist ziemlich unkompliziert entspricht der durch den Aufruf DFX angegebene Spaltennamen einfach angefügt ("`SELECT <column name>, ...`").  
  
 **BindField**  
 Die komplexeste der Vorgänge. Wie bereits erwähnt, in dem der Bindungsstruktur DAO verwendeten sieht `GetRows` eingerichtet ist. Wie Sie vom Code im sehen `DFX_Text` die Arten von Informationen in der Struktur enthalten den DAO-Typ verwendet (**DAO_CHAR** oder **DAO_WCHAR aus** im Fall von `DFX_Text`). Darüber hinaus wird der Typ der Bindung verwendet auch eingerichtet. In einem Abschnitt weiter oben `GetRows` nur kurz beschrieben wurde, aber es wurde erläutert, dass der Typ der Bindung, die von MFC verwendete immer direkt Adressbindung ist ausreichend (**DAOBINDING_DIRECT**). Darüber hinaus für Spalten variabler Länge Bindung (z. B. `DFX_Text`) Rückruf Bindung wird verwendet, sodass MFC können Sie, die speicherbelegung steuern und geben Sie eine Adresse, die richtige Länge. Dies bedeutet, MFC ersichtlich immer DAO "where", um die Daten, wodurch die direkte Bindung an Membervariablen versetzen wird. Der Rest der Bindungsstruktur ist mit z. B. die Adresse des Rückruffunktion Arbeitsspeicher Zuweisung und den Typ der spaltenbindung (Binden von Spaltennamen) ausgefüllt.  
  
 **BindParam**  
 Dies ist ein einfacher Vorgang, der Aufrufe `SetParamValue` mit dem Parameterwert in Ihre Parameterelements angegeben.  
  
 **Fixup**  
 Füllt die **NULL** Status für jedes Feld.  
  
 `SetFieldNull`  
 Dieser Vorgang nur kennzeichnet jede Feldstatus als **NULL** und legt das Element des Variablenwerts auf **PSEUDO_NULL**.  
  
 **SetDirtyField**  
 Aufrufe `SetFieldValue` für jedes Feld, das als geändert gekennzeichnet wurden.  
  
 Die verbleibenden Vorgänge betreffen nur mithilfe des Daten-Caches. Der Datencache ist ein zusätzlicher Puffer von Daten in den aktuellen Datensatz, der verwendet wird, um bestimmte Aspekte zu vereinfachen. Beispielsweise werden "unsaubere" Felder können automatisch erkannt. Wie in der Onlinedokumentation beschrieben kann es vollständig oder auf Feldebene deaktiviert werden. Die Implementierung des Puffers nutzt eine Karte. Diese Zuordnung wird verwendet, um dynamisch zugewiesene Kopien der Daten mit der Adresse des Felds "gebunden" entsprechen (oder `CDaoRecordset` Datenmember abgeleitet).  
  
 **AllocCache**  
 Dynamisch ordnet den zwischengespeicherten Feldwert aus, und die Zuordnung hinzugefügt.  
  
 **FreeCache**  
 Löscht die zwischengespeicherten Feldwert und entfernt es aus der Zuordnung.  
  
 **StoreField**  
 Den aktuelle Wert des Felds kopiert in den Datencache.  
  
 **LoadField**  
 Kopiert den zwischengespeicherten Wert in das Feld Element an.  
  
 **MarkForAddNew**  
 Überprüft, ob der aktuelle Wert des Felds ungleich ist**NULL** und kennzeichnet es fehlerhaft, falls erforderlich.  
  
 **MarkForEdit**  
 Vergleicht die aktuellen Feldwert mit Datencache aus, und bei Bedarf geändert markiert.  
  
> [!TIP]
>  Modellieren Sie Ihre benutzerdefinierte DFX-Routinen auf vorhandenen DFX-Routinen für standard-Datentypen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

