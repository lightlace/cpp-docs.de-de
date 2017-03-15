---
title: "Ausgeben einer parametrisierten Abfrage | Microsoft Docs"
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
  - "Parameterabfragen, Ausführen mit der CCommand-Klasse"
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ausgeben einer parametrisierten Abfrage
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das folgende Beispiel führt eine einfache parametrisierte Abfrage aus, die Datensätze mit einem Feld für das Alter \(mit einem Wert über 30\) aus einer Microsoft Access\-Datenbank abruft.  Zur Unterstützung der Parameter muss der Datensatz über eine zusätzliche Zuordnung verfügen.  Der folgende Code in einem ATL\-Projekt verwendet die `CCommand`\-Klasse anstelle der im vorherigen Beispiel [Durchlaufen eines einfachen Rowsets](../../data/oledb/traversing-a-simple-rowset.md) verwendeten `CTable`\-Klasse.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CCommand<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major   
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
session.Open(connection);  
  
// Set the parameter for the query  
artists.m_nAge = 30;  
artists.Open(session, "select * from artists where age > ?");  
  
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
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)