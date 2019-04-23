---
title: Vereinfachen des Datenzugriffs mit Datenbankattributen
ms.date: 10/19/2018
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
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
ms.openlocfilehash: 83519ffff7dd1f1b5f8a635f094932a1f9728193
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031049"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Vereinfachen des Datenzugriffs mit Datenbankattributen

Dieses Thema veranschaulicht die Verwendung von Datenbankattributen, um Datenbankvorgänge zu vereinfachen.

Die einfachste Möglichkeit, Zugriff auf Informationen aus einer Datenbank ist eine Befehlsklasse (oder Tabellenklasse)-Klasse und eine Benutzerdatensatz-Klasse für eine bestimmte Tabelle in der Datenbank zu erstellen. Der Datenbankattribute vereinfachen Teile der Vorlagendeklarationen, die Sie zuvor musste.

Um die Verwendung von Datenbankattributen zu veranschaulichen, die folgenden Abschnitte zeigen, zwei entsprechende Tabelle und die Benutzerdatensatz-Klassendeklarationen Benutzer: die erste verwendet Attribute und die zweite verwendet OLE DB-Vorlagen. Solcher Deklarationscode ist in der Regel in einer Headerdatei mit dem Namen für die Tabelle oder der Befehl-Objekt, z. B. authors.h.

Vergleichen Sie die beiden Dateien, können Sie sehen, wie viel einfacher ist es zum Verwenden von Attributen. Zu den Unterschieden zählen:

- Verwenden von Attributen, Sie müssen nur eine Klasse zu deklarieren: `CAuthors`, während mit Vorlagen Sie zwei deklarieren müssen: `CAuthorsNoAttrAccessor` und `CAuthorsNoAttr`.

- Die `db_source` Aufruf in der Version entspricht der `OpenDataSource()` rufen Sie in der Vorlagendeklaration.

- Die `db_table` Aufruf in der Version entspricht der folgenden Vorlage-Deklaration:

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- Die `db_column` Aufrufe in der Version entsprechen der spaltenzuordnung (finden Sie unter `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) in der Vorlagendeklaration.

Sie injizieren die Attribute eine Benutzerdatensatz-Klassendeklaration auf. Die Benutzerdatensatz-Klasse ist gleich `CAuthorsNoAttrAccessor` in der Vorlagendeklaration. Wenn Ihre Tabellenklasse ist `CAuthors`, wird die eingefügte Benutzerdatensatz-Klasse mit dem Namen `CAuthorsAccessor`, und Sie können nur der Deklaration im eingefügten Code anzeigen. Weitere Informationen finden Sie unter "Attribute-Injected Benutzerdatensatz-Klassen" in [Benutzerdatensätze](../../data/oledb/user-records.md).

Die attributierte sowohl, in den auf Vorlagen basierende Code müssen Sie festlegen, Rowset-Eigenschaften, die mit `CDBPropSet::AddProperty`.

Weitere Informationen zu den Attributen, die in diesem Thema erläutert, finden Sie unter [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md).

> [!NOTE]
> Die folgenden `include` Anweisungen sind erforderlich, um die folgenden Beispiele zu kompilieren:
> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>Tabellen- und Zugriffsmethoden-Deklaration, die mithilfe von Attributen

Der folgende code ruft `db_source` und `db_table` in der Tabellenklasse. `db_source` Gibt die Datenquelle und die zu verwendende Verbindung. `db_table` Fügt den geeigneten Code zum Deklarieren einer Tabellenklasse an. `db_column` Geben Sie die spaltenzuordnung, und fügen Sie die Zugriffsmethoden-Deklaration. Sie können OLE DB-Consumerattribute in jedem Projekt verwenden, die ATL unterstützt.

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
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>Tabellen- und Zugriffsmethoden-Deklaration, die mithilfe von Vorlagen

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

[OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md)
