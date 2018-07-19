---
title: 'Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC) | Microsoft Docs'
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
ms.openlocfilehash: 1d7cae3b05c20736a2e271b574569bcac4d5cdc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094604"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)
In diesem Thema wird erläutert, wie eine Transaktion in einem Recordset ausführen wird.  
  
> [!NOTE]
>  Nur eine Ebene von Transaktionen wird unterstützt. Transaktionen können nicht geschachtelt werden.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Zum Ausführen einer Transaktions in einem recordset  
  
1.  Rufen Sie die `CDatabase` des Objekts **BeginTrans** Memberfunktion.  
  
2.  Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, rufen Sie die **AddNew/Update**, **bearbeiten/aktualisieren**, und **löschen** Memberfunktionen der ein oder mehrere Recordset-Objekte des gleichen die Datenbank so oft wie erforderlich. Weitere Informationen finden Sie unter [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Wenn Sie gesammelte implementiert haben, müssen Sie Ihre eigenen Funktionen zum Aktualisieren der Datenquelle schreiben.  
  
3.  Rufen Sie zum Schluss die `CDatabase` des Objekts **CommitTrans** Memberfunktion. Wenn in einem der Updates ein Fehler auftritt, oder Sie die Änderungen verwerfen möchten, rufen Sie die **Rollback** Memberfunktion.  
  
 Das folgende Beispiel verwendet zwei Recordsets So löschen Sie eine Student Registrierung aus einer Datenbank "School" Registrierung, entfernen die Studenten aus allen Klassen, die in denen die Studenten registriert ist. Da die **löschen** Aufrufe in beiden Recordsets müssen erfolgreich sein, eine Transaktion erforderlich ist. Im Beispiel wird vorausgesetzt, das Vorhandensein des `m_dbStudentReg`, eine Membervariable des Typs `CDatabase` bereits eine Verbindung zu der Datenquelle und der Recordset-Klassen `CEnrollmentSet` und `CStudentSet`. Die `strStudentID` Variable enthält einen Wert, der vom Benutzer abgerufen.  
  
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
>  Aufrufen von **BeginTrans** erneut ohne Aufruf **CommitTrans** oder **Rollback** ist ein Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaktion: Auswirkungen von Transaktionen Aktualisierungen (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)