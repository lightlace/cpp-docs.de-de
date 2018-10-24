---
title: Debuggen des Anbieters | Microsoft-Dokumentation
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
ms.openlocfilehash: fc4461bb29bb9b9c706177c4dcd2134d37d697e0
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989904"
---
# <a name="debugging-your-provider"></a>Debuggen des Anbieters

Es gibt zwei Möglichkeiten zum Debuggen von Ihrem Anbieters:  
  
- Da der Anbieter im Prozess erstellt wurden, können Sie normalerweise mit Hilfe der OLE DB-Consumervorlagen und einen Einzelschritt in den Anbieter erstellen.  
  
- Sie können das ITEST-Dienstprogramm verwenden, das mit Visual C++ enthalten ist.  
  
## <a name="to-use-the-itest-utility"></a>Verwenden des Dienstprogramms ITEST  
  
1. Öffnen Sie das Anbieterprojekt.  
  
1. Auf der **Projekte** Menü klicken Sie auf **Einstellungen**.  
  
1. In der **Eigenschaftenseiten** Dialogfeld klicken Sie auf die **Debuggen** Registerkarte.  
  
1. In der **ausführbare Datei für Debugsitzung** wählen das ITEST.  
  
1. Legen Sie Haltepunkte fest, und klicken Sie dann wie gewohnt debuggen.  
  
## <a name="see-also"></a>Siehe auch  

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)