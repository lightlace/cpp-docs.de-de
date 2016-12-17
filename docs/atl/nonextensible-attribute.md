---
title: "nonextensible Attribute"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "duale Schnittstellen, nonextensible attribute"
  - "nonextensible attribute"
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# nonextensible Attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird \(das heißt, stellen Methoden oder Eigenschaften nicht über **IDispatch::Invoke** bereit, die nicht über das vtable verfügbar sind\), sollten Sie das **nonextensible**\-Attribut auf die Schnittstellendefinition anwenden.  Dieses Attribut stellt Informationen zu den Clientsprachen bereit \(wie Visual Basic\), um die Überprüfung des vollständigen Code zur Kompilierzeit erforderlich.  Wenn dieses Attribut nicht angegeben wird, bleiben möglicherweise Fehler im Clientcode bis zur Laufzeit ausgeblendet.  
  
 Weitere Informationen zum **nonextensible**\-Attribut und ein Beispiel, finden Sie unter [nicht erweiterbar](../windows/nonextensible.md).  
  
## Siehe auch  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)