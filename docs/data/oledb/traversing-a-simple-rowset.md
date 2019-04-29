---
title: Durchlaufen eines einfachen Rowsets
ms.date: 10/19/2018
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
ms.openlocfilehash: 88a027a24f8ab817f793f101f9f128e1fc0c61c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389150"
---
# <a name="traversing-a-simple-rowset"></a>Durchlaufen eines einfachen Rowsets

Das folgende Beispiel zeigt, Zugriff auf die schnelle und einfache Datenbank, die Befehle enthalten, nicht. Der folgende Consumercode, in einem ATL-Projekt ruft Datensätze aus einer Tabelle namens *Künstler* in einer Microsoft Access-Datenbank mithilfe von Microsoft OLE DB-Anbieter für ODBC. Der Code erstellt eine [CTable](../../data/oledb/ctable-class.md) Table-Objekt mit einem Accessor, auf der Grundlage von der Benutzerdatensatz-Klasse `CArtists`. Öffnet eine Verbindung, wird eine Sitzung für die Verbindung geöffnet und die Tabelle in der Sitzung wird geöffnet.

```cpp
#include <atldbcli.h>
#include <iostream>

using namespace std;

int main()
{
    CDataSource connection;
    CSession session;
    CTable<CAccessor<CArtists>> artists;

    LPCSTR clsid; // Initialize CLSID_MSDASQL here
    LPCTSTR pName = L"NWind";

    // Open the connection, session, and table, specifying authentication
    // using Windows NT integrated security. Hard-coding a password is a major
    // security weakness.
    connection.Open(clsid, pName, NULL, NULL, DBPROP_AUTH_INTEGRATED);

    session.Open(connection);

    artists.Open(session, "Artists");

    // Get data from the rowset
    while (artists.MoveNext() == S_OK)
    {
       cout << artists.m_szFirstName;
       cout << artists.m_szLastName;
    }

    return 0;
}
```

Benutzerdatensatz `CArtists`, sieht wie im folgenden Beispiel:

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()
};
```

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)