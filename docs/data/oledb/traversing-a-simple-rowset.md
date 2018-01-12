---
title: Durchlaufen eines einfachen Rowsets | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9f792e7a65a55cb63fb275d4d606a743e00a0e2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="traversing-a-simple-rowset"></a>Durchlaufen eines einfachen Rowsets
Das folgende Beispiel zeigt die eine schnellen und einfachen Zugriff, die keine Befehle beinhaltet. Die folgenden Consumercode in einem ATL-Projekt ruft Datensätze aus einer Tabelle mit dem Namen *Künstler* in einer Microsoft Access-Datenbank mithilfe der Microsoft OLE DB-Anbieter für ODBC. Der Code erstellt ein [CTable](../../data/oledb/ctable-class.md) Table-Objekt mit einem Accessor basierend auf die Benutzerdatensatz-Klasse `CArtists`. Öffnet eine Verbindung, wird eine Sitzung für die Verbindung geöffnet und die Tabelle in der Sitzung geöffnet.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
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