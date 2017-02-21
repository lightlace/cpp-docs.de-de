---
title: "Ressourcenpooling in OLE&#160;DB-Anwendungen | Microsoft Docs"
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
  - "OLE DB-Anbieter, Ressourcenpooling"
  - "OLE DB-Dienste [OLE DB], Ressourcenpooling"
  - "OLE DB, Ressourcenpooling"
  - "Ressourcenpooling [OLE DB], Dienste"
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ressourcenpooling in OLE&#160;DB-Anwendungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um die Poolingfunktion in der Anwendung optimal zu nutzen, müssen Sie sicherstellen, dass OLE DB\-Dienste aufgerufen werden, indem die Datenquelle über **IDataInitialize** oder **IDBPromptInitialize** empfangen wird.  Wenn Sie den Anbieter mittels der CLSID des Anbieters direkt über `CoCreateInstance` aufrufen, werden keine OLE DB\-Dienste aktiviert.  
  
 Pools verbundener Datenquellen werden von den OLE DB\-Diensten verwaltet, so lange ein Verweis auf **IDataInitialize** oder **IDBPromptInitialize** vorhanden ist bzw. so lange eine Verbindung in Gebrauch ist.  Pools werden innerhalb einer Umgebung mit COM\+ 1.0\-Diensten oder Internetinformationsdiensten \(IIS\) auch automatisch verwaltet.  Wenn die Anwendung Poolingfunktionen außerhalb einer COM\+ 1.0\-Dienste\- oder IIS\-Umgebung nutzt, sollten Sie einen Verweis auf **IDataInitialize** oder **IDBPromptInitialize** beibehalten oder zumindest eine Verbindung aktiv lassen.  Um sicherzustellen, dass der Pool erhalten bleibt, nachdem die letzte Verbindung durch die Anwendung freigegeben wurde, behalten Sie den Verweis bei oder lassen die Verbindung während der Lebensdauer der Anwendung aktiviert.  
  
 Beim Aufrufen von `Initialize` wird der Pool, aus dem die Verbindung erstellt wird, von den OLE DB\-Diensten identifiziert.  Nachdem die Verbindung aus einem Pool erstellt wurde, kann sie nicht mehr in einen anderen Pool verschoben werden.  Daher sollten Sie in der Anwendung alle Schritte unterlassen, durch die die Initialisierungsinformationen geändert werden. Dazu gehört das Aufrufen von `UnInitialize` oder von `QueryInterface` für eine anbieterspezifische Schnittstelle, bevor `Initialize` aufgerufen wird.  Außerdem werden Verbindungen, die mit einem anderen Aufforderungswert als **DBPROMPT\_NOPROMPT** eingerichtet wurden, nicht in den Pool aufgenommen.  Allerdings kann die Initialisierungszeichenfolge, die über eine Aufforderung aus einer Verbindung abgerufen wurde, verwendet werden, um zusätzliche Poolverbindungen mit derselben Datenquelle einzurichten.  
  
 Einige Anbieter müssen für jede Sitzung eine eigene Verbindung herstellen.  Diese zusätzlichen Verbindungen müssen in der verteilten Transaktion, sofern vorhanden, separat eingetragen werden.  Mithilfe der OLE DB\-Dienste werden Einzelsitzungen pro Datenquelle zwischengespeichert und wiederverwendet. Wenn von einer Anwendung jedoch gleichzeitig mehrere Sitzungen aus einer einzelnen Datenquelle angefordert werden, kann es vorkommen, dass der Anbieter zusätzliche Verbindungen herstellt und zusätzliche Transaktionseintragungen vornimmt, die nicht in den Pool aufgenommen werden.  Es ist effizienter, in einer Poolumgebung pro Sitzung eine separate Datenquelle anzulegen als mehrere Sitzungen aus einer einzelnen Datenquelle zu erstellen.  
  
 Da die OLE DB\-Dienste von ADO automatisch verwendet werden, können Sie mit ADO Verbindungen herstellen, während das Pooling und die Eintragungen automatisch erfolgen.  
  
## Siehe auch  
 [OLE DB\-Ressourcenpooling und \-Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)