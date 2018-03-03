---
title: 'Recordset: AddNew, Edit und Delete Funktionsweise (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dbbf224797bd7d2eed2b085a6a7dd8eb1865de1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie die `AddNew`, **bearbeiten**, und **löschen** Memberfunktionen der Klasse `CRecordset` arbeiten. Zu den behandelten Themen gehören:  
  
-   [Hinzufügen von Datensätzen](#_core_adding_a_record)  
  
-   [Sichtbarkeit der hinzugefügte Datensätze](#_core_visibility_of_added_records)  
  
-   [Bearbeiten von Datensätzen](#_core_editing_an_existing_record)  
  
-   [Löschen von Datensätzen](#_core_deleting_a_record)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Als Ergänzung, möchten Sie möglicherweise lesen [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md), das die entsprechende Rolle von RFX in Aktualisierungsvorgängen beschreibt.  
  
##  <a name="_core_adding_a_record"></a>Hinzufügen eines Datensatzes  

 Hinzufügen eines neuen Datensatzes zu einem Recordset beinhaltet den Aufruf des Recordsets [AddNew](../../mfc/reference/crecordset-class.md#addnew) Memberfunktion, die Werte der Felddatenmember des neuen Datensatzes festzulegen und das Aufrufen der [Update](../../mfc/reference/crecordset-class.md#update) Memberfunktion schreiben der Datensatz mit der Datenquelle.  
  
 Als Voraussetzung für den Aufruf von `AddNew`, das Recordset muss nicht geöffnet wurden als schreibgeschützt. Die `CanUpdate` und `CanAppend` Memberfunktionen können Sie diese Bedingungen zu bestimmen.  
  
 Beim Aufruf `AddNew`:  
  
-   Der Datensatz im Bearbeitungspuffer wird gespeichert, damit dessen Inhalt wiederhergestellt werden können, wenn der Vorgang abgebrochen wird.  
  
-   Die Felddatenmember werden gekennzeichnet, daher ist es möglich, Änderungen in ihnen später zu erkennen. Die Felddaten Elemente werden ebenfalls markiert bereinigen (unverändert) und auf Null gesetzt.  
  
 Nach dem Aufruf `AddNew`, der Bearbeitungspuffer einen neuen, leeren Datensatz, mit Werten gefüllt werden soll. Zu diesem Zweck legen Sie die Werte manuell durch zuweisen. Anstatt einen Wert des tatsächlichen Daten für ein Feld angeben, rufen Sie `SetFieldNull` auf den Wert Null festlegen.  
  
 Um die Änderungen zu speichern, rufen Sie **Update**. Beim Aufruf **Update** für den neuen Eintrag:  
  
-   Wenn der ODBC-Treiber unterstützt die **:: SQLSetPos** MFC-ODBC-API-Funktion verwendet die Funktion, um den Datensatz in der Datenquelle hinzuzufügen. Mit **:: SQLSetPos**, kann MFC einen Datensatz effizienter hinzufügen, da sie nicht zum Erstellen und verarbeiten eine SQL-Anweisung verfügt.  
  
-   Wenn **:: SQLSetPos** nicht verwendet, MFC bewirkt Folgendes:  
  
    1.  Wenn keine Änderungen erkannt werden, **Update** wird keine Aktion ausgeführt, und gibt 0 zurück.  
  
    2.  Bei Änderungen, **Update** erstellt eine SQL- **einfügen** Anweisung. Die Spalten, die durch alle Felddatenmember dargestellt sind aufgeführt, der **einfügen** Anweisung. Um eine Spalte enthalten, zu erzwingen, rufen Sie die [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) Memberfunktion:  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **Update** führt einen Commit für den neuen Eintrag – die **einfügen** Anweisung ausgeführt wird und der Datensatz ist bestrebt, die Tabelle auf die Datenquelle (und auf das Recordset, wenn es sich nicht um eine Momentaufnahme handelt), es sei denn, eine Transaktion ausgeführt wird.  
  
    4.  Gespeicherte Datensatz wird im Bearbeitungspuffer wiederhergestellt. Der Datensatz, der vor dem aktuellen wurde die `AddNew` Aufruf ist der aktuelle Vorgang unabhängig davon, ob die **einfügen** -Anweisung erfolgreich ausgeführt wurde.  
  
    > [!TIP]
    >  Für die vollständige Steuerung eines neuen Datensatzes, nehmen Sie die folgende Weise: Legen Sie die Werte der Felder, die Werte aufweisen, und legen Sie dann explizit alle Felder, die durch den Aufruf Null bleibt, werden `SetFieldNull` mit einem Zeiger auf das Feld und der Parameter **"true"**  (Standard). Stellen Sie sicher, dass ein Feld mit der Datenquelle Aufruf nicht geschrieben werden sollen `SetFieldDirty` mit einem Zeiger auf das Feld und der Parameter **"false"**, und ändern Sie den Wert des Felds. Um zu bestimmen, ob ein Feld NULL zulässig ist, rufen Sie `IsFieldNullable`.  
  
    > [!TIP]
    >  Zum Erkennen von Recordset geändert verwendet MFC eine **PSEUDO_NULL** Wert für jeden Datentyp, der in einem Recordset gespeichert werden können. Wenn Sie ein Feld explizit, um festlegen müssen die **PSEUDO_NULL** Wert und das Feld erfolgt bereits Null gekennzeichnet sein müssen Sie auch aufrufen `SetFieldNull`, übergeben die Adresse des Felds in den ersten Parameter und **"false"**im zweiten Parameter.  
  
##  <a name="_core_visibility_of_added_records"></a>Sichtbarkeit der hinzugefügte Datensätze  
 Wenn ein hinzugefügter Datensatz für das Recordset sichtbar ist? Hinzugefügte Datensätze manchmal angezeigt und in einigen Fällen sind nicht sichtbar ist, je nach zwei Dinge:  
  
-   Welche des Treibers ist.  
  
-   Was das Framework nutzen kann.  
  
 Wenn der ODBC-Treiber unterstützt die **:: SQLSetPos** MFC-ODBC-API-Funktion verwendet die Funktion zum Hinzufügen von Einträgen. Mit **:: SQLSetPos**, werden hinzugefügte Datensätze für jedes aktualisierbare MFC-Recordset sichtbar. Hinzugefügt, ohne dass die Unterstützung für die Funktion, Datensätze sind nicht sichtbar, und rufen Sie **Requery** um sie anzuzeigen. Mit **:: SQLSetPos** darüber hinaus ist effizienter.  
  
##  <a name="_core_editing_an_existing_record"></a>Einen vorhandenen Datensatz bearbeiten  
 Bearbeiten einen vorhandenen Datensatz in einem Recordset, scrollen Sie zum Datensatz, rufen des Recordsets [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Memberfunktion, die Werte der Felddatenmember des neuen Datensatzes festzulegen und das Aufrufen der [aktualisieren](../../mfc/reference/crecordset-class.md#update)Memberfunktion versucht, den geänderten Datensatz in der Datenquelle zu schreiben.  
  
 Als Voraussetzung für den Aufruf von **bearbeiten**, muss das Recordset aktualisierbar und auf einen Datensatz. Die `CanUpdate` und `IsDeleted` Memberfunktionen können Sie diese Bedingungen zu bestimmen. Außerdem muss der aktuelle Datensatz nicht gelöscht wurde, und es muss Datensätze im Recordset (beide `IsBOF` und `IsEOF` geben 0 zurück).  
  
 Beim Aufruf **bearbeiten**, den Datensatz im Bearbeitungspuffer (der aktuelle Datensatz) gespeichert ist. Die gespeicherten Datensatz Werte werden später verwendet, um festzustellen, ob alle Felder geändert wurden.  
  
 Nach dem Aufruf **bearbeiten**, Bearbeitungspuffer immer noch den aktuellen Datensatz darstellt, jedoch ist jetzt bereit zur Annahme von Änderungen an den Felddatenmembern. Um den Datensatz zu ändern, legen Sie manuell die Werte der alle Felddatenmember, die Sie bearbeiten möchten. Anstatt einen Wert des tatsächlichen Daten für ein Feld angeben, rufen Sie `SetFieldNull` auf den Wert Null festlegen. Um die Änderungen zu speichern, rufen **Update**.  
  
> [!TIP]
>  Zum Abrufen von `AddNew` oder **bearbeiten** Modus, rufen **verschieben** mit dem Parameter **AFX_MOVE_REFRESH**.  
  
 Als Voraussetzung für den Aufruf von **Update**, das Recordset darf nicht leer sein und der aktuelle Datensatz nicht gelöscht wurde. `IsBOF`, `IsEOF`, und `IsDeleted` sollten alle geben 0 zurück.  
  
 Beim Aufruf **Update** für den geänderten Datensatz:  
  
-   Wenn der ODBC-Treiber unterstützt die **:: SQLSetPos** MFC-ODBC-API-Funktion verwendet die Funktion, um den Datensatz in der Datenquelle zu aktualisieren. Mit **:: SQLSetPos**, vergleicht der Treiber den Bearbeitungspuffer mit den entsprechenden Datensatz auf dem Server, aktualisieren Sie den Datensatz auf dem Server aus, wenn die beiden unterscheiden. Mit **:: SQLSetPos**, kann MFC einen Datensatz effizienter aktualisieren, da sie nicht zum Erstellen und verarbeiten eine SQL-Anweisung verfügt.  
  
     - oder -   
  
-   Wenn **:: SQLSetPos** nicht verwendet, MFC bewirkt Folgendes:  
  
    1.  Wenn keine Änderungen vorgenommen wurden **Update** wird keine Aktion ausgeführt, und gibt 0 zurück.  
  
    2.  Bei Änderungen, **Update** erstellt eine SQL- **UPDATE** Anweisung. Die Spalten aufgeführt, die der **UPDATE** Anweisung basieren auf den Felddatenmembern, die geändert wurden.  
  
    3.  **Update** einen Commit der Änderungen – führt die **UPDATE** Anweisung – und der Datensatz in der Datenquelle geändert wird, jedoch kein Commit ausgeführt, wenn eine Transaktion ist, läuft (finden Sie unter [Transaktion: Ausführen einer Transaktion in ein Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) Informationen zu den Auswirkungen der Transaktions auf des Updates). ODBC wird eine Kopie des Datensatzes, die ebenfalls geändert wird.  
  
    4.  Im Gegensatz zu den Prozess für `AddNew`, **bearbeiten** Prozess gespeicherten Datensatz nicht wiederhergestellt. Der bearbeitete Datensatz wird so lange als den aktuellen Datensatz.  
  
    > [!CAUTION]
    >  Vorbereitung für die Aktualisierung eines Recordsets durch Aufrufen von **aktualisieren**, achten Sie darauf, dass das Recordset alle Spalten, aus denen der Primärschlüssel der Tabelle enthält (oder alle Spalten von jedem eindeutigen index für die Tabelle oder genügend Spalten eindeutig Identifizieren Sie die Zeile). In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind. Ohne die erforderlichen Spalten möglicherweise mehrere Datensätze in der Tabelle aktualisiert werden. In diesem Fall löst das Framework Ausnahmen aus, wenn Sie aufrufen **Update**.  
  
    > [!TIP]
    >  Beim Aufrufen `AddNew` oder **bearbeiten** nach müssen entweder die Funktion aufgerufen, zuvor jedoch vor dem Aufruf **Update**, Bearbeitungspuffer wird aktualisiert, mit dem gespeicherten Datensatz, und Ersetzen Sie dabei den neuen oder bearbeiteten Datensatz in Fortschritt. Dieses Verhalten bietet Ihnen eine Möglichkeit zum Abbrechen einer `AddNew` oder **bearbeiten** und neu zu beginnen: Wenn Sie feststellen, dass der Datensatz in Bearbeitung fehlerhaft ist, rufen Sie einfach **bearbeiten** oder `AddNew` erneut aus.  
  
##  <a name="_core_deleting_a_record"></a>Löschen eines Datensatzes  
 Löschen eines Datensatzes aus einem Recordset umfasst, scrollen Sie zu dem Datensatz und rufen des Recordsets [löschen](../../mfc/reference/crecordset-class.md#delete) Memberfunktion. Im Gegensatz zu `AddNew` und **bearbeiten**, **löschen** erfordert keinen übereinstimmenden Aufruf von **Update**.  
  
 Als Voraussetzung für den Aufruf von **löschen**, muss das Recordset aktualisierbar sein und muss es sich um einen Datensatz handeln. Die `CanUpdate`, `IsBOF`, `IsEOF`, und `IsDeleted` Memberfunktionen können Sie diese Bedingungen zu bestimmen.  
  
 Beim Aufruf **löschen**:  
  
-   Wenn der ODBC-Treiber unterstützt die **:: SQLSetPos** MFC-ODBC-API-Funktion verwendet die Funktion zum Löschen des Datensatzes für die Datenquelle. Mit **:: SQLSetPos** ist normalerweise effizienter als die Verwendung von SQL.  
  
     - oder -   
  
-   Wenn **:: SQLSetPos** nicht verwendet, MFC bewirkt Folgendes:  
  
    1.  Der aktuelle Datensatz im Bearbeitungspuffer werden nicht gesichert, wie in `AddNew` und **bearbeiten**.  
  
    2.  **Löschen Sie** erstellt eine SQL- **löschen** -Anweisung, die den Datensatz entfernt.  
  
         Der aktuelle Datensatz im Bearbeitungspuffer wird nicht gespeichert, wie in `AddNew` und **bearbeiten**.  
  
    3.  **Löschen Sie** führt einen Commit für die Löschung – führt die **löschen** Anweisung. Der Datensatz ist für die Datenquelle als gelöscht markiert und ist der Datensatz eine Momentaufnahme, in ODBC.  
  
    4.  Der gelöschte Datensatz Werte sind immer noch in den Felddatenmembern eines Recordset, aber die Felddatenmembern Transaktionen markiert, Null und des Recordsets `IsDeleted` Memberfunktion gibt einen Wert ungleich NULL zurück.  
  
    > [!NOTE]
    >  Nach dem Löschen eines Datensatzes, sollten Sie einen Bildlauf zu einem anderen Datensatz Auffüllen mit Daten des neuen Datensatzes Bearbeitungspuffer durchführen. Es ist ein Fehler auf, rufen Sie **löschen** erneut, oder rufen **bearbeiten**.  
  
 Informationen zu den SQL-Anweisungen, die in Update-Vorgänge verwendet, finden Sie unter [SQL](../../data/odbc/sql.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Weitere Informationen zu Aktualisierungen (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)