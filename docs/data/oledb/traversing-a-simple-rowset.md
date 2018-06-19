---
title: Durchlaufen eines einfachen Rowsets | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a29d7a226d12f9c464d91ec356ae8a1a02091f1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102950"
---
# <a name="traversing-a-simple-rowset"></a>Durchlaufen eines einfachen Rowsets
Das folgende Beispiel zeigt die eine schnellen und einfachen Zugriff, die keine Befehle beinhaltet. Die folgenden Consumercode in einem ATL-Projekt ruft Datensätze aus einer Tabelle mit dem Namen *Künstler* in einer Microsoft Access-Datenbank mithilfe der Microsoft OLE DB-Anbieter für ODBC. Der Code erstellt ein [CTable](../../data/oledb/ctable-class.md) Table-Objekt mit einem Accessor basierend auf die Benutzerdatensatz-Klasse `CArtists`. Öffnet eine Verbindung, wird eine Sitzung für die Verbindung geöffnet und die Tabelle in der Sitzung geöffnet.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists>> artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL, DBPROP_AUTH_INTEGRATED);  

session.Open(connection);  

artists.Open(session, "Artists");  
  
// Get data from the rowset  
while (artists.MoveNext() == S_OK)  
{  
   cout << artists.m_szFirstName;  
   cout << artists.m_szLastName;  
}  
```  
  
 Der Benutzerdatensatz `CArtists`, wie folgt aussieht:  
  
```  
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
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)