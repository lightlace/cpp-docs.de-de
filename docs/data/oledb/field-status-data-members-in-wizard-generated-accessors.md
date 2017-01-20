---
title: "Feldstatus-Datenmember in vom Assistenten generierten Accessoren"
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
  - "Feldstatus in OLE DB-Vorlagen"
  - "OLE DB-Consumervorlagen, Feldstatus"
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Feldstatus-Datenmember in vom Assistenten generierten Accessoren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie den ATL OLE DB\-Consumer\-Assistenten zum Erstellen eines Consumers verwenden, generiert der Assistent für jedes Feld, das Sie in der Spaltenzuordnung angeben, einen Datenmember in der Benutzerdatensatz\-Klasse.  Jedes Datenmember hat den Typ `DWORD` und enthält einen Statuswert, der dem jeweiligen Feld entspricht.  
  
 Für ein Datenmember *m\_OwnerID* generiert der Assistent beispielsweise ein zusätzliches Datenmember für den Feldstatus \(*dwOwnerIDStatus*\) und ein weiteres für die Feldlänge \(*dwOwnerIDLength*\).  Darüber hinaus wird eine Spaltenzuordnung mit `COLUMN_ENTRY_LENGTH_STATUS`\-Einträgen generiert.  
  
 Dies wird im folgenden Code demonstriert:  
  
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
>  Wenn Sie die Benutzerdatensatz\-Klasse verändern oder einen eigenen Consumer schreiben, müssen die Datenvariablen vor den Status\- und Längenvariablen stehen.  
  
 Sie können die Statuswerte zum Debuggen verwenden.  Wenn vom ATL\-OLE DB\-Consumer\-Assistenten erstellter Code Kompilierungsfehler \(z. B. **DB\_S\_ERRORSOCCURRED** oder **DB\_E\_ERRORSOCCURRED**\) generiert, sollten Sie zunächst die aktuellen Werte der Feldstatus\-Datenmember überprüfen.  Diejenigen mit Werten ungleich 0 entsprechen den problemverursachenden Spalten.  
  
 Sie können die Statuswerte auch verwenden, um einen NULL\-Wert für ein bestimmtes Feld festzulegen.  Dies ist hilfreich in Fällen, in denen Sie einen Feldwert als NULL und nicht als 0 kennzeichnen möchten.  Sie können dabei selbst festlegen, ob NULL einen gültigen Wert oder einen speziellen Wert darstellt und wie die Anwendung diesen Wert behandeln soll.  OLE DB definiert **DBSTATUS\_S\_ISNULL** als korrektes Mittel zum Bestimmen eines generischen NULL\-Werts.  Wenn der Consumer Daten liest und der Wert NULL lautet, wird das Statusfeld auf **DBSTATUS\_S\_ISNULL** gesetzt.  Wenn der Consumer einen NULL\-Wert festlegen möchte, setzt er den Statuswert vor dem Aufrufen des Anbieters auf **DBSTATUS\_S\_ISNULL**.  
  
 Öffnen Sie danach Oledb.h, und suchen Sie nach **DBSTATUSENUM**.  Anschließend können Sie den numerischen Wert des Status mit dem Wert ungleich 0 \(null\) mit den **DBSTATUSENUM**\-Enumerationswerten vergleichen.  Wenn der Enumerationsname nicht ausreicht, herauszufinden, die falsch ist, finden Sie das Problem, Thema im "Datenwertzu binden" Abschnitt aus [OLE DB Programmierhandbuch](http://go.microsoft.com/fwlink/?LinkId=121548).  Dieses Thema enthält Tabellen mit Statuswerten, die beim Abrufen oder Festlegen von Daten verwendet werden.  Informationen zu Längenwerten finden Sie im gleichen Abschnitt im Thema "Länge".  
  
## Abrufen der Länge oder des Status einer Spalte  
 Es ist möglich, die Länge einer Spalte mit variabler Länge oder den Status einer Spalte abzurufen \(z. B. zur Überprüfung von **DBSTATUS\_S\_ISNULL**\):  
  
-   Um die Länge abzurufen, verwenden Sie das Makro `COLUMN_ENTRY_LENGTH`.  
  
-   Um den Status zu bestimmen, verwenden Sie das Makro `COLUMN_ENTRY_STATUS`.  
  
-   Um beides zu bestimmen, verwenden Sie `COLUMN_ENTRY_LENGTH_STATUS` wie im Folgenden dargestellt.  
  
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
  
CTable<CAccessor<CProducts > > product;  
  
product.Open(session, "Product");  
while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 Wenn Sie `CDynamicAccessor` verwenden, werden die Länge und der Status automatisch gebunden.  Um die Längen\- und Statuswerte abzurufen, verwenden Sie die `GetLength` und **GetStatus**\-Memberfunktionen.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)