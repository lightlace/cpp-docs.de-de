---
title: "Dual Interfaces and Events"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "duale Schnittstellen, Ereignisse"
  - "Ereignisse [C++], duale Schnittstellen"
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Dual Interfaces and Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl es möglich ist, eine Ereignisschnittstelle als dual entwerfen, gibt es einige gute entwicklungsspezifischen Gründe, nicht erforderlich.  Der grundlegende Grund ist, dass die Quelle des Ereignisses nur das Ereignis zum vtable oder über `Invoke` auslöst, nicht beide.  Wenn die Ereignisquelle das Ereignis als direkter vtable Methodenaufruf auslöst, werden die `IDispatch`\-Methoden nie verwendet und es ist klar, dass die Schnittstelle eine reine vtable Schnittstelle worden sein sollte.  Wenn die Ereignisquelle das Ereignis als Aufruf `Invoke` auslöst, werden die Methoden nie verwendet und es ist klar, dass die Schnittstelle eine Dispatchschnittstelle worden sein sollte.  Wenn Sie die Ereignisschnittstellen wie verdoppeln definieren, werden Sie Clients erforderlich, Teil einer Schnittstelle implementieren, die nie verwendet wird.  
  
> [!NOTE]
>  Dieses Argument gilt nicht für duale Schnittstellen, im Allgemeinen zu.  Von einer Implementierungsperspektive sind verdoppelt eine schnelle, einfache und Well\-unterstützte Methode der Implementierung von Schnittstellen, die einer großen Zahl von Clients verfügbar sind.  
  
 Es gibt weitere Gründe, duale Ereignisschnittstellen zu vermeiden, Visual Basic unterstützen weder noch Internet Explorer sie.  
  
## Siehe auch  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)