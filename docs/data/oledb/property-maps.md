---
title: "Eigenschaftenzuordnungen"
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
  - "Zuordnungen, Eigenschaft"
  - "OLE DB-Anbieter, Eigenschaften"
  - "Eigenschaftenzuordnungen"
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenzuordnungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neben Sitzungs\-, Rowset\- und optionalen Befehlsobjekten unterstützt jeder Anbieter eine oder mehrere Eigenschaften.  Diese Eigenschaften werden in Eigenschaftenzuordnungen definiert, die in den vom OLE DB\-Anbieter\-Assistenten erstellten Headerdateien enthalten sind.  Jede Headerdatei enthält eine Zuordnung für die Eigenschaften in der OLE DB\-Eigenschaftengruppe, die für eines oder mehrere in dieser Datei festgelegten Objekte definiert wurde.  In der Headerdatei mit dem Datenquellenobjekt befindet sich zusätzlich die Eigenschaftenzuordnung für die [DataSource\-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx).  **Session.h** enthält die Eigenschaftenzuordnung für die [Session\-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms714221.aspx).  Rowset\- und Befehlsobjekte befinden sich in derselben Headerdatei, *projectname*RS.h.  Diese Eigenschaften gehören zur Gruppe der [Rowset\-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms711252.aspx).  
  
## Siehe auch  
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)