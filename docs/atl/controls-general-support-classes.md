---
title: "Controls: General Support Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [ATL]"
  - "general support classes"
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Controls: General Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen bieten Unterstützung für allgemeine ATL\-Steuerelementen:  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) besteht aus Hilfsfunktionen und Datenmember, die zu ATL unbedingt notwendig sind, steuert.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) stellt die Methoden, die für Steuerelemente erforderlich sind.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) stellt die wichtigsten Methoden, durch die ein Container ein Steuerelement ist.  Verwaltet das Einschalten und Ausschalten direkter Steuerelemente.  
  
-   [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) Mähdrescherinitialisierung in einen einzelnen aufrufen, um von Containern zu unterstützen, wenn Ladensteuerelemente Verzögerungen zu vermeiden.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) stellt minimale Mausinteraktion für ein andernfalls inaktives Steuerelement.  
  
## Beispielprogramm  
 [ATLFire](../top/visual-cpp-samples.md)  
  
## Verwandte Elemente  
 [ATL\-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)