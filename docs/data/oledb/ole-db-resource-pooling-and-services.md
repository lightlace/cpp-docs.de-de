---
title: "OLE&#160;DB-Ressourcenpooling und -Dienste"
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
  - "OLE DB-Anbieter, Ressourcenpooling"
  - "OLE DB-Dienste [OLE DB]"
  - "OLE DB-Dienste [OLE DB], Anbieteranforderungen"
  - "OLE DB, Ressourcenpooling"
  - "Ressourcenpooling [OLE DB], Anbieteranforderungen"
  - "Serviceanbieter [OLE DB]"
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# OLE&#160;DB-Ressourcenpooling und -Dienste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Damit der Anbieter einwandfrei mit OLE DB\-Pooling oder anderen OLE DB\-Diensten funktioniert, muss er das Aggregieren sämtlicher Objekte unterstützen.  Diese Anforderung gilt für OLE DB\-Anbieter, Version 1.5, oder höher.  Dieser Faktor ist für die optimale Nutzung der Dienste unerlässlich.  Anbieter, die keine Aggregierung unterstützen, können weder in einem Pool zusammengefasst werden noch zusätzliche Dienste nutzen.  
  
 Zum Pooling müssen Anbieter das Freethreadmodell unterstützen.  Das Threadmodell des Anbieters wird vom Ressourcenpool anhand der **DBPROP\_THREADMODEL**\-Eigenschaft ermittelt.  
  
 Wenn der Anbieter über einen globalen Verbindungszustand verfügt, der sich während des Initialisierungszustands der Datenquelle ändern kann, sollte er die neue **DBPROP\_RESETDATASOURCE**\-Eigenschaft unterstützen.  Diese Eigenschaft wird vor der Wiederverwendung einer Verbindung aufgerufen und bietet dem Anbieter die Möglichkeit, seinen Zustand vor der erneuten Verwendung zu bereinigen.  Falls ein verbindungsabhängiger Zustand vom Anbieter nicht bereinigt werden kann, kann **DBPROPSTATUS\_NOTSETTABLE** für die Eigenschaft zurückgegeben werden, sodass die Verbindung nicht erneut verwendet wird.  
  
 Anbieter, die mit einer Remotedatenbank verbunden werden und wahlweise feststellen können, ob diese Verbindung unterbrochen wird oder nicht, sollten die **DBPROP\_CONNECTIONSTATUS**\-Eigenschaft unterstützen.  Diese Eigenschaft ermöglicht es den OLE DB\-Diensten, inaktive Leitungen zu ermitteln und sicherzustellen, dass sie nicht an den Pool zurückgegeben werden.  
  
 Die automatische Eintragung von Transaktionen funktioniert letztendlich nur dann, wenn sie auf derselben Ebene wie das Pooling implementiert wird.  Anbieter, die selbst die automatische Eintragung von Transaktionen unterstützen, sollten die Deaktivierung dieser Eintragung ermöglichen, indem sie die **DBPROP\_INIT\_OLEDBSERVICES**\-Eigenschaft zur Verfügung stellen, und die Eintragung deaktivieren, wenn **DBPROPVAL\_OS\_TXNENLISTMENT** deaktiviert wird.  
  
## Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)