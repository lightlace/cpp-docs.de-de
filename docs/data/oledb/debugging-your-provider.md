---
title: Debuggen des Anbieters | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 03f8ebdf74dfcf8962b4308c467984d0a63c7968
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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