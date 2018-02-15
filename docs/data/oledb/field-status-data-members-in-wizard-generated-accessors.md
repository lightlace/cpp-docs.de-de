---
title: Feldstatus-Datenmember in vom Assistenten generierten Accessoren Feld | Microsoft Docs
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
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab099689af725c2b074f4caf4d2e9b13d16fbaf2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Feldstatus-Datenmember in vom Assistenten generierten Zugriffsmethoden
Wenn Sie den ATL OLE DB-Consumer-Assistenten zum Erstellen eines Consumers verwenden, generiert der Assistent einen Datenmember in der Benutzerdatensatz-Klasse für jedes Feld, das Sie in der spaltenzuordnung angeben. Jedes Datenelement ist vom Typ `DWORD` und enthält einen Statuswert, der dem jeweiligen Feld entspricht.  
  
 Z. B. für einen Datenmember *M_OwnerID*, generiert der Assistent einen zusätzlichen Datenmember für Feldstatus (*DwOwnerIDStatus*) und eine andere Wissensdatenbank für die Feldlänge (*DwOwnerIDLength*). Außerdem generiert er eine spaltenzuordnung mit `COLUMN_ENTRY_LENGTH_STATUS` Einträge.  
  
 Dies wird im folgenden Code gezeigt:  
  
```  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
>  Wenn Sie die Benutzerdatensatz-klasse ändern oder einen eigenen Consumer erstellen, müssen die Datenvariablen in der Reihenfolge vor den Status- und Längenvariablen liegen.  
  
 Sie können die Statuswerte für Debugzwecke verwenden. Wenn vom ATL-OLE DB-Consumer-Assistenten generierte Code Kompilierungsfehler, wie z. B. generiert **DB_S_ERRORSOCCURRED** oder **DB_E_ERRORSOCCURRED**, sollte die uns zunächst an die aktuellen Werte von der Feldstatus Datenmember. Werte ungleich NULL haben, die betreffenden Spalten entsprechen.  
  
 Die Statuswerte können auch einen Nullwert für ein bestimmtes Feld festlegen. Dies ist hilfreich in Fällen, in denen Sie einen Feldwert als NULL statt 0 (null) zu unterscheiden möchten. Es ist entscheiden, ob Sie entscheiden, ob NULL ein gültiger Wert oder ein spezieller Wert ist, und entscheiden, wie Sie Ihre Anwendung behandelt werden sollen. OLE DB definiert **DBSTATUS_S_ISNULL** als die richtige Methode zur Angabe eines generischen NULL-Werts. Wenn der Consumer Daten liest, und der Wert null ist, wird das Statusfeld zu festgelegt **DBSTATUS_S_ISNULL**. Wenn der Consumer ein Nullwert festgelegt möchte, der Consumer legt den Statuswert auf **DBSTATUS_S_ISNULL** vor dem Aufrufen des Anbieters.  
  
 Als Nächstes öffnen Sie "OleDb.h", und suchen Sie nach **DBSTATUSENUM**. Anschließend können Sie den numerischen Wert des Status mit dem Wert ungleich NULL Vergleichen die **DBSTATUSENUM** Enumerationswerte. Ist der Enumerationsname nicht ausreichend, um Aufschluss darüber, was das Problem ist, finden Sie im Thema "Status" im Abschnitt "Datenwerte binden", der die [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/p/?linkid=121548). Dieses Thema enthält Tabellen mit Statuswerte, die beim Abrufen oder Festlegen von Daten verwendet. Informationen zu Längenwerten finden Sie unter dem Thema "Length" im gleichen Abschnitt.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Abrufen der Länge oder den Status einer Spalte  
 Sie können die Länge einer Spalte variabler Länge oder den Status einer Spalte abrufen (zu suchende **DBSTATUS_S_ISNULL**, z. B.):  
  
-   Verwenden Sie zum Abrufen der Länge der `COLUMN_ENTRY_LENGTH` Makro.  
  
-   Verwenden Sie zum Abrufen des Status der `COLUMN_ENTRY_STATUS` Makro.  
  
-   Verwenden Sie zum Abrufen sowohl `COLUMN_ENTRY_LENGTH_STATUS`, wie unten dargestellt.  
  
```  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts >> product;  
  
product.Open(session, "Product");  

while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 Bei Verwendung von `CDynamicAccessor`, Länge und der Status automatisch für Sie gebunden sind. Verwenden Sie zum Abrufen der Werte für Länge und der Status der `GetLength` und **GetStatus** Memberfunktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)