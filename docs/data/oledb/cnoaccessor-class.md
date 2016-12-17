---
title: "CNoAccessor-Klasse"
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
  - "ATL::CNoAccessor"
  - "CNoAccessor"
  - "ATL.CNoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoAccessor-Klasse"
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CNoAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kann als Vorlagenargument \(`TAccessor`\) für Vorlagenklassen, wie `CCommand` und `CTable` verwendet werden, die ein Accessorklassenargument benötigen.  
  
## Syntax  
  
```  
class CNoAccessor  
```  
  
## Hinweise  
 Verwenden Sie `CNoAccessor` als Vorlagenargument, wenn Sie die Klasse Parameter oder Ausgabespalten nicht unterstützen soll.  
  
 `CNoAccessor` implementiert die folgenden Stubmethoden, die jeweils anderen Accessorklassenmethoden entsprechen:  
  
-   \-**BindColumns** ausführen zu den Accessoren.  
  
-   `BindParameters`\-Bindungen die erstellten Parameter an Spalten.  
  
-   **Binden** stellt \- Bindungen erstellt.  
  
-   \-**Schließen** enthält den Accessor.  
  
-   `ReleaseAccessors`\-Versionen die Accessoren erstellt durch die Klasse.  
  
-   `FreeRecordMemory` \- Gibt alle Spalten im aktuellen Datensatz frei, die freigegeben werden müssen.  
  
-   `GetColumnInfo` \- Ruft Spalteninformationen vom geöffneten Rowsets ab.  
  
-   `GetNumAccessors` \- Ruft die Anzahl der den Accessoren ab, die von der Klasse erstellt werden.  
  
-   `IsAutoAccessor` \- Gibt true zurück, wenn Daten automatisch den Accessor während eines Verschiebungsvorgangs abgerufen werden.  
  
-   `GetHAccessor` \- Ruft das Accessorhandle eines angegebenen Accessor ab.  
  
-   `GetBuffer` \- Ruft den Zeiger auf Lesezeichenpuffer ab.  
  
-   **NoBindOnNullRowset** \- verhindert Datenbindung für leere Rowsets.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)