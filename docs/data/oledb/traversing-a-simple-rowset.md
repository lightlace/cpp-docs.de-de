---
title: "Durchlaufen eines einfachen Rowsets | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Accessoren [C++], Rowsets"
  - "Datenzugriff [C++], Rowsets"
  - "OLE DB-Consumer [C++], Datenbankattribute"
  - "Rowsets [C++], Aufrufen"
  - "Einfache Rowsets"
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Durchlaufen eines einfachen Rowsets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel sehen Sie eine schnelle und einfache Art des Datenbankzugriffs, die ohne Befehle auskommt.  Der folgende Consumercode in einem ATL\-Projekt ruft Datensätze aus einer Tabelle mit der Bezeichnung *Künstler* ab, die Teil einer Microsoft Access\-Datenbank ist. Hierzu wird der Microsoft\-OLE DB\-Anbieter für ODBC verwendet.  Der Code erstellt ein [CTable](../../data/oledb/ctable-class.md)\-Tabellenobjekt mit einem Accessor, der auf der Benutzerdatensatz\-Klasse `CArtists` basiert.  Er öffnet eine Verbindung, eine Sitzung über die Verbindung sowie die Tabelle in der Sitzung.  
  
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
  
 Der Benutzerdatensatz `CArtists` sieht wie folgt aus:  
  
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
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)