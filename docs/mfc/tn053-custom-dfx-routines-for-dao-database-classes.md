---
title: 'TN053: Benutzerdefinierte DFX-Routinen für DAO-Datenbankklassen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 262da283f20df1fe7af6aa02785e8c1ceb09dfda
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611093"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: Benutzerdefinierte DFX-Routinen für DAO-Datenbankklassen

> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützen DAO keine (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.

Diese technische Hinweis beschreibt die DAO-Datensatzfeldaustausch (DFX)-Mechanismus. Um zu verstehen, geschieht in der DFX-Routinen, die `DFX_Text` Funktion wird als Beispiel ausführlich erläutert werden. Als weitere Quelle der Informationen, die diese technischen Hinweis können Sie dem Code für die anderen die einzelne DFX-Funktionen untersuchen. Sie benötigen wahrscheinlich keine benutzerdefinierte DFX-Routine beliebig oft benötigen Sie eine benutzerdefinierte RFX-Routine (mit ODBC-Datenbankklassen verwendet).

Diese technische Hinweis enthält:

- DFX-Übersicht

- [Beispiele für](#_mfcnotes_tn053_examples) mithilfe von DAO-Datensatzfeldaustausch und dynamische Bindung

- [Funktionsweise der DFX](#_mfcnotes_tn053_how_dfx_works)

- [Was bewirkt, dass Ihre benutzerdefinierte DFX-Routine](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [Details der DFX_Text](#_mfcnotes_tn053_details_of_dfx_text)

**DFX-Übersicht**

In den Austauschmechanismus für DAO-Datensatzfeldaustausch (DFX) Dient zur Vereinfachung der Anweisungen zum Abrufen und Aktualisieren von Daten bei Verwendung der `CDaoRecordset` Klasse. Der Prozess wird über die Datenmember der vereinfacht die `CDaoRecordset` Klasse. Durch Ableiten von `CDaoRecordset`, Sie können Datenelemente hinzufügen, in die abgeleitete Klasse, die jedes Feld in einer Tabelle oder Abfrage darstellt. Diesem "statischen" Bindungsmechanismus ist einfach, aber er möglicherweise nicht die Daten abrufen/Update-Methode Ihrer Wahl für alle Anwendungen. DFX Ruft alle gebundenes Feld jedes Mal, wenn der aktuelle Datensatz geändert wird. Wenn Sie eine leistungsabhängigen Anwendung, die keine erfordert jedes Feld abrufen entwickeln, wenn die Währung geändert wird, "dynamische Bindung" über `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue` möglicherweise die Datenzugriffsmethode Ihrer Wahl.

> [!NOTE]
>  DFX und dynamische Bindung sind nicht gegenseitig aus, damit eine kombinierte Verwendung der statische und dynamische Bindung verwendet werden kann.

## <a name="_mfcnotes_tn053_examples"></a> Beispiel 1: Verwenden von DAO-Datensatzfeldaustausch nur

(setzt voraus `CDaoRecordset` – abgeleitete Klasse `CMySet` bereits geöffnet)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Beispiel 2: Verwenden der dynamischen Bindung**

(wird vorausgesetzt, dass `CDaoRecordset` -Klasse, `rs`, und es ist bereits geöffnet)

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

**Beispiel 3: Verwenden von DAO-Datensatzfeldaustausch und dynamische Bindung**

(geht davon aus durchsuchen Mitarbeiterdaten mit `CDaoRecordset`-abgeleitete Klasse `emp`)

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

## <a name="_mfcnotes_tn053_how_dfx_works"></a> Funktionsweise der DFX

Der DFX-Mechanismus funktioniert in ähnlicher Weise wie Datensatzfeldaustausch (RFX) Austauschmechanismus von den MFC-ODBC-Klassen verwendet. Die Prinzipien des DFX und RFX sind identisch, aber es gibt zahlreiche interne Unterschiede. Das Design der DFX-Funktionen wurde so, dass praktisch der gesamte Code der einzelnen DFX-Routinen freigegeben wird. Führt Sie auf der höchsten Ebene DFX nur wenige Aufgaben aus.

- DFX erstellt der SQL- **wählen** -Klausel und SQL **Parameter** -Klausel, wenn erforderlich.

- DFX erstellt der Bindungsstruktur von DAO verwendete `GetRows` Funktion (mehr dazu später).

- DFX verwaltet den Datenpuffer modifizierte Felder ermittelt (wenn es sich um eine doppelte Pufferung verwendet wird)

- DFX verwaltet die **NULL** und **DIRTY** Status arrays und ggf. legt Werte für Updates fest.

Das Herzstück der DFX Mechanismus ist das `CDaoRecordset` abgeleiteten Klasse die `DoFieldExchange` Funktion. Diese Funktion sendet Aufrufe an die einzelnen DFX-Funktionen eines entsprechenden Vorgang-Typs. Vor dem Aufruf `DoFieldExchange` die interne MFC-Funktionen legen Sie den Vorgangstyp. Die folgende Liste enthält, die verschiedene Vorgangstypen und eine kurze Beschreibung.

|Vorgang|Beschreibung|
|---------------|-----------------|
|`AddToParameterList`|Parameter-Klausel erstellt|
|`AddToSelectList`|Builds SELECT-Klausel|
|`BindField`|Richtet DBBINDING-Struktur|
|`BindParam`|Legt die Parameterwerte fest|
|`Fixup`|Legt die NULL-status|
|`AllocCache`|Ordnet der Cache für fehlerhafte Überprüfung|
|`StoreField`|Speichert aktuellen Datensatz cache|
|`LoadField`|Wiederherstellungen Cache an Memberwerten|
|`FreeCache`|Cache frei|
|`SetFieldNull`|Legt das Feld Status & Wert auf NULL|
|`MarkForAddNew`|Markierungen Felder geändert andernfalls PSEUDO-NULL|
|`MarkForEdit`|Markierungen Felder geändert If stimmen nicht überein cache|
|`SetDirtyField`|Legt Feldwerte als geändert markiert|

Im nächsten Abschnitt wird jeder Vorgang im Detail für erläutert werden `DFX_Text`.

Die wichtigste Funktion, über den DAO-Datensatzfeldaustausch Exchange-Prozess zu verstehen ist, verwendet der `GetRows` Funktion der `CDaoRecordset` Objekt. Die DAO `GetRows` -Funktion auf verschiedene Weise funktioniert. Diese technische Hinweis wird nur kurz beschrieben `GetRows` außerhalb des Bereichs dieser technischen Hinweis unverändert.

DAO `GetRows` können auf verschiedene Weise arbeiten.

- Sie können mehrere Datensätze und mehrere Datenfelder auf einmal abzurufen. Dadurch können für einen schnelleren Datenzugriff mit der Komplikation für den Umgang mit der eine große Datenstruktur und die geeigneten Offsets für jedes Feld an und für jeden Datensatz der Daten in der Struktur. MFC ist nicht diesem mehrere Datensätze abrufen Mechanismus nutzen.

- Eine weitere Möglichkeit `GetRows` können Arbeit ist, Programmierern die Bindungsadressen für die abgerufenen Daten der einzelnen Felder für einen Datensatz, der Daten angeben können.

- DAO wird auch "der Aufrufer für Spalten variabler Länge Rückruf in" damit den Aufrufer Arbeitsspeicher belegt werden kann. Diese zweite Funktion hat den Vorteil der Verringerung der Anzahl von Kopien der Daten sowie das direkte Speichern von Daten in die Member einer Klasse ermöglicht (die `CDaoRecordset` abgeleitete Klasse). Dieser zweite Mechanismus ist die Methode, die MFC verwendet, um die Bindung an Datenelemente in `CDaoRecordset` abgeleiteten Klassen.

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Was bewirkt, dass Ihre benutzerdefinierte DFX-Routine

Es ist von dieser Beschreibung, die der wichtigste Vorgang, der in jeder DFX-Funktion implementiert die Möglichkeit, die gegebenenfalls Datenstrukturen einzurichten, erfolgreich aufgerufen werden, muss offensichtlich `GetRows`. Es gibt zahlreiche andere Vorgänge, die eine DFX-Funktion auch unterstützen muss, aber keine als wichtige oder komplex sein wie die ordnungsgemäß für die Vorbereitung der `GetRows` aufrufen.

Die Verwendung von DFX wird in der Onlinedokumentation beschrieben. Es gibt im Wesentlichen zwei Anforderungen. Zunächst müssen Elemente hinzugefügt werden, um die `CDaoRecordset` abgeleitete Klasse für alle gebundenen Feld und Parameter. Dieses `CDaoRecordset::DoFieldExchange` sollte überschrieben werden. Beachten Sie, dass der Datentyp des Elements wichtig ist. Sie sollten mit den Daten aus dem Feld in der Datenbank überein, oder mindestens auf diesen Typ konvertiert werden. Z. B. ein numerisches Feld in der Datenbank, z. B. eine lange ganze Zahl, stets in Text umgewandelt und gebunden werden, um eine `CString` Member, aber ein Textfeld in einer Datenbank kann nicht unbedingt in eine numerische Darstellung, wie z. B. long integer-Wert konvertiert und an eine lange Integ gebunden er Member. DAO und der Microsoft Jet-Datenbank-Engine sind verantwortlich für die Konvertierung (anstelle von MFC-).

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> Details der DFX_Text

Wie bereits erwähnt, ist erklären, wie DFX funktioniert am besten anhand eines Beispiels funktioniert. Zu diesem Zweck über die Interna der `DFX_Text` sollte sehr gut funktionieren, um mindestens ein grundlegendes Verständnis der DFX zu bieten.

- `AddToParameterList`

   Dieser Vorgang erstellt die SQL-Anweisung **Parameter** -Klausel ("`Parameters <param name>, <param type> ... ;`") von Jet erforderlich sind. Jeder Parameter ist mit dem Namen und (gemäß der RFX-Aufruf) eingegeben. Finden Sie unter der Funktion `CDaoFieldExchange::AppendParamType` Funktion, um die Namen der einzelnen Typen angezeigt. Im Fall von `DFX_Text`, ist der verwendete Typ **Text**.

- `AddToSelectList`

   Erstellt die SQL-Anweisung **wählen** Klausel. Dies ist ziemlich einfach, wie der durch den Aufruf DFX angegebene Spaltennamen einfach angefügt wird ("`SELECT <column name>, ...`").

- `BindField`

   Die meisten komplexen Vorgänge. Wie bereits erwähnt, dies ist, wenn der Bindungsstruktur DAO verwendet `GetRows` eingerichtet ist. Wie Sie aus dem Code in sehen `DFX_Text` die Typen von Informationen in der Struktur enthalten den DAO-Typ verwendet (**DAO_CHAR** oder **DAO_WCHAR aus** im Fall von `DFX_Text`). Darüber hinaus wird der Typ der verwendeten Bindung auch eingerichtet. In einem vorherigen Abschnitt `GetRows` nur kurz beschrieben wurde, aber es ausreichen, um zu erklären, dass Sie der Typ der Bindung, die von MFC verwendete immer direkte Adressierung Bindung war (**DAOBINDING_DIRECT**). Darüber hinaus für die Bindung der Spalte mit variabler Länge (z. B. `DFX_Text`) Rückruf Bindung wird verwendet, sodass MFC die speicherbelegung zu steuern kann, und geben Sie eine Adresse in der richtigen Länge. Dies bedeutet, MFC kann DAO immer "where", um die Daten, sodass die Bindung direkt auf Membervariablen abzulegen feststellen. Dinge wie die Adresse der Memory Allocation Callback-Funktion und den Typ der spaltenbindung (über den Spaltennamen Binden) wird in der Rest der Bindungsstruktur eingetragen.

- `BindParam`

   Dies ist ein einfacher Vorgang, der Aufrufe `SetParamValue` mit dem Parameterwert, der in Ihrem Parameterelements angegeben.

- `Fixup`

   Füllt die **NULL** Status für jedes Feld.

- `SetFieldNull`

   Dieser Vorgang nur markiert den Status für jedes Feld als **NULL** und legt das Element des Variablenwerts auf **PSEUDO_NULL**.

- `SetDirtyField`

   Aufrufe `SetFieldValue` für jedes Feld geändert markiert.

Alle verbleibenden Vorgänge betreffen nur mithilfe des Daten-Caches. Das dem Datencache ist ein zusätzlicher Puffer der Daten in den aktuellen Datensatz, der verwendet wird, um bestimmte Dinge zu vereinfachen. Beispielsweise können "dirty" Felder automatisch erkannt werden. Wie in der Onlinedokumentation beschrieben kann es vollständig oder auf Feldebene deaktiviert werden. Die Implementierung des Puffers verwendet eine Zuordnung. Diese Zuordnung wird verwendet, um dynamisch zugewiesene Kopien der Daten mit der Adresse des Felds "gebunden" übereinstimmen (oder `CDaoRecordset` Datenmember abgeleitet).

- `AllocCache`

   Dynamisch ordnet den zwischengespeicherten Feldwert aus, und fügt es der Zuordnung hinzu.

- `FreeCache`

   Löscht die zwischengespeicherten Feldwert aus, und entfernt sie aus der Zuordnung.

- `StoreField`

   Kopiert den aktuellen Feldwert in Datencache.

- `LoadField`

   Kopiert den zwischengespeicherten Wert im Feld-Element.

- `MarkForAddNew`

   Überprüft, ob der aktuelle Wert des Felds nicht ist**NULL** und markiert ihn geändert, wenn erforderlich.

- `MarkForEdit`

   Vergleicht die aktuelle Wert des Felds mit dem Datencache und bei Bedarf geändert markiert.

> [!TIP]
> Modellieren Sie Ihre benutzerdefinierten DFX-Routinen für die vorhandenen DFX-Routinen für standard-Datentypen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
