---
title: Testen des Anbieters
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: d7a3adad546834e2bdc80a695f4c3bf2259dc0ba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038316"
---
# <a name="testing-your-provider"></a>Testen des Anbieters

Bevor Sie einen Anbieter freigeben, sollten Sie die folgenden Tests, in der angegebenen Reihenfolge ausführen. Diese Tests angezeigt, die die Anbieterfunktionen ordnungsgemäß für die meisten möglichen Benutzer.

1. Testen Sie den Anbieter mit einem [Consumer](../../data/oledb/creating-an-ole-db-consumer.md) der OLE DB-Consumervorlagen geschriebene Anwendung. Der Testconsumer sollte alle Funktionsbereiche des Anbieters (Gesamter Code, der hinzugefügt oder geändert haben) abdecken.

1. Testen Sie den Anbieter, die mit einer Consumeranwendung, die mit ADO geschrieben wurden. Die meisten Entwickler (insbesondere Microsoft Visual Basic und Microsoft C#-Entwickler) verwenden ADO- oder ADO.NET-Objekt für Consumer-Anwendungen. Der Testconsumer sollte alle Funktionsbereiche des Anbieters behandelt. Ein Beispiel für eine ADO-Consumer-Anwendung, finden Sie unter [ADO-Codebeispiele in Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx).

1. Führen Sie die OLE DB-Konformitätstests (einschließlich der ADO-Konformitätstests), um anzugeben, dass es sich bei Ihrem Anbieter die Ebene 0-standard für OLE DB-Anbieter erfüllt. (Eine Erläuterung der Ebene 0, suchen Sie nach **OLE DB-Konformitätstests Ebene 0** am [OLE DB Programmer's Guide](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Diese Tests und die zugehörige Dokumentation sind in Visual C++ in das Data Access SDK enthalten. Diese Tests können sich auch an, dass es sich bei Ihrem Anbieter ausgeführt wird, gut, wenn Sie von anderen aggregiert [-Dienstanbieter](../../data/oledb/ole-db-resource-pooling-and-services.md) und sind besonders nützlich, wenn Sie ändern oder Hinzufügen von Eigenschaften. Weitere Informationen zu den Konformitätstests finden Sie unter der Readme-Datei für das Data Access SDK, der auf einem der Visual Studio-CDs befindet.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)