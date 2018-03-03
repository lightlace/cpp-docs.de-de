---
title: Basisklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a83507d89c17aab363f986dab3ff4d84c4c916
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="base-classes"></a>Basisklassen
Der Vererbungsprozess erstellt eine neue abgeleitete Klasse, die aus den Membern der Basisklasse(n) besteht, zuzüglich aller neuer Member, die von der abgeleiteten Klasse hinzugefügt werden. Bei einer Mehrfachvererbung ist es möglich, ein Vererbungsdiagramm zu erstellen, in dem dieselbe Basisklasse Teil von mehr als einer der abgeleiteten Klassen ist. Die folgende Abbildung zeigt ein solches Diagramm.  
  
 ![Mehrere Instanzen einer Basisklasse](../cpp/media/vc38xn1.gif "vc38XN1")  
Mehrere Instanzen einzelner Basisklassen  
  
 In der Abbildung werden bildliche Darstellungen der Komponenten von `CollectibleString` und `CollectibleSortable` angezeigt. Allerdings gibt es die Basisklasse `Collectible` über den `CollectibleSortableString`-Pfad und den `CollectibleString`-Pfad in `CollectibleSortable`. Um diese Redundanz zu entfernen, können solche Klassen als virtuelle Basisklassen deklariert werden, wenn sie vererbt werden.  
  
