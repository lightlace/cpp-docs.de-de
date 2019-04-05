---
title: 'Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
ms.openlocfilehash: 28c885119816c1df662cc0b941e02cb3cf747f3d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024607"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

> [!NOTE]
>  Sie können jetzt Datensätze in einer Sammeloperation effizienter hinzufügen. Weitere Informationen finden Sie unter [Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).

> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die gesammelte verwenden werden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Mit aktualisierbaren Momentaufnahmen und Dynasets können Sie Datensätze hinzufügen, bearbeiten (aktualisieren) und löschen. In diesem Thema wird Folgendes erläutert:

- [Vorgehensweise: bestimmen, ob das Recordset aktualisierbar ist](#_core_determining_whether_your_recordset_is_updatable).

- [Gewusst wie: Hinzufügen eines neuen Datensatzes](#_core_adding_a_record_to_a_recordset).

- [Gewusst wie: bearbeiten ein vorhandenes Datensatzes](#_core_editing_a_record_in_a_recordset).

- [Vorgehensweise: Löschen ein Datensatzes](#_core_deleting_a_record_from_a_recordset).

Weitere Informationen, wie Aktualisierungen durchgeführt werden heraus, und Ihre Updates für andere Benutzer angezeigt werden, finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md). Wenn Sie einen Datensatz hinzufügen, ändern oder löschen, ändert das Recordset die Datenquelle normalerweise sofort. Alternativ können Sie Gruppen zusammengehöriger Aktualisierungen zu Transaktionen zusammenfassen. Während einer Transaktion werden die Aktualisierungen nicht vor Bestätigung der Transaktion endgültig. So können Sie die Änderungen zurücksetzen. Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

In der folgenden Tabelle ist zusammengefasst, welche Optionen für Recordsets zur Verfügung stehen mit den jeweiligen Aktualisierungsmerkmalen.

### <a name="recordset-readupdate-options"></a>Lese- und Aktualisierungsoptionen von Recordsets

|Typ|Thema|Datensatz bearbeiten|Datensatz löschen|Neue hinzufügen (anhängen)|
|----------|----------|-----------------|-------------------|------------------------|
|Schreibgeschützt|J|N|N|N|
|Nur erweiterbar|J|N|N|J|
|Ohne Einschränkungen aktualisierbar|J|J|J|J|

##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> Bestimmen, ob das Recordset ist aktualisierbar

Ein Recordset-Objekt ist aktualisierbar, wenn die Datenquelle aktualisierbar ist und Sie das Recordset als aktualisierbar geöffnet haben. Außerdem hängt die Aktualisierbarkeit von der verwendeten SQL-Anweisung ab, von den Fähigkeiten des ODBC-Treibers und davon, ob die ODBC-Cursorbibliothek geladen ist. Sie können ein schreibgeschütztes Recordset oder eine schreibgeschützte Datenquelle nicht aktualisieren.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>So stellen Sie fest, ob das Recordset aktualisierbar ist

1. Aufrufen des Recordset-Objekts [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Member-Funktion.

   `CanUpdate` Gibt einen Wert ungleich NULL zurück, wenn das Recordset aktualisierbar ist.

Standardmäßig sind Recordsets aktualisierbar (durchführen können `AddNew`, `Edit`, und `Delete` Vorgänge). Sie können jedoch auch die [AppendOnly](../../mfc/reference/crecordset-class.md#open) können aktualisierbare Recordsets zu öffnen. Zu einem auf diese Weise geöffneten Recordset können Sie lediglich mit `AddNew` neue Datensätze hinzufügen. Sie können keine vorhandenen Datensätze bearbeiten oder löschen. Sie können testen, ob ein Recordset nur zum durch Aufrufen von Anhängen geöffnet ist die [CanAppend](../../mfc/reference/crecordset-class.md#canappend) Member-Funktion. `CanAppend` Gibt einen Wert ungleich NULL zurück, wenn das Recordset vollständig aktualisierbar ist oder nur zum Anhängen geöffnet ist.

Der folgende Codeausschnitt zeigt, wie Sie `CanUpdate` in einem Recordset-Objekt mit dem Namen `rsStudentSet` aufrufen können:

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
>  Vorbereitung für die Aktualisierung eines Recordsets durch Aufrufen von `Update`, müssen Sie sicherstellen, dass das Recordset alle Spalten, aus denen der Primärschlüssel der Tabelle (oder alle Spalten eines eindeutigen Index für die Tabelle) umfasst. In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind. Wenn nicht sämtliche benötigten Spalten zur Verfügung stehen, werden möglicherweise mehrere Datensätze in der Tabelle aktualisiert. Hierdurch kann die referenzielle Integrität der Tabelle beschädigt werden. In diesem Fall das Framework Ausnahmen auslöst, wenn Sie aufrufen `Update`.

##  <a name="_core_adding_a_record_to_a_recordset"></a> Hinzufügen eines Eintrags zu einem Recordset

Sie können neue Datensätze zu einem Recordset hinzufügen, wenn die [CanAppend](../../mfc/reference/crecordset-class.md#canappend) Memberfunktion gibt einen Wert ungleich NULL zurück.

#### <a name="to-add-a-new-record-to-a-recordset"></a>So fügen Sie einem Recordset einen neuen Datensatz hinzu

1. Stellen Sie sicher, dass das Recordset erweiterbar ist.

1. Aufrufen des Recordset-Objekts [AddNew](../../mfc/reference/crecordset-class.md#addnew) Member-Funktion.

   `AddNew` Bereitet das Recordset als Bearbeitungspuffer fungieren. Alle Felddatenmember werden auf den Spezialwert Null festgelegt und als nicht geändert markiert, sodass nur geänderte Werte an die Datenquelle, beim Aufrufen geschrieben werden [Update](../../mfc/reference/crecordset-class.md#update).

1. Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.

   Weisen Sie den Felddatenmembern Werte zu. Felddatenelemente, denen Sie keinen Wert zugewiesen haben, werden nicht in die Datenquelle geschrieben.

1. Aufrufen des Recordset-Objekts `Update` Member-Funktion.

   `Update` Schließt das Hinzufügen von beim Schreiben des neuen Eintrags in der Datenquelle ab. Für Informationen zu geschieht, wenn Sie nicht aufrufen, `Update`, finden Sie unter [Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Weitere Informationen zum Hinzufügen von Datensätzen und wann hinzugefügte Datensätze im Recordset angezeigt werden, finden Sie unter [Recordset: Wie AddNew, bearbeiten und Löschen von Arbeit (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).

Das folgende Beispiel zeigt, wie Sie einen neuen Datensatz hinzufügen:

```cpp
if( !rsStudent.Open( ) )
    return FALSE;
if( !rsStudent.CanAppend( ) )
    return FALSE;                      // no field values were set
rsStudent.AddNew( );
rsStudent.m_strName = strName;
rsStudent.m_strCity = strCity;
rsStudent.m_strStreet = strStreet;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not added; no field values were set." );
    return FALSE;
}
```

> [!TIP]
>  Zum Abbrechen einer `AddNew` oder `Edit` aufrufen, stellen Sie einfach einen anderen Aufruf `AddNew` oder `Edit` oder rufen Sie `Move` mit der *AFX_MOVE_REFRESH* Parameter. Datenmember werden auf ihren vorherigen Wert zurückgesetzt, und Sie sind nach wie vor in `Edit` oder `Add` Modus.

##  <a name="_core_editing_a_record_in_a_recordset"></a> Bearbeiten eines Datensatzes in einem Recordset

Sie können vorhandene Datensätze bearbeiten, wenn des Recordsets [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Memberfunktion gibt einen Wert ungleich NULL zurück.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>So bearbeiten Sie einen vorhandenen Datensatz in einem Recordset

1. Stellen Sie sicher, dass das Recordset aktualisierbar ist.

1. Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.

1. Aufrufen des Recordset-Objekts [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Member-Funktion.

   `Edit` Bereitet das Recordset als Bearbeitungspuffer fungieren. Alle Felddatenmember werden so markiert, dass das Recordset später feststellen kann, ob sie geändert wurden. Die neuen Werte für die geänderten Felddatenmember werden an die Datenquelle geschrieben, wenn Sie aufrufen [Update](../../mfc/reference/crecordset-class.md#update).

1. Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.

   Weisen Sie den Felddatenmembern Werte zu. Felddatenmember, denen Sie keine Werte zuweisen, bleiben unverändert.

1. Aufrufen des Recordset-Objekts `Update` Member-Funktion.

   `Update` Schließt das Bearbeiten von den geänderten Datensatz in die Datenquelle schreibt. Für Informationen zu geschieht, wenn Sie nicht aufrufen, `Update`, finden Sie unter [Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Nachdem Sie einen Datensatz bearbeitet haben, bleibt er der aktuelle Datensatz.

Das folgende Beispiel zeigt eine `Edit` Vorgang. Dabei wird vorausgesetzt, dass der Benutzer zu einem Datensatz gewechselt hat, den er bearbeiten möchte.

```cpp
rsStudent.Edit( );
rsStudent.m_strStreet = strNewStreet;
rsStudent.m_strCity = strNewCity;
rsStudent.m_strState = strNewState;
rsStudent.m_strPostalCode = strNewPostalCode;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not updated; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> Zum Abbrechen einer `AddNew` oder `Edit` aufrufen, stellen Sie einfach einen anderen Aufruf `AddNew` oder `Edit` oder rufen Sie `Move` mit der *AFX_MOVE_REFRESH* Parameter. Datenmember werden auf ihren vorherigen Wert zurückgesetzt, und Sie sind nach wie vor in `Edit` oder `Add` Modus.

##  <a name="_core_deleting_a_record_from_a_recordset"></a> Löschen eines Datensatzes aus einem Recordset

Sie können Datensätze löschen, wenn des Recordsets [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Memberfunktion gibt einen Wert ungleich NULL zurück.

#### <a name="to-delete-a-record"></a>So löschen Sie einen Datensatz

1. Stellen Sie sicher, dass das Recordset aktualisierbar ist.

1. Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.

1. Aufrufen des Recordset-Objekts [löschen](../../mfc/reference/crecordset-class.md#delete) Member-Funktion.

   `Delete` markiert den Datensatz als gelöscht, sowohl im Recordset als auch für die Datenquelle.

   Im Gegensatz zu `AddNew` und `Edit`, `Delete` weist kein entsprechendes `Update` aufrufen.

1. Wechseln Sie zu einem anderen Datensatz.

   > [!NOTE]
   >  Beim Scrollen durch das Recordset werden gelöschte Datensätze unter Umständen nicht übersprungen. Weitere Informationen finden Sie unter den [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) Member-Funktion.

Das folgende Beispiel zeigt eine `Delete` Vorgang. Dabei wird vorausgesetzt, dass der Benutzer zu einem zu löschenden Datensatz gewechselt ist. Nach dem `Delete` wird aufgerufen, es ist wichtig, um einen neuen Datensatz zu verschieben.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

Weitere Informationen zu den Auswirkungen der `AddNew`, `Edit`, und `Delete` Member-Funktionen, finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)