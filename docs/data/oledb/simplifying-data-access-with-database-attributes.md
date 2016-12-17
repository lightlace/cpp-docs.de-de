---
title: "Vereinfachen des Datenzugriffs mit Datenbankattributen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attribute [C++], Datenzugriff"
  - "Attribute [C++], Datenbank"
  - "Attribute [C++], OLE DB-Consumer"
  - "Daten [C++], Vereinfachen des Zugriffs"
  - "Datenzugriff [C++], Datenbankattribute"
  - "Datenbankattribute [C++]"
  - "Datenbanken [C++], Attribute"
  - "OLE DB-Consumer [C++], Datenbankattribute"
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Vereinfachen des Datenzugriffs mit Datenbankattributen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die Verwendung von Datenbankattributen zum Vereinfachen von Datenbankoperationen demonstriert.  
  
 Die grundlegende Art des Zugriffs auf Datenbankinformationen besteht darin, eine Befehlsklasse \(oder Tabellenklasse\) sowie eine Benutzerdatensatz\-Klasse für eine bestimmte Tabelle in der Datenbank zu erstellen.  Die Datenbankattribute vereinfachen einige der zuvor notwendigen Vorlagendeklarationen.  
  
 Die Verwendung von Datenbankattributen wird in den folgenden Abschnitten anhand von zwei äquivalenten Deklarationen für Tabellen\- und Benutzerdatensatz\-Klassen demonstriert: Die erste verwendet Attribute und die zweite OLE DB\-Vorlagen.  Diese Art von Deklarationscode wird gewöhnlich in einer Headerdatei gespeichert, die dem Tabellen\- bzw. Befehlsobjekt entsprechend benannt wird, z. B. Authors.h.  
  
 Ein Vergleich der beiden Dateien macht deutlich, wie viel einfacher die Verwendung von Attributen ist.  Einige Unterschiede:  
  
-   Wenn Sie Attribute verwenden, müssen Sie nur eine Klasse deklarieren \(`CAuthors`\), während Sie beim Arbeiten mit Vorlagen zwei Klassen deklarieren müssen \(`CAuthorsNoAttrAccessor` und `CAuthorsNoAttr`\).  
  
-   Der Aufruf `db_source` in der Version mit Attributen entspricht dem Aufruf `OpenDataSource()` in der Vorlagendeklaration.  
  
-   Der Aufruf **db\_table** in der Version mit Attributen entspricht der folgenden Vorlagendeklaration:  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
    ```  
  
-   Die **db\_column**\-Aufrufe in der Version mit Attributen entsprechen der Spaltenzuordnung \(siehe `BEGIN_COLUMN_MAP ... END_COLUMN_MAP` in der Vorlagendeklaration.  
  
 Die Attribute fügen eine Benutzerdatensatz\-Klassendeklaration für Sie ein.  Die Benutzerdatensatz\-Klasse entspricht `CAuthorsNoAttrAccessor` in der Vorlagendeklaration.  Wenn die Tabellenklasse `CAuthors` lautet, erhält die eingefügte Benutzerdatensatz\-Klasse den Namen `CAuthorsAccessor`. Eine Ansicht der entsprechenden Deklaration ist nur im eingefügten Code möglich.  Weitere Informationen finden Sie unter "Benutzerdatensatz\-Klassen mit Attributbeteiligung" unter [Benutzerdatensätze](../../data/oledb/user-records.md).  
  
 Beachten Sie, dass Sie sowohl im Code mit Attributen als auch im Code mit Vorlagen die Rowseteigenschaften mithilfe von `CDBPropSet::AddProperty` festlegen müssen.  
  
 Informationen zu den in diesem Thema behandelten Attributen finden Sie unter [OLE DB\-Consumerattribute](../../windows/ole-db-consumer-attributes.md).  
  
## Tabellen\- und Accessordeklaration mithilfe von Attributen  
 Der folgende Code ruft `db_source` und **db\_table** für die Tabellenklasse auf.  `db_source` gibt dabei die zu verwendende Datenquelle und Verbindung an.  **db\_table** fügt den zum Deklarieren einer Tabellenklasse geeigneten Code ein.  **db\_column** gibt die Spaltenzuordnung an und fügt die Accessordeklaration ein.  OLE DB\-Consumerattribute können in jedem Projekt verwendet werden, das ATL unterstützt.  
  
 Hier nun die Tabellen\- und Accessordeklaration unter Verwendung von Attributen:  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## Tabellen\- und Accessordeklaration mithilfe von Vorlagen  
 Hier nun die Tabellen\- und Accessordeklaration unter Verwendung von Vorlagen:  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  
      HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
{  
public:  
   HRESULT OpenAll()  
   {  
      HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
      HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## Siehe auch  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)   
 [Attributes Walkthroughs](assetId:///73df1d5d-261a-4521-98fb-06dcbf5ec0d0)