---
title: Vereinfachen des Datenzugriffs mit Datenbankattributen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e665369f292a646353d1a180661982ce4c902665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111714"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Vereinfachen des Datenzugriffs mit Datenbankattributen
Dieses Thema veranschaulicht die Verwendung von Datenbankattributen, um Datenbankvorgänge zu vereinfachen.  
  
 Der grundlegende Zugriff auf Informationen aus einer Datenbank besteht darin, eine Klasse Befehlsklasse (oder Tabellenklasse) und eine Benutzerdatensatz-Klasse für eine bestimmte Tabelle in der Datenbank zu erstellen. Der Datenbankattribute vereinfachen Sie einige der Vorlagendeklarationen, die Sie zuvor bereits profitierten möchten.  
  
 Um die Verwendung von Datenbankattributen zu demonstrieren, die folgenden Abschnitte zeigen zwei entsprechende Tabelle und die Benutzerdatensatz-Klassendeklarationen Benutzer: die erste verwendet Attribute und die zweite OLE DB-Vorlagen. Solcher Deklarationscode ist in der Regel in einer Headerdatei, die mit dem Namen für die Tabelle oder Befehl-Objekt, z. B. authors.h.  
  
 Vergleichen Sie die beiden Dateien, können Sie sehen, wie viel einfacher ist es zum Verwenden von Attributen. Einige Unterschiede:  
  
-   Verwenden von Attributen, Sie müssen nur eine Klasse deklarieren: `CAuthors`, während mit Vorlagen Sie zwei deklarieren müssen: `CAuthorsNoAttrAccessor` und `CAuthorsNoAttr`.  
  
-   Die `db_source` Aufruf in der Version entspricht der `OpenDataSource()` rufen Sie in der Vorlagendeklaration.  
  
-   Die **Db_table** Aufruf in der Version entspricht der folgenden Vorlagendeklaration:  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   Die **Db_column** Aufrufe in der Version entsprechen der spaltenzuordnung (siehe `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) in der Vorlagendeklaration.  
  
 Die Attribute einfügen eine Benutzerdatensatz-Klassendeklaration für Sie. Die Benutzerdatensatz-Klasse entspricht `CAuthorsNoAttrAccessor` in der Vorlagendeklaration. Wenn Ihre Tabellenklasse `CAuthors`, wird die eingefügte Benutzerdatensatz-Klasse mit dem Namen `CAuthorsAccessor`, und Sie können nur der Deklaration im eingefügten Code anzeigen. Weitere Informationen finden Sie unter "Attribute-Injected Benutzerdatensatz-Klassen" in [Benutzerdatensätze](../../data/oledb/user-records.md).  
  
 Beachten Sie, dass die attributierte sowohl auf Vorlagen basierende Code, Sie Rowseteigenschaften mit festlegen müssen `CDBPropSet::AddProperty`.  
  
 Weitere Informationen zu den Attributen, die in diesem Thema erläutert, finden Sie unter [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md).  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>Tabelle und der Accessordeklaration, die mithilfe von Attributen  
 Der folgende code ruft `db_source` und **Db_table** in der Tabellenklasse. `db_source` Gibt die Datenquelle und die zu verwendende Verbindung. **Db_table** wird die entsprechende Vorlagencode zum Deklarieren einer Tabellenklasse eingefügt. **Db_column** der spaltenzuordnung angeben und die Accessordeklaration einfügen. Sie können OLE DB-Consumerattribute in jedem Projekt verwenden, die ATL unterstützt.  
  
 Hier ist die Tabelle "und"-Accessor-Deklaration, die mithilfe von Attributen:  
  
```cpp
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
  
## <a name="table-and-accessor-declaration-using-templates"></a>Tabelle und der Accessordeklaration, die mithilfe von Vorlagen  
 Hier ist die Tabelle "und"-Accessor-Deklaration, die mithilfe von Vorlagen.  
  
```cpp
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
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
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
  
## <a name="see-also"></a>Siehe auch  
 [OLE Consumerattribute DB-](../../windows/ole-db-consumer-attributes.md)   
 [Exemplarische Vorgehensweisen für Attribute](http://msdn.microsoft.com/en-us/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)