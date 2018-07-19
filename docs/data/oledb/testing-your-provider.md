---
title: Testen des Anbieters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c35b1391e5b8cbfb073255b3680b0376d19ae040
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104788"
---
# <a name="testing-your-provider"></a>Testen des Anbieters
Bevor Sie einen Anbieter freigeben, sollten Sie die folgenden Tests in der angegebenen Reihenfolge ausführen. Diese Tests sicher, dass der Anbieterfunktionen ordnungsgemäß für die meisten potenziellen Benutzer.  
  
1.  Testen Sie den Anbieter mit einem [Consumer](../../data/oledb/creating-an-ole-db-consumer.md) Anwendung, die mit dem OLE DB-Consumervorlagen geschrieben. Der Testconsumer sollte alle Funktionsbereiche des Anbieters (den gesamten hinzugefügten oder geänderten Code) abdecken.  
  
2.  Testen Sie den Anbieter mithilfe einer mit ADO geschriebenen Consumeranwendung. Die meisten Entwickler (insbesondere Microsoft Visual Basic und Microsoft C#-Entwickler) verwenden ADO- oder ADO.NET-Objekt für Consumer-Anwendungen. Der Testconsumer sollte alle Funktionsbereiche des Anbieters abdecken. Ein Beispiel einer ADO-Consumer-Anwendung finden Sie unter [ADO-Codebeispiele in Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx).  
  
3.  Führen Sie die OLE DB-Konformitätstests (einschließlich der ADO-Konformitätstests), um sicherzustellen, dass der Anbieter die Ebene-0-standard für OLE DB-Anbieter erfüllt. (Eine Erläuterung der Ebene 0, suchen Sie nach "OLE DB-Ebene 0-Konformitätstests" am [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/p/?linkid=121548). Diese Tests und die zugehörige Dokumentation sind im Lieferumfang von Visual C++ in das Data Access SDK. Diese Tests können Sie auch sicherstellen, dass der Anbieter ausgeführt wird, gut, wenn Sie von anderen aggregiert [-Dienstanbieter](../../data/oledb/ole-db-resource-pooling-and-services.md) und sind besonders nützlich, wenn Sie ändern oder Hinzufügen von Eigenschaften. Weitere Informationen zu den Konformitätstests finden Sie unter der Readme-Datei für das Data Access SDK, die sich auf einem der Visual Studio-CDs befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)