---
title: 'TN053: Benutzerdefinierte DFX-Routinen für DAO-Datenbankklassen'
ms.date: 09/17/2019
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
ms.openlocfilehash: 949e1a07b2b45b01b08efb368046e0c65b1264e1
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095985"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: Benutzerdefinierte DFX-Routinen für DAO-Datenbankklassen

> [!NOTE]
>  DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft. Die visuelle C++ Umgebung und die Assistenten unterstützen DAO nicht (obwohl die DAO-Klassen eingeschlossen sind und Sie Sie weiterhin verwenden können). Microsoft empfiehlt, [OLE DB Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte zu verwenden. Sie sollten DAO nur für die Wartung vorhandener Anwendungen verwenden.

Dieser Technische Hinweis beschreibt den DAO-Mechanismus für den Daten Satz Feld Austausch (DFX). Um zu verstehen, was in den DFX-Routinen passiert, `DFX_Text` wird die-Funktion ausführlich als Beispiel erläutert. Als zusätzliche Informationsquelle für diese Technische Notiz können Sie den Code für die anderen DFX-Funktionen überprüfen. Wahrscheinlich benötigen Sie eine benutzerdefinierte DFX-Routine nicht so oft wie möglicherweise eine benutzerdefinierte RFX-Routine (die mit ODBC-Datenbankklassen verwendet wird).

Dieser Technische Hinweis enthält Folgendes:

- DFX-Übersicht

- [Beispiele für](#_mfcnotes_tn053_examples) die Verwendung von DAO-Daten Satz Feld Austausch und dynamischer Bindung

- [Funktionsweise von DFX](#_mfcnotes_tn053_how_dfx_works)

- [Funktionsweise der benutzerdefinierten DFX-Routine](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [Details zu DFX_Text](#_mfcnotes_tn053_details_of_dfx_text)

**DFX-Übersicht**

Der DAO-Daten Satz Feld Austausch-Mechanismus (DFX) wird verwendet, um die Vorgehensweise beim Abrufen und Aktualisieren von `CDaoRecordset` Daten bei Verwendung der-Klasse zu vereinfachen. Der Prozess wird mithilfe von Datenmembern der `CDaoRecordset` -Klasse vereinfacht. Durch Ableiten von `CDaoRecordset`können Sie der abgeleiteten Klasse Datenelemente hinzufügen, die jedes Feld in einer Tabelle oder Abfrage darstellen. Dieser "statische Bindungs Mechanismus" ist einfach, ist aber möglicherweise nicht die für alle Anwendungen bevorzugte Methode zum Abrufen und Aktualisieren von Daten. DFX Ruft jedes gebundene Feld jedes Mal ab, wenn der aktuelle Datensatz geändert wird. Wenn Sie eine leistungsabhängige Anwendung entwickeln, die nicht jedes Feld abrufen muss, wenn die Währung geändert wird, ist "dynamische Bindung" über `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue` möglicherweise die Datenzugriffs Methode Ihrer Wahl.

> [!NOTE]
>  DFX und dynamische Bindung schließen sich nicht gegenseitig aus, sodass eine hybride Verwendung statischer und dynamischer Bindungen verwendet werden kann.

## <a name="_mfcnotes_tn053_examples"></a>Beispiel 1 – Verwendung von DAO-Daten Satz Feld Austausch

(geht `CDaoRecordset` davon aus, `CMySet` dass – abgeleitete Klasse bereits geöffnet

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Beispiel 2 – Verwendung der dynamischen Bindung**

(geht von `CDaoRecordset` der Verwendung `rs`der-Klasse aus, die bereits geöffnet ist.)

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

**Beispiel 3 – Verwendung von DAO-Daten Satz Feld Austausch und dynamischer Bindung**

(setzt das Durchsuchen von `CDaoRecordset`Mitarbeiterdaten mit `emp`der von abgeleiteten Klasse voraus

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

Der DFX-Mechanismus funktioniert ähnlich wie der von den MFC-ODBC-Klassen verwendete Daten Satz Feld Austausch (RFX)-Mechanismus. Die Prinzipien von DFX und RFX sind identisch, aber es gibt zahlreiche interne Unterschiede. Der Entwurf der DFX-Funktionen war so, dass praktisch der gesamte Code von den einzelnen DFX-Routinen gemeinsam genutzt wird. Auf der höchsten Ebene führt DFX nur einige Dinge aus.

- DFX konstruiert bei Bedarf die SQL **Select** -Klausel und die SQL- **Parameter** Klausel.

- DFX konstruiert die Bindungsstruktur, die von der `GetRows` DAO-Funktion verwendet wird (mehr dazu später).

- DFX verwaltet den Datenpuffer, der zum Erkennen von geänderten Feldern verwendet wird (wenn die doppelte Pufferung verwendet wird).

- DFX verwaltet die Status Arrays **null** und **Dirty** und legt bei Bedarf Werte für Updates fest.

Das Herzstück des DFX- `CDaoRecordset` `DoFieldExchange` Mechanismus ist die Funktion der abgeleiteten Klasse. Diese Funktion sendet Aufrufe an die einzelnen DFX-Funktionen eines entsprechenden Vorgangs Typs. Legen Sie `DoFieldExchange` vor dem Aufrufen der internen MFC-Funktionen den Vorgangstyp fest. In der folgenden Liste sind die verschiedenen Vorgangs Typen und eine kurze Beschreibung aufgeführt.

|Vorgang|Beschreibung|
|---------------|-----------------|
|`AddToParameterList`|Builds Parameters-Klausel|
|`AddToSelectList`|Builds SELECT-Klausel|
|`BindField`|Richtet die Bindungsstruktur ein.|
|`BindParam`|Legt Parameterwerte fest.|
|`Fixup`|Legt den Status NULL fest|
|`AllocCache`|Ordnet den Cache für die geänderte Prüfung zu.|
|`StoreField`|Speichert den aktuellen Datensatz im Cache.|
|`LoadField`|Wiederherstellen von Cache-und Element Werten|
|`FreeCache`|Freigibt Cache|
|`SetFieldNull`|Legt den Feld Status & Wert auf NULL fest.|
|`MarkForAddNew`|Markiert Felder, die geändert werden, wenn nicht Pseudo NULL ist|
|`MarkForEdit`|Markiert Felder, die geändert werden, wenn der Cache nicht entspricht|
|`SetDirtyField`|Legt Feldwerte als geändert fest.|

Im nächsten Abschnitt wird jeder Vorgang ausführlicher für `DFX_Text`erläutert.

Das wichtigste Feature, das über den DAO-Daten Satz Feld Austauschprozess zu verstehen ist, `GetRows` besteht darin, `CDaoRecordset` dass die-Funktion des-Objekts verwendet wird. Die DAO `GetRows` -Funktion kann auf verschiedene Weise funktionieren. Dieser Technische Hinweis beschreibt `GetRows` nur kurz, wie er sich außerhalb des Umfangs dieses technischen Hinweises befindet.
DAO 3,6 ist die endgültige Version und wird als veraltet eingestuft. `GetRows`kann auf verschiedene Weise funktionieren.

- Es können mehrere Datensätze und mehrere Datenfelder gleichzeitig abgerufen werden. Dies ermöglicht einen schnelleren Datenzugriff mit der Komplikation einer großen Datenstruktur und der entsprechenden Offsets für jedes Feld und für jeden Daten Satz in der Struktur. MFC nutzt diesen mehrfachen Abruf Mechanismus nicht.

- Eine andere `GetRows` Möglichkeit besteht darin, Programmierern die Angabe von Bindungs Adressen für die abgerufenen Daten jedes Felds für einen Datensatz von Daten zu gestatten.

- DAO führt auch einen Aufruf an den Aufrufer für Spalten mit variabler Länge durch, um dem Aufrufer das Zuweisen von Arbeitsspeicher zu ermöglichen. Dieses zweite Feature hat den Vorteil, dass die Anzahl der Datenkopien minimiert und die direkte Speicherung von Daten in Member einer Klasse (die `CDaoRecordset` abgeleitete Klasse) ermöglicht wird. Dieser zweite Mechanismus ist die Methode, die MFC verwendet, um Datenelemente `CDaoRecordset` in abgeleiteten Klassen zu binden.

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>Funktionsweise der benutzerdefinierten DFX-Routine

Es ist offensichtlich, dass der wichtigste Vorgang, der in jeder DFX-Funktion implementiert ist, die Möglichkeit sein muss, die erforderlichen Datenstrukturen einzurichten, `GetRows`um erfolgreich aufgerufen werden zu können. Es gibt eine Reihe von anderen Vorgängen, die eine DFX-Funktion ebenfalls unterstützen muss, aber keine so wichtig oder komplex ist wie `GetRows` die ordnungsgemäße Vorbereitung des Aufrufes.

Die Verwendung von DFX wird in der Online Dokumentation beschrieben. Im Wesentlichen gibt es zwei Anforderungen. Zuerst müssen die Member der `CDaoRecordset` abgeleiteten Klasse für jedes gebundene Feld und jeden Parameter hinzugefügt werden. Das `CDaoRecordset::DoFieldExchange` folgende sollte überschrieben werden. Beachten Sie, dass der Datentyp des Members wichtig ist. Er sollte den Daten aus dem Feld in der Datenbank entsprechen oder zumindest in diesen Typ konvertierbar sein. Beispielsweise kann ein numerisches Feld in einer Datenbank, z. b. eine lange ganze Zahl, immer in Text konvertiert `CString` und an einen Member gebunden werden, ein Textfeld in einer Datenbank kann jedoch nicht notwendigerweise in eine numerische Darstellung konvertiert werden, z. b. eine lange ganze Zahl, die an eine lange ganze Zahl gebunden ist. er-Member. DAO und das Microsoft Jet-Datenbankmodul sind für die Konvertierung (anstelle von MFC) verantwortlich.

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a>Details zu DFX_Text

Wie bereits erwähnt, ist die beste Möglichkeit, die Funktionsweise von DFX zu erläutern, das Arbeiten mit einem Beispiel. Zu diesem Zweck sollten die internale von `DFX_Text` sehr gut funktionieren, um mindestens ein grundlegendes Verständnis von DFX zu bieten.

- `AddToParameterList`

   Mit diesem Vorgang wird die für Jet erforderliche SQL`Parameters <param name>, <param type> ... ;`-Parameter Klausel ("") erstellt. Jeder Parameter wird benannt und eingegeben (wie im RFX-Befehl angegeben). Sehen Sie sich `CDaoFieldExchange::AppendParamType` die Funktions Funktion an, um die Namen der einzelnen Typen anzuzeigen. Im Fall von `DFX_Text`lautet der verwendete Typ **Text**.

- `AddToSelectList`

   Erstellt die SQL **Select** -Klausel. Dies ist recht einfach, da der durch den DFX-Befehl angegebene Spaltenname einfach angefügt wird`SELECT <column name>, ...`("").

- `BindField`

   Die komplizierteste der Vorgänge. Wie bereits erwähnt, wird hier die DAO-Bindungsstruktur eingerichtet `GetRows` , die von verwendet wird. Wie Sie `DFX_Text` aus dem Code in den Typen der Informationen in der Struktur sehen können, enthält der verwendete DAO-Typ (**DAO_CHAR** oder **DAO_WCHAR** im Fall `DFX_Text`von). Außerdem wird der Typ der verwendeten Bindung ebenfalls eingerichtet. In einem früheren Abschnitt `GetRows` wurde nur kurz beschrieben, aber es war ausreichend, zu erläutern, dass der von MFC verwendete Bindungstyp immer Direct Address Binding (**DAOBINDING_DIRECT**) ist. Außerdem wird für die Spalten Bindung mit variabler Länge ( `DFX_Text`wie) die Rückruf Bindung verwendet, damit MFC die Speicher Belegung steuern und eine Adresse mit der richtigen Länge angeben kann. Dies bedeutet, dass MFC DAO immer den "Where"-Wert anweisen kann, um die Daten zu platzieren, sodass direkt an Element Variablen gebunden werden kann. Der Rest der Bindungsstruktur ist mit Elementen wie der Adresse der Rückruffunktion für die Speicher Belegung und dem Typ der Spalten Bindung (Bindung nach Spaltenname) gefüllt.

- `BindParam`

   Dies ist ein einfacher Vorgang, der `SetParamValue` mit dem Parameterwert aufruft, der im Parameter Element angegeben ist.

- `Fixup`

   Füllt den **null** -Status für jedes Feld aus.

- `SetFieldNull`

   Durch diesen Vorgang wird jeder Feld Status nur als **null** gekennzeichnet, und der Wert der Element Variablen wird auf **PSEUDO_NULL**festgelegt.

- `SetDirtyField`

   Ruft `SetFieldValue` für jedes als "Dirty" markierte Feld auf.

Alle verbleibenden Vorgänge befassen sich nur mit der Verwendung des Daten Caches. Der Daten Cache ist ein zusätzlicher Puffer der Daten im aktuellen Datensatz, der verwendet wird, um bestimmte Dinge einfacher zu gestalten. Beispielsweise können "Dirty"-Felder automatisch erkannt werden. Wie in der Online Dokumentation beschrieben, kann Sie vollständig oder auf Feldebene ausgeschaltet werden. Die-Implementierung des Puffers nutzt eine Karte. Diese Zuordnung wird verwendet, um dynamisch zugeordnete Kopien der Daten mit der Adresse des gebundenen Felds (oder `CDaoRecordset` abgeleiteter Datenmember) zu vergleichen.

- `AllocCache`

   Ordnet den zwischengespeicherten Feldwert dynamisch zu und fügt ihn der Zuordnung hinzu.

- `FreeCache`

   Löscht den zwischengespeicherten Feldwert und entfernt ihn aus der Zuordnung.

- `StoreField`

   Kopiert den aktuellen Feldwert in den Daten Cache.

- `LoadField`

   Kopiert den zwischengespeicherten Wert in den Feldmember.

- `MarkForAddNew`

   Prüft, ob der aktuelle Feldwert ungleich**null** ist, und markiert ihn ggf. als fehlerhaft.

- `MarkForEdit`

   Vergleicht den aktuellen Feldwert mit dem Daten Cache und kennzeichnet ggf. eine Änderung.

> [!TIP]
> Modellieren Sie Ihre benutzerdefinierten DFX-Routinen in den vorhandenen DFX-Routinen für Standard Datentypen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
