---
title: "Transaktion: Ausf&#252;hren einer Transaktion in einem Recordset (ODBC)"
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
  - "Transaktionen, Aktualisieren von Recordsets"
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Transaktion: Ausf&#252;hren einer Transaktion in einem Recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie Sie eine Transaktion in einem Recordset ausführen.  
  
> [!NOTE]
>  Es wird nur eine einzige Transaktionsebene unterstützt. Sie können Transaktionen nicht schachteln.  
  
#### So führen Sie eine Transaktion in einem Recordset aus  
  
1.  Rufen Sie die **BeginTrans**\-Memberfunktion des `CDatabase`\-Objekts auf.  
  
2.  Falls Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, rufen Sie so oft wie erforderlich die Memberfunktionen **AddNew\/Update**, **Edit\/Update** und **Delete** eines oder mehrerer Recordset\-Objekte derselben Datenbank auf.  Weitere Informationen finden Sie unter [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  Falls Sie das gesammelte Abrufen von Zeilen implementiert haben, müssen Sie eigene Funktionen zur Aktualisierung der Datenquelle erstellen.  
  
3.  Rufen Sie abschließend die **CommitTrans**\-Memberfunktion des CDatabase\-Objekts auf.  Wenn bei einer Aktualisierung ein Fehler auftritt oder die Änderungen abgebrochen werden sollen, rufen Sie die zugehörige **Rollback**\-Memberfunktion auf.  
  
 Im folgenden Beispiel wird mithilfe von zwei Recordsets die Einschreibung eines Studenten in die Registrierdatenbank der Schule gelöscht. So wird der Student aus allen Kursen gelöscht, in denen er eingetragen war.  Da die **Delete**\-Aufrufe in beiden Recordsets erfolgreich durchgeführt werden müssen, wird eine Transaktion benötigt.  Das Beispiel setzt das Vorhandensein von `m_dbStudentReg` voraus, einer Membervariablen vom Typ `CDatabase`, die bereits mit der Datenquelle verbunden ist, sowie der Recordset\-Klassen `CEnrollmentSet` und `CStudentSet`.  Die `strStudentID`\-Variable enthält einen Wert, der vom Benutzer eingegeben wurde.  
  
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
>  Das erneute Aufrufen von **BeginTrans** ohne **CommitTrans** oder **Rollback** aufzurufen stellt einen Fehler dar.  
  
## Siehe auch  
 [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)