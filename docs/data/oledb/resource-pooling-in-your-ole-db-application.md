---
title: Ressourcenpooling in OLE DB-Anwendungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ece7ce128251f66360566c9b1965466352c4e493
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-pooling-in-your-ole-db-application"></a>Ressourcenpooling in OLE DB-Anwendungen
Um in Ihrer Anwendung nutzen zu können, stellen Sie sicher, OLE DB-Dienste werden aufgerufen, durch Abrufen der Datenquelle über **IDataInitialize** oder **IDBPromptInitialize**. Wenn Sie direkt `CoCreateInstance` zum Aufrufen des Anbieters basierend auf den Anbieter CLSID keine OLE DB-Dienste aufgerufen werden.  
  
 Der OLE DB-Dienste verwalten Pools verbundenen Datenquellen so lange als Verweis auf **IDataInitialize** oder **IDBPromptInitialize** gespeicherte oder so lange wie eine Verbindung verwendet wird. Pools werden auch automatisch innerhalb einer Umgebung COM+ 1.0 Services oder Internet Information Services (IIS) verwaltet. Wenn Ihre Anwendung Pooling von außerhalb einer COM+ 1.0 Services oder IIS-Umgebung nutzt, sollten Sie einen Verweis auf halten **IDataInitialize** oder **IDBPromptInitialize** oder mindestens eine festhalten Verbindung. Um sicherzustellen, dass der Pool nicht zerstört ist, wenn die letzte Verbindung durch die Anwendung veröffentlicht wird, behalten Sie den Verweis, oder warten Sie, um die Verbindung für die Lebensdauer der Anwendung.  
  
 OLE DB-Dienste zu identifizieren, den Pool, von dem die Verbindung zu dem Zeitpunkt gezeichnet wird, die `Initialize` aufgerufen wird. Nachdem die Verbindung aus einem Pool gezeichnet wird, kann es in einen anderen Ressourcenpool verschoben werden. Vermeiden Sie daher, Dinge in Ihrer Anwendung, die Initialisierungsinformationen für die, wie ein Aufruf ändern `UnInitialize` oder zum Aufrufen von `QueryInterface` für eine anbieterspezifische Schnittstelle vor dem Aufruf `Initialize`. Außerdem Verbindungen mit einem Aufforderungswert außer **DBPROMPT_NOPROMPT** sind nicht in einem Pool zusammengefasst. Allerdings kann die Initialisierungszeichenfolge aus eine Verbindung mit der Aufforderung abgerufen verwendet werden, um zusätzliche gepoolte Verbindungen mit derselben Datenquelle herzustellen.  
  
 Einige Anbieter müssen eine separate Verbindung für jede Sitzung machen. Diese zusätzlichen Verbindungen müssen separat an der verteilten Transaktion eingetragen werden, sofern vorhanden. OLE DB-Dienste werden zwischengespeichert und wiederverwendet eine einzelne Sitzung pro Datenquelle, aber wenn die Anwendung mehr als eine Sitzung zu einem Zeitpunkt aus einer einzelnen Datenquelle anfordert, wird der Anbieter zusätzliche Verbindungen herstellen und auf diese Weise zusätzliche transaktionseintragungen, die Enden nicht in einem Pool zusammengefasst. Es ist eigentlich eine effizientere zum Erstellen von einer anderen Datenquelle für jede Sitzung in einer Umgebung in einem Pool zusammengefasste, als mehrere Sitzungen aus einer einzelnen Datenquelle zu erstellen.  
  
 Schließlich, da ADO erstellt automatisch die Verwendung des OLE DB-Dienste können ADO, um Verbindungen herzustellen und das Verbindungspooling und Eintragung geschieht automatisch.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Ressourcenpooling und -Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)