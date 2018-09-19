---
title: Feld-Datenmember in vom Assistenten generierten Zugriffsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e289e2f40326142894894dad1bfe34c801889bb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066855"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Feldstatus-Datenmember in vom Assistenten generierten Zugriffsmethoden

Wenn Sie die ATL-OLE DB-Consumer-Assistenten verwenden, um einen Consumer zu erstellen, generiert der Assistent einen Datenmember in die Benutzerdatensatz-Klasse für jedes Feld, das Sie in der spaltenzuordnung angeben. Jedes Datenelement ist vom Typ `DWORD` und enthält einen Statuswert, der dem jeweiligen Feld entspricht.  
  
Z. B. für einen Datenmember *M_OwnerID*, generiert der Assistent einen zusätzlichen Datenmember für Feldstatus (*DwOwnerIDStatus*) und eine andere für die Feldlänge (*DwOwnerIDLength*). Es generiert außerdem eine spaltenzuordnung zu COLUMN_ENTRY_LENGTH_STATUS-Einträgen.  
  
Dies wird im folgenden Code gezeigt:  
  
```cpp  
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
  
Sie können die Status-Werte verwenden, zu Debugzwecken. Wenn mit dem ATL-OLE DB-Consumer-Assistenten generierten Code Kompilierungsfehler, z. B. DB_S_ERRORSOCCURRED oder DB_E_ERRORSOCCURRED generiert, sollten Sie zunächst die aktuellen Werte von der Feldstatus-Datenmember überprüfen. Die betreffenden Spalten entsprechen mit Werten ungleich NULL.  
  
Sie können auch die Status-Werte verwenden, um einen NULL-Wert für ein bestimmtes Feld festzulegen. Auf diese Weise können Sie in Fällen, in denen Sie einen Feldwert als NULL statt 0 (null) zu unterscheiden möchten. Es liegt an Ihnen zu entscheiden, ob NULL ein gültiger Wert oder ein spezieller Wert, und entscheiden, wie Sie Ihre Anwendung behandelt werden soll. OLE DB definiert DBSTATUS_S_ISNULL als die richtige Methode zur Angabe der eines generischen NULL-Werts. Wenn der Consumer Daten liest, und der Wert null ist, wird das Statusfeld auf DBSTATUS_S_ISNULL festgelegt. Wenn der Consumer einen NULL-Wert festgelegt möchte, setzt der Consumer den Statuswert auf DBSTATUS_S_ISNULL vor dem Aufruf des Anbieters an.  
  
Öffnen Sie "OleDb.h", und suchen Sie nach `DBSTATUSENUM`. Anschließend können Sie vergleichen, der numerische Wert des Status mit dem ungleich null der `DBSTATUSENUM` -Enumerationswerte fest. Der Enumerationsname reicht nicht aus Ihnen mitteilen, was falsch ist, finden Sie unter "Status" im Abschnitt "Binding Data Values" der [OLE DB Programmer's Guide](/previous-versions/windows/desktop/ms713643\(v=vs.85\)). Dieses Thema enthält Tabellen mit dem Status-Werte, die beim Abrufen oder Festlegen der Daten verwendet. Informationen zu Längenwerten finden Sie im Thema "Length" im gleichen Abschnitt.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Abrufen der Länge oder der Status einer Spalte  

Sie können die Länge einer Spalte variabler Länge oder der Status einer Spalte (z. B. DBSTATUS_S_ISNULL, zu überprüfen) abrufen:  
  
- Verwenden Sie zum Abrufen der Länge der COLUMN_ENTRY_LENGTH-Makro ein.  
  
- Um den Status zu erhalten, verwenden Sie die COLUMN_ENTRY_STATUS-Marko.  
  
- Um beides zu erhalten, verwenden Sie COLUMN_ENTRY_LENGTH_STATUS, wie unten dargestellt.  
  
```cpp  
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
  
Bei Verwendung von `CDynamicAccessor`, die Länge und den Status automatisch für Sie gebunden sind. Verwenden Sie zum Abrufen der Werte für Länge und der Status der `GetLength` und `GetStatus` Memberfunktionen.  
  
## <a name="see-also"></a>Siehe auch  

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)