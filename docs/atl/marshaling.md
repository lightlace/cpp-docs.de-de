---
title: Marshalling | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec8c85606f0f0ef3de67a61181ead6537fde179e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="marshaling"></a>Marshalling
Das Verfahren COM-Marshalling kann Schnittstellen verfügbar gemacht werden, indem Sie ein Objekt in einem Prozess in einem anderen Prozess verwendet werden. Marshalling COM stellt Code bereit (oder Code bereitgestellt, die von der Implementierung der Schnittstelle verwendet), damit Parameter einer Methode in ein Format zu packen, die prozessübergreifend (sowie über das Netzwerk auf andere Computer ausgeführten Prozesse) verschoben werden können und Entpacken Sie diese Parameter am anderen Ende. Ebenso muss COM dieselben Schritte für die Rückgabe aus dem Aufruf ausführen.  
  
> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle, die von einem Objekt bereitgestellt in demselben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Marshalling von Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)

