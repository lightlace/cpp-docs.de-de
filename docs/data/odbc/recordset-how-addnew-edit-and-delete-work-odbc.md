---
title: "Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddNew-Methode"
  - "Daten in Recordsets [C++]"
  - "ODBC-Recordsets [C++], Hinzufügen von Datensätzen"
  - "ODBC-Recordsets [C++], Löschen von Datensätzen"
  - "ODBC-Recordsets [C++], Bearbeiten von Datensätzen"
  - "Datensatzbearbeitung [C++], In Recordsets"
  - "Datensätze [C++], Hinzufügen"
  - "Datensätze [C++], Löschen in Recordsets"
  - "Datensätze [C++], Bearbeiten"
  - "Datensätze [C++], Aktualisieren"
  - "Recordsets [C++], Hinzufügen von Datensätzen"
  - "Recordsets [C++], Löschen von Datensätzen"
  - "Recordsets [C++], Bearbeiten von Datensätzen"
  - "Recordsets [C++], Aktualisieren"
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie die `AddNew`\-Memberfunktion, **Edit**\-Memberfunktion und **Delete**\-Memberfunktion der `CRecordset`\-Klasse funktionieren.  Folgende Themen werden behandelt:  
  
-   [Hinzufügen von Datensätzen](#_core_adding_a_record)  
  
-   [Sichtbarkeit hinzugefügter Datensätze](#_core_visibility_of_added_records)  
  
-   [Bearbeiten von Datensätzen](#_core_editing_an_existing_record)  
  
-   [Löschen von Datensätzen](#_core_deleting_a_record)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Ergänzend sollten Sie das Thema [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md) lesen, in dem die entsprechende Rolle von RFX bei Aktualisierungsoperationen beschrieben wird.  
  
##  <a name="_core_adding_a_record"></a> Hinzufügen eines Datensatzes  
 Um einen neuen Datensatz zu einem Recordset hinzuzufügen, rufen Sie die [AddNew](../Topic/CRecordset::AddNew.md)\-Memberfunktion des Recordsets auf, tragen Werte in die Felddatenmember des neuen Datensatzes ein und rufen die [Update](../Topic/CRecordset::Update.md)\-Memberfunktion auf, um den Datensatz in die Datenquelle zu schreiben.  
  
 Voraussetzung für den Aufruf von `AddNew` ist, dass das Recordset nicht als schreibgeschützt geöffnet wurde.  Mit der `CanUpdate`\-Memberfunktion und der `CanAppend`\-Memberfunktion können Sie dies überprüfen.  
  
 Wenn Sie `AddNew` aufrufen:  
  
-   wird der Datensatz aus dem Bearbeitungspuffer gespeichert, damit sein Inhalt wiederhergestellt werden kann, falls die Operation abgebrochen wird;  
  
-   Die Felddatenmember werden gekennzeichnet, damit daran vorgenommene Änderungen später festgestellt werden können.  Die Felddatenmember werden außerdem als "clean" \(bereinigt, unverändert\) markiert und auf NULL gesetzt.  
  
 Nach dem Aufruf von `AddNew` enthält der Bearbeitungspuffer einen neuen, leeren Datensatz, den Sie mit Werten füllen können.  Stellen Sie hierzu von Hand die Werte durch Zuweisungen ein.  Statt einen Datenwert für ein Feld anzugeben, können Sie auch `SetFieldNull` aufrufen und für das Feld so den Wert NULL festlegen.  
  
 Um die Änderungen zu bestätigen, rufen Sie **Update** auf.  Wenn Sie für den neuen Datensatz **Update** aufrufen, geschieht Folgendes:  
  
-   Falls der ODBC\-Treiber die ODBC\-API\-Funktion **::SQLSetPos** unterstützt, fügt MFC mit dieser Funktion den Datensatz der Datenquelle hinzu.  Mit **::SQLSetPos** kann MFC einen Datensatz effizienter hinzufügen, da dann keine SQL\-Anweisung zusammengestellt und ausgeführt werden muss.  
  
-   Falls **::SQLSetPos** nicht zur Verfügung steht, verfährt MFC wie folgt:  
  
    1.  Falls keine Änderungen entdeckt werden, tut **Update** nichts und gibt das Ergebnis 0 zurück.  
  
    2.  Falls es Änderungen gibt, konstruiert **Update** eine SQL\-**INSERT**\-Anweisung.  Alle Spalten, deren zugeordnete Felddatenmember als verändert markiert sind, werden in der **INSERT**\-Anweisung aufgelistet.  Um die Aufnahme einer Spalte zu erzwingen, rufen Sie die [SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md)\-Memberfunktion auf:  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **Update** führt für den neuen Datensatz einen Commit aus, d. h., die **INSERT**\-Anweisung wird ausgeführt und der Datensatz an die Tabelle in der Datenquelle übergeben \(und an das Recordset, falls es sich nicht um einee Momentaufnahme handelt\). Dies gilt jedoch nur, sofern derzeit keine Transaktion durchgeführt wird.  
  
    4.  Der gespeicherte Datensatz wird im Bearbeitungspuffer wiederhergestellt.  Der Datensatz, der vor dem `AddNew`\-Aufruf der aktuelle Datensatz war, wird wieder aktuell, unabhängig davon, ob die **INSERT**\-Anweisung erfolgreich ausgeführt wurde oder nicht.  
  
    > [!TIP]
    >  Für die vollständige Steuerung eines neuen Datensatzes sollten Sie folgende Methode wählen: Legen Sie die Werte aller Felder fest, die Werte enthalten sollen. Legen Sie dann die Felder explizit fest, die NULL enthalten, indem Sie `SetFieldNull` mit einem Zeiger auf das Feld und dem **TRUE**\-Parameter \(Standardwert\) aufrufen.  Falls Sie nicht möchten, dass ein Feld in die Datenquelle geschrieben wird, rufen Sie `SetFieldDirty` mit einem Zeiger auf das Feld und den **FALSE**\-Parameter auf und ändern den Feldwert nicht.  Rufen Sie `IsFieldNullable` auf, um festzustellen, ob ein Feld den Wert NULL haben darf.  
  
    > [!TIP]
    >  Um festzustellen, ob sich die Werte von Datenmembern des Recordsets geändert haben, verwendet MFC einen **PSEUDO\_NULL**\-Wert. Einen solchen Wert gibt es für jeden Datentyp, den Sie in einem Recordset speichern können.  Falls Sie für ein Feld explizit den **PSEUDO\_NULL**\-Wert festlegen müssen und das Feld bereits mit NULL gekennzeichnet ist, müssen Sie außerdem `SetFieldNull` aufrufen und dabei als ersten Parameter die Adresse des Felds und als zweiten Parameter **FALSE** angeben.  
  
##  <a name="_core_visibility_of_added_records"></a> Sichtbarkeit hinzugefügter Datensätze  
 Wann wird ein hinzugefügter Datensatz für das Recordset sichtbar?  Zwei Faktoren bestimmen, ob ein hinzugefügter Datensatz angezeigt wird:  
  
-   von den Fähigkeiten des Treibers;  
  
-   von den Möglichkeiten, die durch das Framework genutzt werden können.  
  
 Falls der ODBC\-Treiber die **::SQLSetPos**\-ODBC\-API\-Funktion unterstützt, fügt MFC mit dieser Funktion neue Datensätze hinzu.  Bei Verwendung von **::SQLSetPos** werden hinzugefügte Datensätze für jedes aktualisierbare MFC\-Recordset sichtbar.  Wenn diese Funktion nicht unterstützt wird, werden hinzugefügte Datensätze nicht angezeigt. In diesem Fall müssen Sie **Requery** aufrufen, um die hinzugefügten Datensätze anzuzeigen.  Der Einsatz von **::SQLSetPos** ist außerdem effizienter.  
  
##  <a name="_core_editing_an_existing_record"></a> Bearbeiten eines vorhandenen Datensatzes  
 Um einen vorhandenen Datensatz eines Recordsets zu bearbeiten, scrollen Sie zum Datensatz, rufen die [Edit](../Topic/CRecordset::Edit.md)\-Memberfunktion des Recordsets auf, legen Werte für die Felddatenmember des neuen Recordsets fest und rufen die [Update](../Topic/CRecordset::Update.md)\-Memberfunktion auf, um den geänderten Datensatz in die Datenquelle zu schreiben.  
  
 Voraussetzung für den Aufruf von **Edit** ist, dass das Recordset aktualisierbar und auf einen Datensatz eingestellt ist.  Mit der `CanUpdate`\-Memberfunktion und der `IsDeleted`\-Memberfunktion können Sie dies überprüfen.  Außerdem darf der aktuelle Datensatz nicht gelöscht worden sein und das Recordset muss Datensätze enthalten \(sowohl `IsBOF` als auch `IsEOF` geben 0 zurück\).  
  
 Wenn Sie **Edit** aufrufen, wird der Datensatz aus dem Bearbeitungspuffer \(der aktuelle Datensatz\) gespeichert.  Die gespeicherten Werte des Datensatzes werden später dazu verwendet, festzustellen, ob sich die Felder geändert haben.  
  
 Nach dem Aufruf von **Edit** repräsentiert der Bearbeitungspuffer weiterhin den aktuellen Datensatz, ist jetzt aber bereit, Änderungen der Felddatenmember zu verarbeiten.  Um den Datensatz zu ändern, weisen Sie von Hand allen Felddatenmembern, die Sie bearbeiten möchten, neue Werte zu.  Statt einen Datenwert für ein Feld anzugeben, können Sie auch `SetFieldNull` aufrufen und für das Feld so den Wert NULL festlegen.  Um die Änderungen zu bestätigen, rufen Sie **Update** auf.  
  
> [!TIP]
>  Um den `AddNew`\-Modus oder den **Edit**\-Modus zu verlassen, können Sie **Move** mit dem Parameter **AFX\_MOVE\_REFRESH** aufrufen.  
  
 Voraussetzung für den Aufruf von **Update** ist, dass das Recordset nicht leer ist und dass der aktuelle Datensatz nicht gelöscht wurde.  `IsBOF`, `IsEOF` und `IsDeleted` müssen alle den Wert 0 \(null\) zurückgeben.  
  
 Wenn Sie für den geänderten Datensatz **Update** aufrufen, geschieht Folgendes:  
  
-   Falls der ODBC\-Treiber die **::SQLSetPos**\-ODBC\-API\-Funktion unterstützt, aktualisiert MFC den Datensatz in der Datenquelle mit dieser Funktion.  Beim Aufruf von **::SQLSetPos** vergleicht der Treiber den Bearbeitungspuffer mit dem entsprechenden Datensatz auf dem Server und aktualisiert den Datensatz auf dem Server, falls er Unterschiede feststellt.  Mit **::SQLSetPos** kann MFC einen Datensatz effizienter aktualisieren, da dann keine SQL\-Anweisung zusammengestellt und ausgeführt werden muss.  
  
     \- oder \-  
  
-   Falls **::SQLSetPos** nicht zur Verfügung steht, verfährt MFC wie folgt:  
  
    1.  Falls keine Änderungen entdeckt werden, führt **Update** keinen Vorgang durch und gibt 0 \(null\) zurück.  
  
    2.  Falls es Änderungen gibt, konstruiert **Update** eine SQL\-**UPDATE**\-Anweisung.  Welche Spalten in der **UPDATE**\-Anweisung aufgeführt sind, hängt davon ab, welche Felddatenmember geändert wurden.  
  
    3.  **Update** führt einen Commit für die Änderungen aus, d. h., die **UPDATE**\-Anweisung wird ausgeführt und der Datensatz in der Datenquelle geändert. Es wird jedoch kein Commit ausgeführt, während eine Transaktion aktiv ist. \(Weitere Informationen über die Auswirkungen einer Transaktion auf eine Aktualisierung finden Sie unter [Transaktion: Ausführen einer Transaktion in einem Recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).\)  ODBC bewahrt eine Kopie des Datensatzes auf, die ebenfalls geändert wird.  
  
    4.  Im Unterschied zu `AddNew` wird beim **Edit**\-Prozess der vorher gespeicherte Datensatz nicht wiederhergestellt.  Der bearbeitete Datensatz bleibt der aktuelle Datensatz.  
  
    > [!CAUTION]
    >  Wenn Sie durch Aufruf von **Update** die Aktualisierung eines Recordsets vorbereiten, müssen Sie sicherstellen, dass das Recordset alle Spalten enthält, aus denen sich der Primärschlüssel der Tabelle zusammensetzt \(oder alle Spalten eines eindeutigen Tabellenindex bzw. genügend Spalten zur eindeutigen Identifizierung der Zeile\).  In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind.  Wenn nicht sämtliche benötigten Spalten zur Verfügung stehen, werden möglicherweise mehrere Datensätze in der Tabelle aktualisiert.  In diesem Fall löst das Framework beim Aufruf von **Update** eine Ausnahme aus.  
  
    > [!TIP]
    >  Wenn Sie `AddNew` oder **Edit** aufrufen, nachdem Sie die jeweilige Funktion bereits einmal aufgerufen haben, aber noch bevor Sie **Update** aufrufen, wird der Bearbeitungspuffer mit dem gespeicherten Datensatz aktualisiert. Der gerade hinzugefügte oder bearbeitete Datensatz wird ersetzt.  Dieses Verhalten gibt Ihnen die Möglichkeit, `AddNew` oder **Edit** abzubrechen und den jeweiligen Prozess neu zu beginnen: Sollten Sie feststellen, dass der bearbeitete Datensatz fehlerhaft ist, rufen Sie einfach erneut `AddNew` oder **Edit** auf.  
  
##  <a name="_core_deleting_a_record"></a> Löschen eines Datensatzes  
 Um einen Datensatz aus einem Recordset zu löschen, scrollen Sie zu dem Datensatz und rufen die [Delete](../Topic/CRecordset::Delete.md)\-Memberfunktion des Recordsets auf.  Im Unterschied zu `AddNew` und **Edit** wird für **Delete** kein Aufruf von **Update** benötigt.  
  
 Voraussetzung für den Aufruf von **Delete** ist, dass das Recordset aktualisierbar und auf einen Datensatz eingestellt ist.  Mit den Memberfunktionen `CanUpdate`, `IsBOF`, `IsEOF` und `IsDeleted` können Sie dies überprüfen.  
  
 Wenn Sie **Delete** aufrufen, geschieht Folgendes:  
  
-   Falls der ODBC\-Treiber die **::SQLSetPos**\-ODBC\-API\-Funktion unterstützt, löscht MFC mit dieser Funktion den Datensatz aus der Datenquelle.  Der Einsatz von **::SQLSetPos** ist gewöhnlich effizienter als der Einsatz von SQL.  
  
     \- oder \-  
  
-   Falls **::SQLSetPos** nicht zur Verfügung steht, verfährt MFC wie folgt:  
  
    1.  Der aktuelle Datensatz im Bearbeitungspuffer wird im Unterschied zu `AddNew` und **Edit** nicht gesichert.  
  
    2.  **Delete** konstruiert eine SQL\-**DELETE**\-Anweisung zum Löschen des Datensatzes.  
  
         Der aktuelle Datensatz im Bearbeitungspuffer wird im Unterschied zu `AddNew` und **Edit** nicht gespeichert.  
  
    3.  **Delete** bestätigt den Löschvorgang, das heißt, die **DELETE**\-Anweisung wird ausgeführt.  Der Datensatz wird in der Datenquelle als gelöscht markiert. Falls der Datensatz eine Momentaufnahme ist, wird er auch in ODBC als gelöscht markiert.  
  
    4.  Die Werte des gelöschten Datensatzes befinden sich noch in den Felddatenmembern des Recordsets, die Felddatenmember werden aber mit NULL markiert, und die `IsDeleted`\-Memberfunktion des Recordsets gibt einen Wert ungleich 0 \(null\) zurück.  
  
    > [!NOTE]
    >  Nach dem Löschen eines Datensatzes müssen Sie zu einem anderen Datensatz wechseln, um den Bearbeitungspuffer mit den Daten eines neuen Datensatzes zu füllen.  Der erneute Aufruf von **Delete** oder der Aufruf von **Edit** ruft einen Fehler hervor.  
  
 Weitere Informationen über die SQL\-Anweisungen, die bei Aktualisierungsoperationen eingesetzt werden, finden Sie unter [SQL](../../data/odbc/sql.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Weitere Informationen zu Aktualisierungen \(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)