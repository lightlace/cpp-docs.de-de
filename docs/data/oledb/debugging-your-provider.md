---
title: Debuggen des Anbieters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c6258ddd3fd4317c608cb20486c364918fb5c73a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-your-provider"></a>Debuggen des Anbieters
Es gibt zwei Möglichkeiten zum Debuggen von Ihrem Anbieters:  
  
-   Da der Anbieter im Prozess erstellt werden, können Sie mithilfe der OLE DB-Consumervorlagen und einen Einzelschritt in den Anbieter normalerweise Consumercode erstellen.  
  
-   Sie können das ITEST-Hilfsprogramm verwenden, das mit Visual C++ enthalten ist.  
  
### <a name="to-use-the-itest-utility"></a>Zum Verwenden des Hilfsprogramms ITEST  
  
1.  Öffnen Sie das Anbieterprojekt.  
  
2.  Auf der **Projekte** Menü klicken Sie auf **Einstellungen**.  
  
3.  In der **Eigenschaftenseiten** (Dialogfeld), klicken Sie auf die **Debuggen** Registerkarte.  
  
4.  In der **ausführbare Datei für die Debugsitzung** wählen das ITEST.  
  
5.  Legen Sie Haltepunkte, und klicken Sie dann wie üblich Debuggen.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)