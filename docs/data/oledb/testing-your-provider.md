---
title: Testen des Anbieters | Microsoft-Dokumentation
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
ms.openlocfilehash: 04687ed080013d9ae96a11eda32e060c02c61dec
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081980"
---
# <a name="testing-your-provider"></a>Testen des Anbieters

Bevor Sie einen Anbieter freigeben, sollten Sie die folgenden Tests in der angegebenen Reihenfolge ausführen. Diese Tests sicher, dass die Anbieterfunktionen ordnungsgemäß für die meisten möglichen Benutzer.  
  
1. Testen Sie den Anbieter mit einem [Consumer](../../data/oledb/creating-an-ole-db-consumer.md) der OLE DB-Consumervorlagen geschriebene Anwendung. Der Testconsumer sollte alle Funktionsbereiche des Anbieters (Gesamter Code, die Sie hinzugefügt oder geändert) abdecken.  
  
1. Testen Sie den Anbieter, die mit einer Consumeranwendung, die mit ADO geschrieben wurden. Die meisten Entwickler (insbesondere Microsoft Visual Basic und Microsoft C#-Entwickler) verwenden ADO- oder ADO.NET-Objekt für Consumer-Anwendungen. Der Testconsumer sollte alle Funktionsbereiche des Anbieters behandelt. Ein Beispiel für eine ADO-Consumer-Anwendung, finden Sie unter [ADO-Codebeispiele in Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx).  
  
1. Führen Sie die OLE DB-Konformitätstests (einschließlich der ADO-Konformitätstests), um sicherzustellen, dass es sich bei Ihrem Anbieter die Ebene 0-standard für OLE DB-Anbieter erfüllt. (Eine Erläuterung der Ebene 0, suchen Sie nach "OLE DB-Ebene 0-Konformitätstests" am [OLE DB Programmer's Guide](/previous-versions/windows/desktop/ms713643). Diese Tests und die zugehörige Dokumentation sind in Visual C++ in das Data Access SDK enthalten. Diese Tests auch dabei helfen, um sicherzustellen, dass es sich bei Ihrem Anbieter ausgeführt wird, gut, wenn Sie von anderen aggregiert [-Dienstanbieter](../../data/oledb/ole-db-resource-pooling-and-services.md) und sind besonders nützlich, wenn Sie ändern oder Hinzufügen von Eigenschaften. Weitere Informationen zu den Konformitätstests finden Sie unter der Readme-Datei für das Data Access SDK, der auf einem der Visual Studio-CDs befindet.  
  
## <a name="see-also"></a>Siehe auch  

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)