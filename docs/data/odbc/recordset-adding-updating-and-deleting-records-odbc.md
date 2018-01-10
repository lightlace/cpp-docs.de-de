---
title: "Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cad50d25f6b9e2cc619fb19e21c2b6575ababa47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
> [!NOTE]
>  Sie können jetzt Datensätze in einer Sammeloperation effizienter hinzufügen. Weitere Informationen finden Sie unter [Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Mit aktualisierbaren Momentaufnahmen und Dynasets können Sie Datensätze hinzufügen, bearbeiten (aktualisieren) und löschen. In diesem Thema wird Folgendes erläutert:  
  
-   [Gewusst wie: bestimmen, ob das Recordset aktualisierbar ist](#_core_determining_whether_your_recordset_is_updatable).  
  
-   [Gewusst wie: Hinzufügen eines neues Datensatzes](#_core_adding_a_record_to_a_recordset).  
  
-   [Gewusst wie: bearbeiten ein vorhandenes Datensatzes](#_core_editing_a_record_in_a_recordset).  
  
-   [Vorgehensweise: Löschen ein Datensatzes](#_core_deleting_a_record_from_a_recordset).  
  
 Weitere Informationen, wie Aktualisierungen durchgeführt werden kopiert und die Aktualisierungen, anderen Benutzern angezeigt werden, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md). Wenn Sie einen Datensatz hinzufügen, ändern oder löschen, ändert das Recordset die Datenquelle normalerweise sofort. Alternativ können Sie Gruppen zusammengehöriger Aktualisierungen zu Transaktionen zusammenfassen. Während einer Transaktion werden die Aktualisierungen nicht vor Bestätigung der Transaktion endgültig. So können Sie die Änderungen zurücksetzen. Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
 In der folgenden Tabelle ist zusammengefasst, welche Optionen für Recordsets zur Verfügung stehen mit den jeweiligen Aktualisierungsmerkmalen.  
  
### <a name="recordset-readupdate-options"></a>Lese- und Aktualisierungsoptionen von Recordsets  
  
|Typ|Lesen|Datensatz bearbeiten|Datensatz löschen|Neue hinzufügen (anhängen)|  
|----------|----------|-----------------|-------------------|------------------------|  
|Schreibgeschützt|J|N|N|N|  
|Nur erweiterbar|J|N|N|J|  
|Ohne Einschränkungen aktualisierbar|J|J|J|J|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a>Bestimmen, ob das Recordset ist aktualisierbar  
 Ein Recordset-Objekt ist aktualisierbar, wenn die Datenquelle aktualisierbar ist und Sie das Recordset als aktualisierbar geöffnet haben. Außerdem hängt die Aktualisierbarkeit von der verwendeten SQL-Anweisung ab, von den Fähigkeiten des ODBC-Treibers und davon, ob die ODBC-Cursorbibliothek geladen ist. Sie können ein schreibgeschütztes Recordset oder eine schreibgeschützte Datenquelle nicht aktualisieren.  
  
#### <a name="to-determine-whether-your-recordset-is-updatable"></a>So stellen Sie fest, ob das Recordset aktualisierbar ist  
  
1.  Rufen Sie des Recordset-Objekts [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Memberfunktion.  
  
     `CanUpdate` gibt einen Wert ungleich 0 (null) zurück, falls das Recordset aktualisierbar ist.  
  
 Standardmäßig sind Recordsets aktualisierbar (Sie ausführen können `AddNew`, **bearbeiten**, und **löschen** Vorgänge). Sie können jedoch auch die [AppendOnly](../../mfc/reference/crecordset-class.md#open) können aktualisierbare Recordsets zu öffnen. Zu einem auf diese Weise geöffneten Recordset können Sie lediglich mit `AddNew` neue Datensätze hinzufügen. Sie können keine vorhandenen Datensätze bearbeiten oder löschen. Sie können testen, ob ein Recordset nur zum Anhängen von Aufrufen geöffnet ist die [CanAppend](../../mfc/reference/crecordset-class.md#canappend) Memberfunktion. `CanAppend` gibt einen Wert ungleich 0 (null) zurück, wenn das Recordset vollständig aktualisierbar ist oder nur zum Anhängen geöffnet ist.  
  
 Der folgende Codeausschnitt zeigt, wie Sie `CanUpdate` in einem Recordset-Objekt mit dem Namen `rsStudentSet` aufrufen können:  
  
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
>  Vorbereitung für die Aktualisierung eines Recordsets durch Aufrufen von **aktualisieren**, achten Sie darauf, dass das Recordset alle Spalten, aus denen der Primärschlüssel der Tabelle (oder alle Spalten eines eindeutigen Index für die Tabelle) umfasst. In einigen Fällen kann das Framework zur Identifizierung des Datensatzes, der in der Tabelle aktualisiert werden soll, nur die Spalten verwenden, die im Recordset ausgewählt sind. Wenn nicht sämtliche benötigten Spalten zur Verfügung stehen, werden möglicherweise mehrere Datensätze in der Tabelle aktualisiert. Hierdurch kann die referenzielle Integrität der Tabelle beschädigt werden. In diesem Fall löst das Framework Ausnahmen aus, wenn Sie aufrufen **Update**.  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a>Hinzufügen eines Datensatzes zu einem Recordset  
 Sie können neue Datensätze zu einem Recordset hinzufügen, wenn seine [CanAppend](../../mfc/reference/crecordset-class.md#canappend) Memberfunktion gibt einen Wert ungleich NULL zurück.  
  
#### <a name="to-add-a-new-record-to-a-recordset"></a>So fügen Sie einem Recordset einen neuen Datensatz hinzu  
  
1.  Stellen Sie sicher, dass das Recordset erweiterbar ist.  
  
2.  Rufen Sie des Recordset-Objekts [AddNew](../../mfc/reference/crecordset-class.md#addnew) Memberfunktion.  
  
     `AddNew` bereitet das Recordset so vor, dass dieses als Bearbeitungspuffer fungieren kann. Alle Felddatenmember werden auf den Spezialwert Null festgelegt und als nicht geändert markiert, damit nur geänderte Werte in die Datenquelle geschrieben werden, beim Aufrufen von [Update](../../mfc/reference/crecordset-class.md#update).  
  
3.  Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.  
  
     Weisen Sie den Felddatenmembern Werte zu. Felddatenelemente, denen Sie keinen Wert zugewiesen haben, werden nicht in die Datenquelle geschrieben.  
  
4.  Rufen Sie des Recordset-Objekts **Update** Memberfunktion.  
  
     **Update** schließt das Hinzufügen von den neuen Eintrag in der Datenquelle schreibt. Informationen, was geschieht, wenn Sie nicht aufrufen **Update**, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Informationen zum Hinzufügen von Datensätzen und wann hinzugefügte Datensätze im Recordset angezeigt werden, finden Sie unter [Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).  
  
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
>  Auf "Abbrechen" ein `AddNew` oder **bearbeiten** aufzurufen, rufen zum `AddNew` oder **bearbeiten** , oder rufen Sie **verschieben** mit der **AFX_MOVE_REFRESH**  Parameter. Datenmember werden auf ihren vorherigen Wert zurückgesetzt, und Sie befinden sich noch im **bearbeiten** oder **hinzufügen** Modus.  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a>Editieren eines Datensatzes in einem Recordset  
 Sie können vorhandene Datensätze bearbeiten, wenn des Recordsets [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Memberfunktion gibt einen Wert ungleich NULL zurück.  
  
#### <a name="to-edit-an-existing-record-in-a-recordset"></a>So bearbeiten Sie einen vorhandenen Datensatz in einem Recordset  
  
1.  Stellen Sie sicher, dass das Recordset aktualisierbar ist.  
  
2.  Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.  
  
3.  Rufen Sie des Recordset-Objekts [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Memberfunktion.  
  
     **Bearbeiten Sie** bereitet das Recordset als Bearbeitungspuffer fungieren. Alle Felddatenmember werden so markiert, dass das Recordset später feststellen kann, ob sie geändert wurden. Die neuen Werte für die geänderten Felddatenmember werden an die Datenquelle geschrieben, wenn Sie rufen [Update](../../mfc/reference/crecordset-class.md#update).  
  
4.  Stellen Sie die Werte der Felddatenmember des neuen Datensatzes ein.  
  
     Weisen Sie den Felddatenmembern Werte zu. Felddatenmember, denen Sie keine Werte zuweisen, bleiben unverändert.  
  
5.  Rufen Sie des Recordset-Objekts **Update** Memberfunktion.  
  
     **Update** schließt das Bearbeiten von den geänderten Datensatz in die Datenquelle schreibt. Informationen, was geschieht, wenn Sie nicht aufrufen **Update**, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Nachdem Sie einen Datensatz bearbeitet haben, bleibt er der aktuelle Datensatz.  
  
 Das folgende Beispiel zeigt eine **bearbeiten** Vorgang. Dabei wird vorausgesetzt, dass der Benutzer zu einem Datensatz gewechselt hat, den er bearbeiten möchte.  
  
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
>  Auf "Abbrechen" ein `AddNew` oder **bearbeiten** aufzurufen, rufen zum `AddNew` oder **bearbeiten** , oder rufen Sie **verschieben** mit der **AFX_MOVE_REFRESH**  Parameter. Datenmember werden auf ihren vorherigen Wert zurückgesetzt, und Sie befinden sich noch im **bearbeiten** oder **hinzufügen** Modus.  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a>Löschen eines Datensatzes aus einem Recordset  
 Sie können Datensätze löschen, wenn des Recordsets [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) Memberfunktion gibt einen Wert ungleich NULL zurück.  
  
#### <a name="to-delete-a-record"></a>So löschen Sie einen Datensatz  
  
1.  Stellen Sie sicher, dass das Recordset aktualisierbar ist.  
  
2.  Wechseln Sie zu dem Datensatz, den Sie aktualisieren möchten.  
  
3.  Rufen Sie des Recordset-Objekts [löschen](../../mfc/reference/crecordset-class.md#delete) Memberfunktion.  
  
     **Löschen Sie** markiert den Datensatz sofort als gelöscht, sowohl im Recordset als auch für die Datenquelle.  
  
     Im Gegensatz zu `AddNew` und **bearbeiten**, **löschen** verfügt über keine entsprechende **Update** aufrufen.  
  
4.  Wechseln Sie zu einem anderen Datensatz.  
  
    > [!NOTE]
    >  Beim Scrollen durch das Recordset werden gelöschte Datensätze unter Umständen nicht übersprungen. Weitere Informationen finden Sie unter der [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) Memberfunktion.  
  
 Das folgende Beispiel zeigt eine **löschen** Vorgang. Dabei wird vorausgesetzt, dass der Benutzer zu einem zu löschenden Datensatz gewechselt ist. Nach dem **löschen** wird aufgerufen, es ist wichtig, um einen neuen Datensatz zu verschieben.  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 Weitere Informationen zu den Auswirkungen der `AddNew`, **bearbeiten**, und **löschen** Memberfunktionen, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)