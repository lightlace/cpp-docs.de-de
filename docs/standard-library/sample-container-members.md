---
title: "Sample Container-Member | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "container-Klassen"
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Sample Container-Member
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
## Referenz  
  
## Typedefs  
  
|||  
|-|-|  
|[const\_iterator](../standard-library/container-class-const-iterator.md)|Beschreibt ein Objekt, das als konstanter Iterator für die gesteuerte Sequenz dienen kann.|  
|[const\_reference](../standard-library/container-class-const-reference.md)|Beschreibt ein Objekt, das als konstanten Verweis auf ein Element der Sequenz gesteuerten dienen kann.|  
|[const\_reverse\_iterator](../standard-library/container-class-const-reverse-iterator.md)|Beschreibt ein Objekt, das als konstanter umgekehrter Iterator für die gesteuerte Sequenz dienen kann.|  
|[difference\_type](../standard-library/container-class-difference-type.md)|Beschreibt ein Objekt, das den Unterschied zwischen den Adressen aller zwei Elemente in der Sequenz gesteuerten darstellen kann.|  
|[Iterator](../standard-library/container-class-iterator.md)|Beschreibt ein Objekt, das als Iterator für die gesteuerte Sequenz dienen kann.|  
|[Verweis](../standard-library/container-class-reference.md)|Beschreibt ein Objekt, das als Verweis auf ein Element der Sequenz gesteuerten dienen kann.|  
|[reverse\_iterator](../standard-library/container-class-reverse-iterator.md)|Beschreibt ein Objekt, das als umgekehrter Iterator für die gesteuerte Sequenz dienen kann.|  
|[size\_type](../standard-library/container-class-size-type.md)|Beschreibt ein Objekt, das die Länge jeder gesteuerten Sequenz darstellen kann.|  
|[value\_type](../standard-library/container-class-value-type.md)|Fungiert ein Synonym für den Vorlagenparameter **Ty**.|  
  
## Memberfunktionen  
  
|||  
|-|-|  
|[begin](../standard-library/container-class-begin.md)|Gibt ein Iterator zurück, der beim ersten Element der Sequenz zeigt \(oder direkt über dem Ende eine leere Sequenz hinaus\).|  
|[clear](../standard-library/container-class-clear.md)|Ruft [Löschen](../standard-library/container-class-erase.md) auf \( [Starten](../standard-library/container-class-begin.md), [Ende](../standard-library/container-class-end.md)\).|  
|[empty](../standard-library/container-class-empty.md)|Gibt **true**  für eine leere gesteuerte Sequenz zurück.|  
|[end](../standard-library/container-class-end.md)|Gibt ein Iterator zurück, der nur über das Ende der Sequenz hinaus zeigt.|  
|[Löschen](../standard-library/container-class-erase.md)|Löscht ein Element.|  
|[max\_size](../standard-library/container-class-max-size.md)|Gibt die Länge der längsten Sequenz, die das Objekt steuern kann, in der konstanten Zeit unabhängig von der Länge gesteuerten der Sequenz zurück.|  
|[rbegin](../standard-library/container-class-rbegin.md)|Gibt einen umgekehrten Iterator, der direkt über dem Ende der Sequenz gesteuerten hinaus zeigt zurück und legt den Anfang der Rücksequenz fest.|  
|[rend](../standard-library/container-class-rend.md)|Die Memberfunktion gibt einem umgekehrten Iterator, der beim ersten Element der Sequenz zeigt \(oder direkt über dem Ende eine leere Sequenz hinaus\) zurück und legt das Ende der Rücksequenz fest.|  
|[size](../standard-library/container-class-size.md)|Gibt die Länge der gesteuerten Sequenz, in der konstanten Zeit unabhängig von der Länge gesteuerten der Sequenz zurück.|  
|[swap](../standard-library/container-class-swap.md)|Vertauscht die gesteuerten Sequenzen zwischen **\*this** und `_Right`.|