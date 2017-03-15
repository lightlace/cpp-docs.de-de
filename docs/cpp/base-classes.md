---
title: "Basisklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basisklassen"
  - "Basisklassen, Virtuell"
  - "Abgeleitete Klassen, Mehrere Basen"
  - "Vererbung, Mehrere"
  - "Mehrfachvererbung, Basisklassen"
  - "Virtuelle Basisklassen"
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Basisklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Vererbungsprozess erstellt eine neue abgeleitete Klasse, die aus den Membern der Basisklasse\(n\) besteht, zuzüglich aller neuer Member, die von der abgeleiteten Klasse hinzugefügt werden.  Bei einer Mehrfachvererbung ist es möglich, ein Vererbungsdiagramm zu erstellen, in dem dieselbe Basisklasse Teil von mehr als einer der abgeleiteten Klassen ist.  Die folgende Abbildung zeigt ein solches Diagramm.  
  
 ![Mehrere Instanzen einer Basisklasse](../cpp/media/vc38xn1.png "vc38XN1")  
Mehrere Instanzen einzelner Basisklassen  
  
 In der Abbildung werden bildliche Darstellungen der Komponenten von `CollectibleString` und `CollectibleSortable` angezeigt.  Allerdings gibt es die Basisklasse `Collectible` über den `CollectibleSortableString`\-Pfad und den `CollectibleString`\-Pfad in `CollectibleSortable`.  Um diese Redundanz zu entfernen, können solche Klassen als virtuelle Basisklassen deklariert werden, wenn sie vererbt werden.  
  
 Weitere Informationen zum Deklarieren von virtuellen Basisklassen und dazu, wie Objekte mit virtuellen Basisklassen zusammengesetzt werden, finden Sie unter [Virtuelle Basisklassen](../misc/virtual-base-classes.md).  
  
## Siehe auch  
 [Übersicht über abgeleitete Klassen](../misc/overview-of-derived-classes.md)