---
title: Basisklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09879dbcc370df1468e181ffed830ab6297f5201
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="base-classes"></a>Basisklassen
Der Vererbungsprozess erstellt eine neue abgeleitete Klasse, die aus den Membern der Basisklasse(n) besteht, zuzüglich aller neuer Member, die von der abgeleiteten Klasse hinzugefügt werden. Bei einer Mehrfachvererbung ist es möglich, ein Vererbungsdiagramm zu erstellen, in dem dieselbe Basisklasse Teil von mehr als einer der abgeleiteten Klassen ist. Die folgende Abbildung zeigt ein solches Diagramm.  
  
 ![Mehrere Instanzen einer Basisklasse](../cpp/media/vc38xn1.gif "vc38XN1")  
Mehrere Instanzen einzelner Basisklassen  
  
 In der Abbildung werden bildliche Darstellungen der Komponenten von `CollectibleString` und `CollectibleSortable` angezeigt. Allerdings gibt es die Basisklasse `Collectible` über den `CollectibleSortableString`-Pfad und den `CollectibleString`-Pfad in `CollectibleSortable`. Um diese Redundanz zu entfernen, können solche Klassen als virtuelle Basisklassen deklariert werden, wenn sie vererbt werden.  
  
