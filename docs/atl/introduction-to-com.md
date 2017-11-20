---
title: "Einführung in COM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 236222296b270fe52f43f42a823e3f6f790d08ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="introduction-to-com"></a>Einführung in COM
COM ist das grundlegende "Object Model", auf welche ActiveX-Steuerelemente und OLE erstellt werden. COM einem Objekt Gelegenheit zu seiner Funktionalität mit anderen Komponenten und zum Hosten von Anwendungen verfügbar zu machen. Es definiert, wie das Objekt selbst verfügbar macht und Funktionsweise dieses Offenlegen über Prozesse und Netzwerke hinweg. COM definiert auch die Lebensdauer des Objekts.  
  
 Die folgenden Konzepte sind für COM von grundlegender Wichtigkeit:  
  
-   [Schnittstellen](../atl/interfaces-atl.md) – der Mechanismus, durch die ein Objekt seine Funktionalität verfügbar macht.  
  
-   [IUnknown](../atl/iunknown.md) – die grundlegende Schnittstelle, die auf dem alle anderen basieren. Es implementiert die verweiszählung und Abfragen von Mechanismen, die ausgeführt wird, über COM-Schnittstelle  
  
-   [Verweiszählung](../atl/reference-counting.md) – das Verfahren, mit dem ein Objekt (oder streng genommen eine Schnittstelle) entscheidet, wenn es nicht mehr verwendet wird und daher selbst entfernen.  
  
-   [QueryInterface](../atl/queryinterface.md) – die Methode verwendet, um ein Objekt für die jeweilige Schnittstelle abzufragen.  
  
-   [Marshalling](../atl/marshaling.md) – der Mechanismus, mit der Objekte in der gesamten Thread, Prozess und Netzwerkgrenzen, bei dem Speicherort Unabhängigkeit verwendet werden kann.  
  
-   [Aggregation](../atl/aggregation.md) – eine Möglichkeit, die in der ein Objekt vornehmen kann von einer anderen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM und ATL](../atl/introduction-to-com-and-atl.md)   
 [Das Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)

