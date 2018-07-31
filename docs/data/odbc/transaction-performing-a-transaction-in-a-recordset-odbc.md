---
title: 'Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9fcc5c6aae86aea005aef50f9083aeb718f64b19
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340266"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)
In diesem Thema wird erläutert, wie Sie eine Transaktion in einem Recordset ausführen wird.  
  
> [!NOTE]
>  Es wird nur eine Ebene von Transaktionen unterstützt. Sie können keine Transaktionen verschachteln.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Ausführen eine Transaktion in einem recordset  
  
1.  Rufen Sie die `CDatabase` des Objekts `BeginTrans` Member-Funktion.  
  
2.  Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, rufen Sie die `AddNew/Update`, `Edit/Update`, und `Delete` Memberfunktionen von ein oder mehrere Recordset-Objekte der gleichen Datenbank so oft wie erforderlich. Weitere Informationen finden Sie unter [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Wenn Sie die gesammelte implementiert haben, müssen Sie Ihre eigenen Funktionen zum Aktualisieren der Datenquelle schreiben.  
  
3.  Rufen Sie abschließend die `CDatabase` des Objekts `CommitTrans` Member-Funktion. Wenn in einem der Updates ein Fehler auftritt, oder Sie entscheiden, um die Änderungen abzubrechen, rufen Sie die `Rollback` Member-Funktion.  
  
 Im folgende Beispiel wird mit zwei Recordsets eine Student Registrierung aus einer Datenbank "School"-Registrierung, entfernt der Student, der aus allen Klassen, die in denen der Student, der registriert wird gelöscht. Da die `Delete` Aufrufe in beiden Recordsets müssen erfolgreich sein, eine Transaktion ist erforderlich. Im Beispiel wird davon ausgegangen, `m_dbStudentReg`, eine Membervariable des Typs `CDatabase` bereits Verbindungen mit der Datenquelle und der Recordset-Klassen `CEnrollmentSet` und `CStudentSet`. Die `strStudentID` Variable enthält einen Wert, der vom Benutzer.  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  Aufrufen von `BeginTrans` erneut ohne `CommitTrans` oder `Rollback` ein Fehler auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaktion: Auswirkungen von Transaktionen Aktualisierungen (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)