---
title: Ressourcenpooling in OLE DB-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: c4e548d00f5772e41e0a725020cd2f279e3ab89b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479546"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>Ressourcenpooling in OLE DB-Anwendungen

Um in Ihrer Anwendung nutzen zu können, stellen Sie sicher, OLE DB-Dienste werden aufgerufen, indem Sie die Datenquelle über abrufen `IDataInitialize` oder `IDBPromptInitialize`. Wenn Sie direkt `CoCreateInstance` zum Aufrufen des Anbieters basierend auf der CLSID des Anbieters keine OLE DB-Dienste aufgerufen werden.

Pools verbundenen Datenquellen so lange wie ein Verweis auf die OLE DB-Dienste verwaltet, `IDataInitialize` oder `IDBPromptInitialize` ist unterbrochene oder so lange, wie eine Verbindung verwendet. Pools sind auch automatisch innerhalb einer Umgebung COM+ 1.0-Dienste oder (Internet Information Services, IIS) verwaltet. Wenn Ihre Anwendung außerhalb einer COM+ 1.0 Services oder IIS-Umgebung nutzt, sollten Sie einen Verweis auf halten `IDataInitialize` oder `IDBPromptInitialize` oder mindestens eine Verbindung daran festhalten. Um sicherzustellen, dass der Pool nicht zerstört wird, wenn die letzte Verbindung von der Anwendung veröffentlicht wird, behalten Sie den Verweis, oder halten Sie auf, um die Verbindung für die Lebensdauer der Anwendung.

OLE DB-Dienste zu identifizieren, den Pool, die von dem die Verbindung, die zum Zeitpunkt erstellt wird, `Initialize` aufgerufen wird. Nachdem die Verbindung aus einem Pool gezeichnet wird, kann es in einen anderen Pool verschoben werden. Vermeiden Sie daher, Dinge in Ihrer Anwendung, die Initialisierungsinformationen, wie ein Aufruf ändern `UnInitialize` oder Aufrufen `QueryInterface` für einen Anbieter spezifische Schnittstelle vor dem Aufruf `Initialize`. Darüber hinaus werden Verbindungen mit einem anderen DBPROMPT_NOPROMPT Eingabeaufforderung Wert nicht in einem Pool zusammengefasst. Allerdings kann die Initialisierungszeichenfolge aus eine Verbindung hergestellt wird, über die Eingabeaufforderung verwendet werden, um zusätzliche gepoolte Verbindungen mit derselben Datenquelle herzustellen.

Einige Anbieter müssen für jede Sitzung eine eigene Verbindung. Diese zusätzlichen Verbindungen müssen separat in der verteilten Transaktion eingetragen werden, sofern vorhanden. OLE DB-Dienste werden zwischengespeichert und eine einzigen Sitzung pro Datenquelle verwendet, aber wenn die Anwendung mehr als eine Sitzung zu einem Zeitpunkt von einer einzelnen Datenquelle anfordert, der Anbieter kann am Ende zusätzliche Verbindungen zu machen und zusätzliche transaktionseintragungen, die dies nicht in einem Pool zusammengefasst. Es ist tatsächlich eine effizientere Erstellung eine anderen Datenquelle, für jede Sitzung in einer Umgebung in einem Pool zusammengefasste, als mehrere Sitzungen aus einer einzelnen Datenquelle zu erstellen.

Schließlich, da ADO wird automatisch für die Verwendung von OLE DB Services, Sie können ADO verwenden, um Verbindungen herzustellen und das pooling und die Eintragung erfolgt automatisch.

## <a name="see-also"></a>Siehe auch

[OLE DB-Ressourcenpooling und -Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)