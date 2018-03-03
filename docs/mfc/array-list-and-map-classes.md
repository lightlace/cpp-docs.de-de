---
title: Arrays, Listen und Zuordnungsklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7de6f3c72b31ea9094af032bc81e9f2506606cce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="array-list-and-map-classes"></a>Klassen für Arrays, Listen und Zuordnungen
Für die Behandlung von Aggregaten von Daten, die Klassenbibliothek bietet eine Gruppe von Auflistungsklassen, arrays, Listen und Zuordnungen –, die eine Vielzahl von Objekt und die vordefinierten Typen aufnehmen kann. Die Sammlungen werden dynamisch angepasst. Diese Klassen können in jedem Programm verwendet werden, ob für Windows oder nicht geschrieben. Allerdings sind sie besonders hilfreich für die Implementierung der Datenstrukturen, die Document-Klassen in das Anwendungsframework definieren. Sie können spezielle Auflistungsklassen unmittelbar von diesen ableiten, oder Sie können basierend auf der Vorlagenklassen erstellen. Weitere Informationen zu diesen Vorgehensweisen finden Sie im Artikel [Sammlungen](../mfc/collections.md). Eine Liste der Auflistung Vorlagenklassen, finden Sie im Artikel [Vorlagenklassen für Arrays, Listen und Zuordnungen](../mfc/template-classes-for-arrays-lists-and-maps.md).  
  
 Arrays sind eindimensionale-Datenstrukturen, die im Arbeitsspeicher zusammenhängend gespeichert werden. Sie unterstützen sehr schnellen zufälligen Zugriff, da die Speicheradresse eines bestimmten Elements berechnet werden kann, indem der Index des Elements mit der Größe eines Elements multipliziert und das Ergebnis an die Basisadresse des Arrays hinzugefügt. Aber Arrays sind sehr teuer, wenn Sie Elemente in das Array eingefügt haben, seit das gesamte Array vergangenen das Element eingefügt wurde verschoben werden, um Platz für das Element eingefügt werden. Arrays können wachsen und schrumpfen nach Bedarf.  
  
 Listen ähneln Arrays jedoch sehr unterschiedlich gespeichert werden. Jedes Element in einer Liste umfasst auch einen Zeiger auf die vorherige und kommende Elemente, die somit einer doppelt verknüpften Liste. Es ist sehr schnell hinzufügen oder löschen Elemente aus, da auf diese Weise nur beinhaltet einige Zeiger ändern. Durchsuchen einer Liste kann sich jedoch teuer sein, da alle suchen, um an einem Ende der Liste zu starten müssen.  
  
 Zuordnungen werden einen Schlüssel-Wert an einen Datenwert beziehen. Der Schlüssel einer Zuordnung kann z. B. eine Zeichenfolge und die Daten einen Zeiger in eine Liste sein. Sie würden die Karte, um Sie den Zeiger, die einer bestimmten Zeichenfolge zugeordneten geben bitten. Map-Suchvorgänge sind schnell, da Zuordnungen Hashtabellen zum Key Lookups verwenden. Hinzufügen und Löschen von Elementen ist auch schnell. Zuordnungen werden häufig mit anderen Datenstrukturen als zusätzlichen Indizes verwendet. MFC verwendet eine spezielle Art von Zuordnung bezeichnet eine [meldungszuordnung](../mfc/mapping-messages.md) , Windows-Nachrichten in einen Zeiger an die Handlerfunktion für diese Nachricht zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

