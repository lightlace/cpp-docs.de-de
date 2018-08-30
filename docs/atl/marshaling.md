---
title: Marshalling | Microsoft-Dokumentation
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
ms.openlocfilehash: ac4bb35d29d74f0e66337dc6c3999df66a63d254
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212690"
---
# <a name="marshaling"></a>Marshalling
Das Verfahren der COM-Marshalling kann Schnittstellen verfügbar gemacht werden, von einem Objekt in einem Prozess in einem anderen Prozess verwendet werden. Marshalling COM stellt Code bereit (oder verwendet den von der Implementierung der Schnittstelle bereitgestellten Code) Parameter einer Methode in einem Format packen, die zwischen Prozessen (sowie über das Netzwerk für laufende Prozesse auf anderen Computern) verschoben werden können und Entpacken Sie diese Parameter am anderen Ende. Ebenso muss COM dieselben Schritte bei der Rückgabe aus dem Aufruf ausführen.  
  
> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle zur Verfügung gestellt, von einem Objekt im selben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Marshalling von Details](/windows/desktop/com/marshaling-details)

