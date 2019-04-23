---
title: 'Datensatzfeldaustausch: Funktionsweise von RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
ms.openlocfilehash: 7da9d480f16dcb6bc5ded0a1dff559b1b1ac4b38
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032676"
---
# <a name="record-field-exchange-how-rfx-works"></a>Datensatzfeldaustausch: Funktionsweise von RFX

In diesem Thema wird erläutert, den RFX-Prozess. Dies ist ein komplexes Thema abdeckenden:

- [RFX und das recordset](#_core_rfx_and_the_recordset)

- [Der RFX-Prozess](#_core_the_record_field_exchange_process)

> [!NOTE]
>  Dieses Thema gilt für Klassen, die von `CRecordset` in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird die Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_rfx_and_the_recordset"></a> RFX und das Recordset

Des Recordset-Objekts Felddatenmember, gemeinsam bilden eine Bearbeitungspuffers, der die ausgewählten Spalten eines Datensatzes enthält. Wenn das Recordset zuerst geöffnet wird und zum Lesen des ersten Datensatzes, RFX bindet (verknüpft) ausgewählte jede Spalte an die Adresse des entsprechenden Felds Datenmembers. Wenn das Recordset einen Datensatz aktualisiert wird, ruft RFX ODBC API-Funktionen zum Senden von einer SQL **UPDATE** oder **einfügen** Anweisung, um den Treiber. RFX verwendet sein Wissen um den Felddatenmembern an die Spalten aus, zu schreiben.

Das Framework sichert Bearbeitungspuffer in bestimmte Phasen nach, damit sie seinen Inhalt bei Bedarf wiederherstellen können. RFX sichert Bearbeitungspuffer, bevor Sie einen neuen Datensatz hinzufügen und Bearbeiten eines vorhandenen Datensatzes. Bearbeitungspuffer in einigen Fällen, z. B. wiederhergestellt, nachdem ein `Update` folgenden für Aufruf `AddNew`. Bearbeitungspuffer wird nicht wiederhergestellt werden, wenn Sie einen gerade geänderten Bearbeitungspuffer, z. B. verwerfen verschieben zu einem anderen Datensatz vor dem Aufruf `Update`.

Neben dem Austausch von Daten zwischen der Datenquelle und dem Recordset Felddatenmembern verwaltet RFX Bindungsparameter. Wenn das Recordset geöffnet wird, werden in der Reihenfolge der Parameterdatenmember gebunden das "?" Platzhalter in der SQL-Anweisung, die `CRecordset::Open` erstellt. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Der Recordset-Klasse außer Kraft setzen der `DoFieldExchange` übernimmt alle Aufgaben, Verschieben von Daten in beide Richtungen. Wie Dialogdatenaustausch (DDX) benötigt der RFX Informationen über die Datenmember der Klasse. Der Assistent enthält die erforderlichen Informationen, indem Sie schreiben eine Recordset-spezifische Implementierung der `DoFieldExchange` , basierend auf den Felddaten Member-Namen und Datentypen Sie, mit dem Assistenten angeben.

##  <a name="_core_the_record_field_exchange_process"></a> RFX-Prozess

In diesem Abschnitt wird die Abfolge der RFX-Ereignisse beschrieben, wie einem Recordset-Objekt geöffnet wird und wie Sie hinzugefügt haben, aktualisieren und Löschen von Datensätzen. In der Tabelle [Sequenz der RFX-Vorgänge beim Öffnen eines Recordset](#_core_sequence_of_rfx_operations_during_recordset_open) und die Tabelle [Sequenz der RFX-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling) in diesem Thema veranschaulichen die Vorgehensweise als RFX-Prozesse eine `Move` -Befehl in der Recordset und ein Update verwaltet. Während dieser Prozesse wird [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) aufgerufen, um viele verschiedene Operationen durchzuführen. Die `m_nOperation` Datenmember der [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) Objekt bestimmt, welcher Vorgang angefordert wird. Möglicherweise hilfreich sein, lesen Sie [Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [Recordset: Wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) vor der Lektüre dieses Materials.

###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: Binden von Spalten und Parametern

Die folgenden RFX-Aktivitäten auftreten, in der Reihenfolge angezeigt, wenn Sie einem Recordset-Objekt aufrufen [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion:

- Wenn das Recordset Parameterdatenmember verfügt, das Framework ruft `DoFieldExchange` , die Parameter, Platzhalter für Parameter in die Zeichenfolge des Recordsets SQL-Anweisung zu binden. Eine abhängige Typ-Darstellung des Werts des Parameters, für jeden Platzhalter verwendet wird Daten finden Sie in der **wählen** Anweisung. Dies tritt auf, nachdem die SQL-Anweisung vorbereitet wurde, jedoch bevor er ausgeführt wird. Informationen zur anweisungsvorbereitung, finden Sie unter den `::SQLPrepare` -Funktion in der ODBC *Programmer's Reference*.

- Das Framework ruft `DoFieldExchange` ein zweites Mal aus, um die Werte der ausgewählten Spalten entsprechende Felddatenmembern im Recordset zu binden. Dadurch wird das Recordset-Objekt als Bearbeitungspuffer mit den Spalten des ersten Datensatzes eingerichtet.

- Das Recordset führt die SQL-Anweisung aus, und die Datenquelle wählt den ersten Datensatz. Die Spalten des Datensatzes werden in die Recordset Felddatenmembern geladen.

Die folgende Tabelle zeigt die Reihenfolge der RFX-Vorgänge beim Öffnen eines Recordsets.

### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a> Reihenfolge der RFX-Vorgänge beim Öffnen eines Recordsets

|Der Vorgang|DoFieldExchange-Vorgang|Datenbank/SQL-Vorgang|
|--------------------|-------------------------------|-----------------------------|
|1. Öffnen des Recordsets.|||
||2. Erstellen Sie eine SQL-Anweisung.||
|||3. Senden Sie die SQL-Anweisung.|
||4. Parameterdatenmember zu binden.||
||5. Gebunden Sie Felddatenmember an Spalten.||
|||6. ODBC führt die Verschiebung und füllt mit Daten.|
||7. Beheben Sie die Daten für C++.||

Durch Recordsets verwenden ODBCs vorbereitete Ausführung, um für schnelles erneutes Abfragen mit der gleichen SQL-Anweisung ermöglichen. Weitere Informationen über die vorbereitete Ausführung finden Sie im ODBC-SDK *Programmer's Reference* in der MSDN Library.

###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: Scrollen

Wenn Sie von einem Datensatz in eine andere scrollen, um das Framework ruft `DoFieldExchange` , die zuvor in den Felddatenmembern Werte für den neuen Datensatz gespeicherten Werte ersetzen.

In der folgende Tabelle zeigt die Reihenfolge der RFX-Vorgänge auf, wenn der Benutzer von Datensatz zu Datensatz bewegt.

### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a> Reihenfolge der RFX-Vorgänge während des Bildlaufs

|Der Vorgang|DoFieldExchange-Vorgang|Datenbank/SQL-Vorgang|
|--------------------|-------------------------------|-----------------------------|
|1. Rufen Sie `MoveNext` oder einer anderen Funktion verschieben.|||
|||2. ODBC führt die Verschiebung und füllt mit Daten.|
||3. Beheben Sie die Daten für C++.||

###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: Neue Datensätze hinzufügen und Bearbeiten vorhandener Einträge

Wenn Sie einen neuen Datensatz hinzufügen, gilt die das Recordset als Bearbeitungspuffer, um den Inhalt des neuen Datensatzes zu erstellen. Wie beim Hinzufügen von Datensätzen, umfasst das Bearbeiten von Datensätzen ändern der Werte der Felddatenmember des Recordsets. Aus der RFX-Perspektive ist die Sequenz wie folgt:

1. Beim Aufruf des Recordsets [AddNew](../../mfc/reference/crecordset-class.md#addnew) oder [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Memberfunktion bewirkt, dass RFX, den aktuellen Bearbeitungspuffer zu speichern, damit sie später wiederhergestellt werden kann.

1. `AddNew` oder `Edit` bereitet die Felder im Bearbeitungspuffer vor, damit RFX geänderten Felddatenmember ermitteln kann.

   Da ein neuer Datensatz keine alten Werte mit neue Werten verglichen wurde `AddNew` legt den Wert jedes felddatenelement auf den Wert PSEUDO_NULL fest. Später beim Aufrufen `Update`, RFX wird jeder Datenmember-Wert, mit dem Wert PSEUDO_NULL verglichen. Wenn es ein Unterschied besteht, wurde der Datenmember festgelegt. (PSEUDO_NULL ist nicht identisch mit einer Spalte "Record" mit einem Null-Wert "true" noch eines dieser identisch mit C++ NULL.)

   Im Gegensatz zu den `Update` rufen Sie für `AddNew`, `Update` rufen Sie für `Edit` vergleicht aktualisierte Werte mit den zuvor gespeicherten Werte, anstatt PSEUDO_NULL. Der Unterschied besteht darin, die `AddNew` hat keine zuvor gespeicherten Werte für den Vergleich.

1. Sie können die Werte der Felddatenmember direkt festlegen, deren Werte, die Sie bearbeiten möchten, oder, dass Sie für einen neuen Datensatz füllen möchten. Dazu gehören Aufrufen `SetFieldNull`.

1. Den Aufruf von [Update](../../mfc/reference/crecordset-class.md#update) wird nach geänderten Felddatenmember, wie in Schritt 2 beschrieben (finden Sie in der Tabelle [Sequenz der RFX-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling)). Wenn keine Werte geändert haben, `Update` gibt 0 zurück. Wenn einige Felddatenmember geändert haben, `Update` vorbereitet und führt eine SQL **einfügen** -Anweisung, die Werte für alle aktualisierten Felder im Datensatz enthält.

1. Für `AddNew`, `Update` endet mit dem Wiederherstellen der zuvor gespeicherten Werten des Datensatzes, der vor dem aktuellen wurde die `AddNew` aufrufen. Für `Edit`, die neuen, geänderten Werte bleiben unverändert.

In der folgende Tabelle zeigt die Reihenfolge der RFX-Vorgänge auf, wenn Sie einen neuen Datensatz hinzufügen oder ein vorhandenes Datensatzes bearbeiten.

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>Reihenfolge der RFX-Vorgänge während der AddNew "und" Bearbeiten

|Der Vorgang|DoFieldExchange-Vorgang|Datenbank/SQL-Vorgang|
|--------------------|-------------------------------|-----------------------------|
|1. Rufen Sie `AddNew` oder `Edit`.|||
||2. Sichern Sie den Bearbeitungspuffer.||
||3. Für `AddNew`Felddatenmember als "sauber" zu markieren, und Null.||
|4. Recordset-Felddatenmembern Werte zuweisen.|||
|5. Rufen Sie `Update` auf.|||
||6. Überprüfen Sie die geänderten Felder.||
||7. Erstellen von SQL **einfügen** -Anweisung für `AddNew` oder **UPDATE** -Anweisung für `Edit`.||
|||8. Senden Sie die SQL-Anweisung.|
||9. Für `AddNew`, Bearbeitungspuffer wiederherstellen, auf deren Inhalte gesichert wurden. Für `Edit`, löschen Sie die Sicherung.||

### <a name="rfx-deleting-existing-records"></a>RFX: Löschen von vorhandenen Datensätzen

Wenn Sie einen Datensatz löschen, setzt der RFX alle Felder auf NULL als Erinnerung, die der Datensatz gelöscht, und Sie müssen aus einem Dienst verschieben. Sie können weitere Informationen zur RFX-Sequenz ist nicht erforderlich.

## <a name="see-also"></a>Siehe auch

[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange-Klasse](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)