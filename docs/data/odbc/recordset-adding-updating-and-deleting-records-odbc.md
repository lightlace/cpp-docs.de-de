---
title: "Recordset: Hinzuf&#252;gen, Aktualisieren und L&#246;schen von Datens&#228;tzen (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddNew-Methode"
  - "Daten in Recordsets [C++]"
  - "ODBC-Recordsets [C++], Hinzufügen von Datensätzen"
  - "ODBC-Recordsets [C++], Löschen von Datensätzen"
  - "ODBC-Recordsets [C++], Bearbeiten von Datensätzen"
  - "Datensatzbearbeitung [C++]"
  - "Datensatzbearbeitung [C++], In Recordsets"
  - "Datensätze [C++], Hinzufügen"
  - "Datensätze [C++], Löschen"
  - "Datensätze [C++], Bearbeiten"
  - "Datensätze [C++], Aktualisieren"
  - "Recordsets [C++], Hinzufügen von Datensätzen"
  - "Recordsets [C++], Löschen von Datensätzen"
  - "Recordsets [C++], Bearbeiten von Datensätzen"
  - "Recordsets [C++], Aktualisieren"
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Recordset: Hinzuf&#252;gen, Aktualisieren und L&#246;schen von Datens&#228;tzen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
> [!NOTE]
>  Sie können jetzt Datensätze in einer Sammeloperation effizienter hinzufügen.  Weitere Informationen finden Sie unter [Recordset: Hinzufügen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Mit aktualisierbaren Momentaufnahmen und Dynasets können Sie Datensätze hinzufügen, bearbeiten \(aktualisieren\) und löschen.  In diesem Thema wird Folgendes erläutert:  
  
-   [Wie Sie entscheiden, ob ein Recordset aktualisierbar ist](#_core_determining_whether_your_recordset_is_updatable).  
  
-   [Wie Sie einen neuen Datensatz hinzufügen](#_core_adding_a_record_to_a_recordset).  
  
-   [Wie Sie einen vorhandenen Datensatz bearbeiten](#_core_editing_a_record_in_a_recordset).  
  
-   [Wie Sie einen Datensatz löschen](#_core_deleting_a_record_from_a_recordset).  
  
 Weitere Informationen darüber, wie Aktualisierungen durchgeführt werden und auf welche Weise die vorgenommenen Aktualisierungen bei anderen Benutzern angezeigt werden, finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  Wenn Sie einen Datensatz hinzufügen, ändern oder löschen, ändert das Recordset die Datenquelle normalerweise sofort.  Alternativ können Sie Gruppen zusammengehöriger Aktualisierungen zu Transaktionen zusammenfassen.  Während einer Transaktion werden die Aktualisierungen nicht vor Bestätigung der Transaktion endgültig.  So können Sie die Änderungen zurücksetzen.  Informationen über Transaktionen finden Sie unter [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
 In der folgenden Tabelle ist zusammengefasst, welche Optionen für Recordsets zur Verfügung stehen mit den jeweiligen Aktualisierungsmerkmalen.  
  
### Lese\- und Aktualisierungsoptionen von Recordsets  
  
|Typ|Read|Datensatz bearbeiten|Datensatz löschen|Neue hinzufügen \(anhängen\)|  
|---------|----------|--------------------------|-----------------------|----------------------------------|  
|Schreibgeschützt|J|N|N|N|  
|Nur erweiterbar|J|N|N|J|  
|Ohne Einschränkungen aktualisierbar|J|J|J|J|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> Ermitteln, ob das Recordset aktualisierbar ist  
 Ein Recordset\-Objekt ist aktualisierbar, wenn die Datenquelle aktualisierbar ist und Sie das Recordset als aktualisierbar geöffnet haben.  Außerdem hängt die Aktualisierbarkeit von der verwendeten SQL\-Anweisung ab, von den Fähigkeiten des ODBC\-Treibers und davon, ob die ODBC\-Cursorbibliothek geladen ist.  Sie können ein schreibgeschütztes Recordset oder eine schreibgeschützte Datenquelle nicht aktualisieren.  
  
#### So stellen Sie fest, ob das Recordset aktualisierbar ist  
  
1.  Rufen Sie die [CanUpdate](../Topic/CRecordset::CanUpdate.md)\-Memberfunktion des Recordset\-Objekts auf.  
  
     `CanUpdate` gibt einen Wert ungleich 0 \(null\) zurück, falls das Recordset aktualisierbar ist.  
  
 Standardmäßig sind Recordsets ohne Einschränkungen aktualisierbar \(Sie können die Operationen `AddNew`, **Edit** und **Delete** ausführen\).  Sie können aktualisierbare Recordsets aber auch mit der [appendOnly](../Topic/CRecordset::Open.md)\-Option öffnen.  Zu einem auf diese Weise geöffneten Recordset können Sie lediglich mit `AddNew` neue Datensätze hinzufügen.  Sie können keine vorhandenen Datensätze bearbeiten oder löschen.  Sie können testen, ob ein Recordset nur zum Anhängen geöffnet ist, indem Sie die [CanAppend](../Topic/CRecordset::CanAppend.md)\-Memberfunktion aufrufen.  `CanAppend` gibt einen Wert ungleich 0 \(null\) zurück, wenn das Recordset vollständig aktualisierbar ist oder nur zum Anhängen geöffnet ist.  
  
 Der folgende Codeausschnitt zeigt, wie Sie `CanUpdate` in einem Recordset\-Objekt mit dem Namen `rsStudentSet` aufrufen können:  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  Wenn Sie durch Aufruf von **Update** die Aktualisierung eines Recordsets vorbereiten, müssen Sie sicherstellen, dass das Recordset alle Spalten umfasst, aus denen sich der Primärschlüssel der Tabelle zusammensetzt \(oder sämtliche Spalten eines beliebigen, eindeutigen Index für die Tabelle\).  In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind.  Wenn nicht sämtliche benötigten Spalten zur Verfügung stehen, werden möglicherweise mehrere Datensätze in der Tabelle aktualisiert. Hierdurch kann die referenzielle Integrität der Tabelle beschädigt werden.  In diesem Fall löst das Framework beim Aufruf von **Update** eine Ausnahme aus.  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a> Hinzufügen eines Datensatzes zu einem Recordset  
 Sie können neue Datensätze zu einem Recordset hinzufügen, falls die [CanAppend](../Topic/CRecordset::CanAppend.md)\-Memberfunktion des Recordsets einen Wert ungleich 0 \(null\) zurückgibt.  
  
#### So fügen Sie einem Recordset einen neuen Datensatz hinzu  
  
1.  Stellen Sie sicher, dass das Recordset erweiterbar ist.  
  
2.  Rufen Sie die [AddNew](../Topic/CRecordset::AddNew.md)\-Memberfunktion des Recordset\-Objekts auf.  
  
     `AddNew` bereitet das Recordset so vor, dass dieses als Bearbeitungspuffer fungieren kann.  Alle Felddatenmember werden auf den Spezialwert NULL gesetzt und als nicht geändert markiert. So werden beim Aufruf von [Update](../Topic/CRecordset::Update.md) ausschließlich geänderte Werte in die Datenquelle geschrieben.  
  
3.  Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.  
  
     Weisen Sie den Felddatenmembern Werte zu.  Felddatenelemente, denen Sie keinen Wert zugewiesen haben, werden nicht in die Datenquelle geschrieben.  
  
4.  Rufen Sie die **Update**\-Memberfunktion des Recordset\-Objekts auf.  
  
     **Update** schließt das Hinzufügen des neuen Datensatzes ab, indem es den Datensatz in die Datenquelle schreibt.  Informationen darüber, was geschieht, wenn Sie **Update** nicht aufrufen, finden Sie unter[Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Informationen darüber, wie das Hinzufügen von Datensätzen funktioniert und wann hinzugefügte Datensätze im Recordset angezeigt werden, finden Sie unter [Recordset: Funktionsweise von AddNew, Edit und Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).  
  
 Das folgende Beispiel zeigt, wie Sie einen neuen Datensatz hinzufügen:  
  
```  
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
>  Um einen `AddNew`\-Aufruf oder **Edit**\-Aufruf abzubrechen, rufen Sie `AddNew` oder **Edit** bzw. **Move** mit dem **AFX\_MOVE\_REFRESH**\-Parameter erneut auf.  Die Datenmember werden auf ihren vorherigen Wert zurückgesetzt, befinden sich aber weiterhin im **Edit**\-Modus oder **Add**\-Modus.  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a> Editieren eines Datensatzes in einem Recordset  
 Sie können vorhandene Datensätze des Recordsets bearbeiten, falls die Memberfunktion [CanUpdate](../Topic/CRecordset::CanUpdate.md) des Recordsets einen Wert ungleich 0 \(null\) zurückgibt.  
  
#### So bearbeiten Sie einen vorhandenen Datensatz in einem Recordset  
  
1.  Stellen Sie sicher, dass das Recordset aktualisierbar ist.  
  
2.  Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.  
  
3.  Rufen Sie die [Edit](../Topic/CRecordset::Edit.md)\-Memberfunktion des Recordset\-Objekts auf.  
  
     **Edit** bereitet das Recordset so vor, dass es als Bearbeitungspuffer fungieren kann.  Alle Felddatenmember werden so markiert, dass das Recordset später feststellen kann, ob sie geändert wurden.  Die neuen Werte der geänderten Felddatenmember werden in die Datenquelle geschrieben, wenn Sie [Update](../Topic/CRecordset::Update.md) aufrufen.  
  
4.  Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.  
  
     Weisen Sie den Felddatenmembern Werte zu.  Felddatenmember, denen Sie keine Werte zuweisen, bleiben unverändert.  
  
5.  Rufen Sie die **Update**\-Memberfunktion des Recordset\-Objekts auf.  
  
     **Update** schließt das Bearbeiten des Datensatzes ab, indem es den geänderten Datensatz in die Datenquelle schreibt.  Informationen darüber, was geschieht, wenn Sie **Update** nicht aufrufen, finden Sie unter[Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Nachdem Sie einen Datensatz bearbeitet haben, bleibt er der aktuelle Datensatz.  
  
 Das folgende Beispiel zeigt eine **Edit**\-Operation.  Dabei wird vorausgesetzt, dass der Benutzer zu einem Datensatz gewechselt hat, den er bearbeiten möchte.  
  
```  
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
>  Um einen `AddNew`\-Aufruf oder **Edit**\-Aufruf abzubrechen, rufen Sie `AddNew` oder **Edit** bzw. **Move** mit dem **AFX\_MOVE\_REFRESH**\-Parameter erneut auf.  Die Datenmember werden auf ihren vorherigen Wert zurückgesetzt, befinden sich aber weiterhin im **Edit**\-Modus oder **Add**\-Modus.  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a> Löschen eines Datensatzes aus einem Recordset  
 Sie können Datensätze löschen, falls die [CanUpdate](../Topic/CRecordset::CanUpdate.md)\-Memberfunktion des Recordsets einen Wert ungleich 0 \(null\) zurückgibt.  
  
#### So löschen Sie einen Datensatz  
  
1.  Stellen Sie sicher, dass das Recordset aktualisierbar ist.  
  
2.  Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.  
  
3.  Rufen Sie die [Delete](../Topic/CRecordset::Delete.md)\-Memberfunktion des Recordset\-Objekts auf.  
  
     **Delete** markiert den Datensatz sofort als gelöscht, und zwar sowohl im Recordset als auch in der Datenquelle.  
  
     Im Unterschied zu `AddNew` und **Edit** gibt es keinen zu **Delete** gehörigen **Update**\-Aufruf.  
  
4.  Wechseln Sie zu einem anderen Datensatz.  
  
    > [!NOTE]
    >  Beim Scrollen durch das Recordset werden gelöschte Datensätze unter Umständen nicht übersprungen.  Weitere Informationen hierzu finden Sie unter dem Thema [IsDeleted](../Topic/CRecordset::IsDeleted.md)\-Memberfunktion.  
  
 Das folgende Beispiel zeigt eine **Delete**\-Operation.  Dabei wird vorausgesetzt, dass der Benutzer zu einem zu löschenden Datensatz gewechselt ist.  Nach dem Aufruf von **Delete** müssen Sie zu einem neuen Datensatz wechseln.  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 Weitere Informationen über die Auswirkungen der `AddNew`\-Memberfunktion, der **Edit**\-Memberfunktion und der **Delete**\-Memberfunktion finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Sperren von Datensätzen \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)