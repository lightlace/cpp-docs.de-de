---
title: Sammlungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: beae5370c86bf0142b29f029778083f3042ae931
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="collections"></a>Auflistungen
Die Microsoft Foundation Class-Bibliothek stellt Auflistungsklassen zum Verwalten von Gruppen von Objekten bereit. Diese Klassen sind zwei Typen:  
  
-   [Auflistungsklassen, die von C++-Vorlagen erstellt](#_core_the_template_based_collection_classes)  
  
-   [Auflistungsklassen, die nicht aus Vorlagen erstellt.](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  Wenn Ihr Code bereits Auflistungsklassen verwendet wird, können Sie weiterhin zu verwenden. Wenn Sie neue typsichere Auflistungsklassen für eigene Datentypen schreiben, wird empfohlen, dass Sie die neueren Template-basierten Klassen verwenden.  
  
##  <a name="_core_collection_shapes"></a> Auflistungsformen  
 Eine Auflistungsklasse wird durch die "Shape" und von den Typen seiner Elemente gekennzeichnet. Die Form "bezieht sich auf die Möglichkeit, die Objekte organisiert und von der Auflistung gespeichert werden. MFC bietet drei grundlegende Auflistungsformen: Listen, arrays und ordnet (auch bekannt als Wörterbücher). Sie können die Form "Auflistung" auswählen, die sich am besten für Ihr Problem für bestimmte Programmiersprachen ist.  
  
 Jede der drei Auflistungsformen wird kurz weiter unten in diesem Thema beschrieben. Zum Vergleichen der Funktionen der Formen können Sie entscheiden, die für Ihre Anwendung am besten geeignet ist, finden Sie unter [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   Liste  
  
     Der List-Klasse stellt eine sortierte, nicht indizierte Liste von Elementen, die als eine doppelt verknüpfte Liste implementiert. Eine Liste verfügt über eine "Head" und einem "Ende" und hinzufügen oder Entfernen von Elementen aus der Head oder Tail, einfügen oder Löschen von Elementen in der Mitte ist sehr schnell.  
  
-   Array  
  
     Die Array-Klasse stellt eine dynamisch mit angegebener Größe, geordnete und Integer-indizierte Array von Objekten bereit.  
  
-   Zuordnung (auch bekannt als ein Wörterbuch)  
  
     Eine Karte ist eine Auflistung, die ein Wertobjekt ein Schlüsselobjekt zuordnet.  
  
##  <a name="_core_the_template_based_collection_classes"></a> Die vorlagenbasierte Auflistungsklassen  
 Die einfachste Möglichkeit, eine typsichere Auflistung implementieren, die Objekte eines beliebigen Typs enthält, ist eine von der MFC-Template-basierten Klassen verwenden. Beispiele für diese Klassen, finden Sie im MFC-Beispiel [sammeln](../visual-cpp-samples.md).  
  
 Die folgende Tabelle enthält die vorlagenbasierte Auflistungsklassen von MFC.  
  
### <a name="collection-template-classes"></a>Vorlage-Auflistungsklassen  
  
|Auflistungsinhalt|Arrays|Listen|Karten|  
|-------------------------|------------|-----------|----------|  
|Auflistungen von Objekten eines beliebigen Typs|`CArray`|`CList`|`CMap`|  
|Sammlungen von Zeigern auf Objekte eines beliebigen Typs|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Die nicht auf Vorlagen basieren Auflistungsklassen  
 Wenn die Anwendung bereits MFC nicht auf Vorlagen basierende Klassen verwendet wird, können Sie weiterhin zu verwenden. Für neue Sammlungen empfehlen wir jedoch, dass Sie die Template-basierten Klassen verwenden. Die folgende Tabelle enthält die MFC-Auflistungsklassen, die nicht auf Vorlagen basieren.  
  
### <a name="nontemplate-collection-classes"></a>Auflistungsklassen  
  
|Arrays|Listen|Karten|  
|------------|-----------|----------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 Die Merkmale von MFC-Auflistungsklassen Tabelle [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md) beschreibt die MFC-Auflistungsklassen in Bezug auf diese Merkmale (mit Ausnahme des Form "):  
  
-   ob die Klasse C++-Vorlagen verwendet  
  
-   ob die in der Auflistung gespeicherten Elemente serialisiert werden können  
  
-   ob die in der Auflistung gespeicherten Elemente zur Diagnose gesichert werden können  
  
-   ob die Auflistung typsicher ist  
  
### <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
  
#### <a name="general-collection-class-tasks"></a>Auflistungsklasse für allgemeine Aufgaben  
  
-   [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [Vorgehensweise: Erstellen einer typsicheren Auflistung](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [Erstellen von Stapel- und Warteschlangenauflistungen](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../mfc/reference/carray-class.md#add)  
  
#### <a name="template-based-collection-class-tasks"></a>Template-basierten Auflistungsklasse Aufgaben  
  
-   [Vorlagenbasierte Klassen](../mfc/template-based-classes.md)  
  
#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Zugriff auf die Member einer Auflistung (Template-basierten oder nicht)  
  
-   [Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [Löschen aller Objekte in einer CObject-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

