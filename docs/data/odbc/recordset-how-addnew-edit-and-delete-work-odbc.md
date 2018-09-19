---
title: 'Recordset: AddNew, Edit und Delete Funktionsweise (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4f15e593300c45cf5bbc24b85eacee107dafca58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052230"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
In diesem Thema wird erläutert, wie die `AddNew`, `Edit`, und `Delete` Memberfunktionen der Klasse `CRecordset` arbeiten. Zu den behandelten Themen gehören:  
  
- [Hinzufügen von Datensätzen](#_core_adding_a_record)  
  
- [Sichtbarkeit der hinzugefügte Datensätze](#_core_visibility_of_added_records)  
  
- [Bearbeiten von Datensätzen](#_core_editing_an_existing_record)  
  
- [Löschen von Datensätzen](#_core_deleting_a_record)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die gesammelte verwenden werden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
Als Ergänzung, Sie möchten lesen [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md), dem die entsprechende Rolle von RFX in Aktualisierungsvorgängen beschrieben.  
  
##  <a name="_core_adding_a_record"></a> Hinzufügen eines Datensatzes  

Hinzufügen eines neuen Datensatzes zu einem Recordset beinhaltet den Aufruf des Recordsets [AddNew](../../mfc/reference/crecordset-class.md#addnew) Member-Funktion, wenn die Werte der Felddatenmember des neuen Datensatzes und dem Aufrufen der [Update](../../mfc/reference/crecordset-class.md#update) Memberfunktion schreiben der Datensatz mit der Datenquelle.  
  
Voraussetzung für den Aufruf `AddNew`, das Recordset nicht geöffnet worden sein muss als schreibgeschützt. Die `CanUpdate` und `CanAppend` Memberfunktionen können Sie die folgenden Bedingungen zu ermitteln.  
  
Beim Aufruf `AddNew`:  
  
- Der Datensatz im Bearbeitungspuffer wird gespeichert, sodass dessen Inhalt wiederhergestellt werden können, wenn der Vorgang abgebrochen wird.  
  
- Die Felddatenmember werden gekennzeichnet, daher ist es möglich, Änderungen in die sie später zu erkennen. Die Felddaten Member werden ebenfalls markiert bereinigen (unverändertes) und auf Null gesetzt.  
  
Nach dem Aufruf von `AddNew`Bearbeitungspuffer stellt einen neuen, leeren Datensatz, mit Werten gefüllt werden soll. Zu diesem Zweck legen Sie die Werte manuell von ihnen zuweisen. Anstatt einen tatsächliche Datenwert für ein Feld zu verwenden, können Sie aufrufen `SetFieldNull` an den Wert Null.  
  
Um die Änderungen zu speichern, rufen Sie `Update`. Beim Aufruf `Update` für den neuen Datensatz:  
  
- Wenn der ODBC-Treiber unterstützt die `::SQLSetPos` MFC-ODBC-API-Funktion verwendet die Funktion, um den Datensatz in der Datenquelle hinzuzufügen. Mit `::SQLSetPos`, kann MFC einen Datensatz effizienter hinzufügen, da es nicht zum Erstellen und eine SQL-Anweisung zu verarbeiten.  
  
- Wenn `::SQLSetPos` nicht verwendet, von MFC bewirkt Folgendes:  
  
    1.  Wenn keine Änderungen erkannt werden, `Update` führt keine Aktion aus und gibt 0 zurück.  
  
    2.  Wenn es Änderungen gibt, `Update` erstellt eine SQL- **einfügen** Anweisung. Spalten, deren alle Felddatenmember finden Sie in der **einfügen** Anweisung. Um eine Spalte zu erzwingen, rufen die [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) Memberfunktion:  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  `Update` Führt einen Commit für den neuen Datensatz, der **einfügen** -Anweisung ausgeführt wird und der Datensatz ist an die Tabelle in der Datenquelle (und auf das Recordset, wenn es sich nicht um eine Momentaufnahme handelt) ein Commit ausgeführt, es sei denn, eine Transaktion ausgeführt wird.  
  
    4.  Gespeicherte Datensatz wird im Bearbeitungspuffer wiederhergestellt. Der Datensatz, der vor dem aktuellen wurde die `AddNew` Aufruf ist der aktuelle Vorgang unabhängig davon, ob die **einfügen** -Anweisung erfolgreich ausgeführt wurde.  
  
    > [!TIP]
    >  Für die vollständige Kontrolle über einen neuen Datensatz, nehmen Sie die folgende Vorgehensweise: Legen Sie die Werte von Feldern, die über Werte verfügen und legen Sie dann alle Felder, die durch den Aufruf Null bleibt, explizit `SetFieldNull` mit einem Zeiger auf das Feld und den Parameter "true" (Standard). Wenn Sie möchten sicherstellen, dass ein Feld nicht in der Datenquelle, den Aufruf geschrieben wird `SetFieldDirty` mit einem Zeiger auf das Feld und den Parameter "false", und ändern Sie den Wert des Felds nicht. Um zu bestimmen, ob ein Feld NULL zulässig ist, rufen Sie `IsFieldNullable`.  
  
    > [!TIP]
    >  Zum erkennen, wenn Recordsets Wert ändern, verwendet MFC einen PSEUDO_NULL-Wert für jeden Datentyp, der in einem Recordset gespeichert werden können. Wenn ein Feld mit dem PSEUDO_NULL Wert explizit festlegen müssen und das Feld bereits erfolgt, Null gekennzeichnet werden, müssen Sie auch aufrufen `SetFieldNull`, übergeben Sie die Adresse des Felds in den ersten Parameter und "false", im zweiten Parameter.  
  
##  <a name="_core_visibility_of_added_records"></a> Sichtbarkeit der hinzugefügte Datensätze  

Wann ist ein hinzugefügte Datensatz für das Recordset sichtbar? Hinzugefügte Datensätze manchmal angezeigt und manchmal sind nicht sichtbar ist, je nach zwei Dinge:  
  
- Welche der Treiber kann.  
  
- Was das Framework nutzen kann.  
  
Wenn der ODBC-Treiber unterstützt die `::SQLSetPos` MFC-ODBC-API-Funktion verwendet die Funktion, um Datensätze hinzufügen. Mit `::SQLSetPos`, werden hinzugefügte Datensätze für alle aktualisierbaren MFC-Recordset sichtbar. Ohne Unterstützung für die Funktion hinzugefügt werden soll, Einträge sind nicht sichtbar, und rufen Sie `Requery` um sie anzuzeigen. Mithilfe von `::SQLSetPos` ist außerdem effizienter.  
  
##  <a name="_core_editing_an_existing_record"></a> Einen vorhandenen Datensatz bearbeiten  

Bearbeiten eines vorhandenen Datensatzes in einem Recordset, scrollen Sie auf den Datensatz, der Aufruf des Recordsets [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Member-Funktion, wenn die Werte der Felddatenmember des neuen Datensatzes und dem Aufrufen der [aktualisieren](../../mfc/reference/crecordset-class.md#update)Memberfunktion versucht, den geänderten Datensatz in der Datenquelle zu schreiben.  
  
Voraussetzung für den Aufruf `Edit`, muss das Recordset aktualisierbar und auf einen Datensatz. Die `CanUpdate` und `IsDeleted` Memberfunktionen können Sie die folgenden Bedingungen zu ermitteln. Außerdem muss der aktuelle Datensatz nicht gelöscht wurde, muss sein und Datensätze im Recordset (beide `IsBOF` und `IsEOF` gibt 0 zurück).  
  
Beim Aufruf `Edit`, wird der Datensatz im Bearbeitungspuffer (der aktuelle Datensatz) gespeichert. Die gespeicherten Werte des Datensatzes werden später verwendet, um festzustellen, ob alle Felder geändert wurden.  
  
Nach dem Aufruf von `Edit`, Bearbeitungspuffer weiterhin den aktuellen Datensatz darstellt, aber ist nun bereit, um Änderungen an den Felddatenmembern zu akzeptieren. Um den Datensatz zu ändern, legen Sie manuell die Werte des Felds Datenmember, die Sie bearbeiten möchten. Anstatt einen tatsächliche Datenwert für ein Feld zu verwenden, können Sie aufrufen `SetFieldNull` an den Wert Null. Aufrufen, um Ihre Änderungen zu übernehmen, `Update`.  
  
> [!TIP]
>  Zum Abrufen von `AddNew` oder `Edit` Modus, rufen `Move` mit dem Parameter *AFX_MOVE_REFRESH*.  
  
Voraussetzung für den Aufruf `Update`, das Recordset darf nicht leer sein und der aktuelle Datensatz nicht gelöscht wurde. `IsBOF`, `IsEOF`, und `IsDeleted` sollten alle gibt 0 zurück.  
  
Beim Aufruf `Update` für den geänderten Datensatz:  
  
- Wenn der ODBC-Treiber unterstützt die `::SQLSetPos` MFC-ODBC-API-Funktion verwendet die Funktion, um den Datensatz in der Datenquelle zu aktualisieren. Mit `::SQLSetPos`, vergleicht der Treiber den Bearbeitungspuffer mit den entsprechenden Datensatz auf dem Server, der den Datensatz auf dem Server aktualisieren, wenn die beiden unterscheiden. Mit `::SQLSetPos`, kann MFC Datensatz effizienter aktualisieren, da es nicht zum Erstellen und eine SQL-Anweisung zu verarbeiten.  
  
     - oder -   
  
- Wenn `::SQLSetPos` nicht verwendet, von MFC bewirkt Folgendes:  
  
    1.  Wenn keine Änderungen wurden `Update` führt keine Aktion aus und gibt 0 zurück.  
  
    2.  Wenn es Änderungen gibt, `Update` erstellt eine SQL- **UPDATE** Anweisung. Die Spalten aufgelistet, die der **UPDATE** Anweisung hängen von den Felddatenmembern, die geändert wurden.  
  
    3.  `Update` übernimmt die Änderungen, führt die **UPDATE** Anweisung – und für die Datenquelle der Datensatz geändert wird, aber kein Commit ausgeführt. wenn eine Transaktion wird ausgeführt (finden Sie unter [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) Informationen zu den Auswirkungen der Transaktions auf des Updates). ODBC bewahrt eine Kopie des Datensatzes, die auch geändert.  
  
    4.  Im Unterschied zu `AddNew`, `Edit` Prozess gespeicherten Datensatz nicht wiederhergestellt. Der bearbeitete Datensatz bleibt als aktuellen Datensatz.  
  
    > [!CAUTION]
    >  Vorbereitung für die Aktualisierung eines Recordsets durch Aufrufen von `Update`, müssen Sie sicherstellen, dass das Recordset alle Spalten, aus denen der Primärschlüssel der Tabelle (oder alle Spalten von beliebigen, eindeutigen Index für die Tabelle oder genügend Spalten zur eindeutigen Identifizierung die Zeile) enthält. In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind. Ohne die erforderlichen Spalten möglicherweise mehrere Datensätze in der Tabelle aktualisiert werden. In diesem Fall das Framework Ausnahmen auslöst, wenn Sie aufrufen `Update`.  
  
    > [!TIP]
    >  Wenn Sie aufrufen `AddNew` oder `Edit` rufen Sie nach dem jeweilige Funktion einmal aufgerufen werden, zuvor jedoch vor dem `Update`, Bearbeitungspuffer wird aktualisiert, mit dem gespeicherten Datensatz, und Ersetzen Sie dabei den neuen oder bearbeiteten Datensatz wird ausgeführt. Dieses Verhalten gibt Ihnen eine Möglichkeit zum Abbrechen einer `AddNew` oder `Edit` und beginnen Sie eine neue: Wenn Sie feststellen, dass die Datensatz-in Bearbeitung sind fehlerhaft ist, rufen Sie einfach `Edit` oder `AddNew` erneut.  
  
##  <a name="_core_deleting_a_record"></a> Löschen eines Datensatzes  

Löschen eines Datensatzes aus einem Recordset umfasst, scrollen Sie zu dem Datensatz und das Aufrufen des Recordsets [löschen](../../mfc/reference/crecordset-class.md#delete) Member-Funktion. Im Gegensatz zu `AddNew` und `Edit`, `Delete` erfordert einen entsprechenden Aufruf von keine `Update`.  
  
Voraussetzung für den Aufruf `Delete`, muss das Recordset aktualisierbar sein und muss auf einen Datensatz sein. Die `CanUpdate`, `IsBOF`, `IsEOF`, und `IsDeleted` Memberfunktionen können Sie die folgenden Bedingungen zu ermitteln.  
  
Beim Aufruf `Delete`:  
  
- Wenn der ODBC-Treiber unterstützt die `::SQLSetPos` MFC-ODBC-API-Funktion verwendet die Funktion, um den Datensatz in der Datenquelle zu löschen. Mithilfe von `::SQLSetPos` ist in der Regel effizienter als die Verwendung von SQL.  
  
     - oder -   
  
- Wenn `::SQLSetPos` nicht verwendet, von MFC bewirkt Folgendes:  
  
    1.  Der aktuelle Datensatz im Bearbeitungspuffer werden nicht gesichert, wie in `AddNew` und `Edit`.  
  
    2.  `Delete` erstellt eine SQL- **löschen** -Anweisung, die den Datensatz wird entfernt.  
  
         Der aktuelle Datensatz im Bearbeitungspuffer befindet sich nicht als in `AddNew` und `Edit`.  
  
    3.  `Delete` Führt einen Commit für das Löschen, führt die **löschen** Anweisung. Der Datensatz ist für die Datenquelle als gelöscht markiert und, wenn der Datensatz mit einer Momentaufnahme in ODBC ist.  
  
    4.  Werte des gelöschten Datensatzes befinden sich noch in die Felddatenmember der Recordset, sondern die Felddatenmembern gekennzeichnet Null und des Recordsets `IsDeleted` Memberfunktion gibt einen Wert ungleich NULL zurück.  
  
    > [!NOTE]
    >  Nach dem Löschen eines Datensatzes, sollten Sie einen Bildlauf zu einem anderen Datensatz im Bearbeitungspuffer des neuen Datensatzes Daten auffüllen durchführen. Es ist ein Fehler Aufrufen `Delete` erneut oder Aufrufen `Edit`.  
  
Weitere Informationen zu den SQL-Anweisungen, die Updatevorgänge verwendet, finden Sie unter [SQL](../../data/odbc/sql.md).  
  
## <a name="see-also"></a>Siehe auch  

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Weitere Informationen zu Aktualisierungen (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)