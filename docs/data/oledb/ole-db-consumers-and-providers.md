---
title: "OLE&#160;DB-Consumer und -Anbieter | Microsoft Docs"
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
  - "OLE DB-Consumer"
  - "OLE DB-Consumer, OLE DB-Datenarchitektur"
  - "OLE DB-Anbieter"
  - "OLE DB-Anbieter, OLE DB-Datenarchitektur"
  - "OLE DB, Datenmodell"
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE&#160;DB-Consumer und -Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Architektur verwendet das Modell von Consumern und Anbietern.  Ein Consumer stellt eine Anfrage nach Daten.  Ein Anbieter beantwortet diese Anfragen, indem er Daten in ein tabellarisches Format einfügt und sie an den Consumer übermittelt.  Jeder mögliche Aufruf durch den Consumer muss im Anbieter implementiert sein.  
  
 Technisch definiert ist ein Consumer jede Art von System oder Anwendungscode \(nicht notwendigerweise eine OLE DB\-Komponente\), dessen Datenzugriff über OLE DB\-Schnittstellen erfolgt.  Die Schnittstellen sind in einem Anbieter implementiert.  Ein Anbieter ist jede Art von Softwarekomponente, die OLE DB\-Schnittstellen so implementiert, dass der Datenzugriff gekapselt und anderen Objekten \(d. h. Consumern\) verfügbar gemacht wird.  
  
 Betrachtet man die Rollenverteilung, ruft ein Consumer Methoden an OLE DB\-Schnittstellen auf. Ein OLE DB\-Anbieter implementiert die benötigten OLE DB\-Schnittstellen.  
  
 OLE DB vermeidet die Begriffe Client und Server, da diese Rollen nicht immer und insbesondere in n\-stufigen Situationen nicht sinnvoll sind.  Ein Consumer könnte eine Komponente auf einer Ebene sein, die einer anderen Komponente dient. Dies eine Client\-Komponente zu nennen wäre also irreführend.  Darüber hinaus verhält sich ein Anbieter manchmal eher wie ein Datenbanktreiber als ein Server.  
  
## Siehe auch  
 [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB\-Programmierung](../../data/oledb/ole-db-programming-overview.md)