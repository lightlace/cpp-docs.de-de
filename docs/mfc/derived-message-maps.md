---
title: Abgeleitete Meldungszuordnungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e780d411e62d1347d8286f86b45df864b0fcdb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="derived-message-maps"></a>Abgeleitete Meldungszuordnungen
Während Nachricht behandeln, überprüfen eine Nachricht von der Klasse ist die Zuordnung nicht das Ende des Textabschnitts meldungszuordnung. Was geschieht, wenn Klasse `CMyView` (abgeleitet von `CView`) wurde kein übereinstimmenden Eintrag für eine Nachricht  
  
 Beachten Sie, dass `CView`, die Basisklasse von `CMyView`, abgeleitet wird wiederum `CWnd`. Daher `CMyView` *ist* eine `CView` und *ist* eine `CWnd`. Jede dieser Klassen verfügt über eine eigene meldungszuordnung. Die Abbildung "Eine Hierarchie anzeigen" unten zeigt die hierarchische Beziehung von den Klassen, sondern bleiben Beachten Sie, dass ein `CMyView` Objekt stellt ein einzelnes Objekt mit den Eigenschaften von allen drei Klassen.  
  
 ![Ansichtshierarchie](../mfc/media/vc38621.gif "vc38621")  
Eine Hierarchie anzeigen  
  
 Wenn eine Meldung in Klasse abgeglichen werden kann `CMyView`des meldungszuordnung, die das Framework auch auf die meldungszuordnung ihrer unmittelbaren Basisklasse gesucht. Die `BEGIN_MESSAGE_MAP` Makro am Anfang der meldungszuordnung gibt zwei Klassennamen als Argumente übergeben:  
  
 [!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]  
  
 Das erste Argument den Namen der Klasse, zu der die meldungszuordnung gehört. Das zweite Argument stellt eine Verbindung mit der direkten Basisklasse – `CView` hier – das Framework seine meldungszuordnung zu suchen kann.  
  
 Die Message-Handler, die in einer Basisklasse bereitgestellt werden daher von der abgeleiteten Klasse geerbt. Dies ist vergleichbar mit normalen virtuellen Memberfunktionen ohne alle Handler-Memberfunktionen virtuellen stellen.  
  
 Wenn in einer von der Basisklasse meldungszuordnungen kein Handler gefunden wird, wird standardmäßig der Verarbeitung der Nachricht ausgeführt. Wenn die Nachricht ein Befehl ist, leitet Sie das Framework auf das nächste Befehlsziel weiter. Wenn es sich um eine standardmäßige Windows-Nachricht handelt, wird die Nachricht an die entsprechende Standardfensterprozedur übergeben.  
  
 Damit meldungszuordnung Abgleich beschleunigt werden, speichert das Framework aktuelle entspricht der Wahrscheinlichkeit, dass es die gleiche Nachricht empfangen wird. Eine Folge davon ist, dass die Prozesse Framework Nachrichten nicht sehr effizient behandelt. Meldungszuordnungen sind auch mehr Speicherplatz, effizient als Implementierungen, die virtuelle Funktionen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

