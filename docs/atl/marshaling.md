---
title: Marshalling | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b8b82d5369aa536dab638efa379089325d10b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360099"
---
# <a name="marshaling"></a>Marshalling
Das Verfahren COM-Marshalling kann Schnittstellen verfügbar gemacht werden, indem Sie ein Objekt in einem Prozess in einem anderen Prozess verwendet werden. Marshalling COM stellt Code bereit (oder Code bereitgestellt, die von der Implementierung der Schnittstelle verwendet), damit Parameter einer Methode in ein Format zu packen, die prozessübergreifend (sowie über das Netzwerk auf andere Computer ausgeführten Prozesse) verschoben werden können und Entpacken Sie diese Parameter am anderen Ende. Ebenso muss COM dieselben Schritte für die Rückgabe aus dem Aufruf ausführen.  
  
> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle, die von einem Objekt bereitgestellt in demselben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Marshalling von Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)

