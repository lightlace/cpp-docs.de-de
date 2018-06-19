---
title: Einführung in COM | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 938d0c45cae5ec9a2988f77f539af1a3d5513b83
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356174"
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

