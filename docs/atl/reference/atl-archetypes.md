---
title: "ATL Archetypes"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "archetype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, archetypes"
ms.assetid: 809fb0af-c0f4-4cc0-b5bc-afe3de5d9722
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Archetypes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Kontext ist ein *Prototyp* theoretische eine Klasse, die eine Auflistung Methoden, statische Datenmember, Funktionen, Typdefinitionen oder andere Features.  Der Prototyp enthält auch eine Beschreibung der Semantik, die erforderlich ist, die Klasse zu erstellen oder verwenden, um ein bestimmtes Konzept darzustellen.  Klassen, die den Prototyp imitieren, indem die gleichen Funktionen bereitstellen, stellen das Konzept dar und können immer zusammen mit verwendet werden den Prototyp können verwendet werden.  
  
 Prototypen sind in C\+\+ für die Beschreibung der Funktionen der gültigen Werte für Vorlagenparameter hilfreich.  Der Designer der Vorlage weist eine eindeutige Vorstellung von erforderlichen und genügend Funktionen des Vorlagenparameters, und der Compiler setzt die syntaktischen Forderungen zur Buildzeit durch, aber der Benutzer einer Vorlage erfordert Dokumentation, um die Semantik zu beschreiben und die Beziehungen zwischen den eindeutig formuliert werden Prototypen und Klassen zu ermöglichen.  
  
 Beispiele von Prototypen in der C\+\+\-Standardbibliothek sind die verschiedenen Typen von Iterators und des Containers.  Diese Prototypen werden in den Themen [Iterator\-Konventionen](../../standard-library/iterators.md) und [STL\-Container](../../standard-library/stl-containers.md) beschrieben.  
  
 ATL\-Server definiert die folgenden Prototypen:  
  
|Name|Description|  
|----------|-----------------|  
|[Worker\-Prototyp](../../atl/reference/worker-archetype.md)|Klassen, die an den *Workerprototyp* entsprechen, stellen den Code zu den Prozessarbeitsaufgaben bereit, die in einem Threadpool in die Warteschlange gestellt werden.|  
  
## Siehe auch  
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)