---
title: "Auflistungen | Microsoft Docs"
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
  - "Arrayvorlagen"
  - "Arrays [C++], Klassen"
  - "Auflistungsklassen, Informationen über Auflistungsklassen"
  - "Auflistungsklassen, Arrays"
  - "Auflistungsklassen, Listen"
  - "Auflistungsklassen, Zuordnungen"
  - "Auflistungsklassen, MFC"
  - "Auflistungsklassen, Formen"
  - "Auflistungsklassen, Vorlagenbasiert"
  - "Auflistungen, Informationen über Auflistungen"
  - "MFC-Auflistungsklassen"
  - "MFC, Auflistungen"
  - "Formen"
  - "Formen, Auflistung"
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Auflistungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Microsoft Foundation Class\-Bibliothek enthält Auflistungsklassen, um Gruppen von Objekten zu verwalten.  Diese Klassen sind von zweierlei Typen:  
  
-   [Auflistungsklassen erstellt von C\+\+\-Vorlagen](#_core_the_template.2d.based_collection_classes)  
  
-   [Auflistungsklassen erstellt nicht Vorlagen](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  Wenn der Code bereits nicht auf Vorlagen basierende MFC\-Auflistungsklassen verwendet, können Sie weiterhin, um sie zu verwenden.  Wenn Sie neue typsichere für Auflistungsklassen eigener Datentypen schreiben, wird empfohlen, die späteren vorlagenbasierten Klassen verwenden.  
  
##  <a name="_core_collection_shapes"></a> Auflistungs\-Formen  
 Eine Auflistungsklasse wird durch die "Form" und die Typen seiner Elemente bezeichnet.  Die Form wird die Methode an, die die Objekte von der Auflistung organisiert und gespeichert werden.  MFC enthält drei grundlegende Auflistungsformen: Listen, Arrays und Zuordnungen \(auch Wörterbücher\).  Sie können die Auflistungsform auswählen, die höchst zu dem bestimmten Programmierung Problem verarbeiten.  
  
 Jede der drei bereitgestellten Auflistungsformen wird kurz weiter unten in diesem Thema beschrieben.  Um die Funktionen der Formen zu vergleichen Sie Informationen entscheiden das für das Programm am besten geeignet ist, finden Sie unter [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   List  
  
     Die Listenklasse stellt eine geordnete, nicht indizierte Elementliste, doppelt implementiert als verknüpfte Liste.  Eine Liste hat einen "Kopf" und ein "Ende," und Elemente im head\-Teil oder vom Ende Hinzufügen bzw. Entfernen oder Elemente in der Mitte Einfügen oder Löschen, ist sehr schnell.  
  
-   Array  
  
     Die Arrayklasse stellt ein skaliertes dynamisch, bestelltes und Zahl\-indiziertes Objektarray.  
  
-   Zuordnung \(auch als Wörterbuch\)  
  
     Eine Zuordnung ist eine Auflistung, die ein Schlüsselobjekt mit einem Wertobjekt zuordnet.  
  
##  <a name="_core_the_template.2d.based_collection_classes"></a> Die Vorlage gebildeten Auflistungsklassen  
 Die einfachste Methode, eine typsichere Auflistung zu implementieren, die Objekte eines Typs enthält, ist, eine der vorlagenbasierten Klassen MFC verwenden.  Beispiele dieser Klassen finden Sie im MFC\-Beispiel [COLLECT Sie](../top/visual-cpp-samples.md).  
  
 In der folgenden Tabelle sind die auf Vorlagen basierenden Auflistungsklassen auf MFC.  
  
### Auflistungs\-Vorlagenklassen  
  
|Auflistungsinhalt|Arrays|Listen|Zuordnungen|  
|-----------------------|------------|------------|-----------------|  
|Auflistungen Objekte von einem Typ|`CArray`|`CList`|`CMap`|  
|Auflistungen Zeiger auf Objekte von allen Typen|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Die Auflistungsklassen nicht basierend auf Vorlagen  
 Wenn die Anwendung bereits nicht auf Vorlagen basierende Klassen von MFC verwendet, können Sie weiterhin, um sie zu verwenden.  Für neue Auflistungen, wird empfohlen, die auf Vorlagen basierenden Klassen verwenden.  Die folgende Tabelle zeigt die MFC\-Auflistungsklassen auf, die nicht auf Vorlagen basieren.  
  
### Nicht auf Vorlagen basierende MFC\-Auflistungsklassen  
  
|Arrays|Listen|Zuordnungen|  
|------------|------------|-----------------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 Die Eigenschaften der MFC\-Auflistungsklassentabelle in [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md) beschreiben die MFC\-Auflistungsklassen im Hinblick auf diese Eigenschaften \(außer Form\):  
  
-   Ob der Klasse C\+\+\-Vorlagen verwendet  
  
-   Ob die Elemente, die in der Auflistung gespeichert werden, serialisiert werden können  
  
-   Ob die Elemente, die in der Auflistung gespeichert werden, für Diagnose gesichert werden können  
  
-   Ob die Auflistung ist typsicher  
  
### Was möchten Sie tun?  
  
#### Allgemeine Auflistungsklassen\-Aufgaben  
  
-   [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [Gewusst wie: Erstellen einer typsicheren Auflistung](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [Erstellen von Stack\- und Warteschlangenauflistungen](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../Topic/CArray::Add.md)  
  
#### Auf Vorlagen basierende Auflistungsklassen\-Aufgaben  
  
-   [Vorlagenbasierte Klassen](../mfc/template-based-classes.md)  
  
#### Auf die Member einer Auflistung zugreifen \(vorlagenbasiert oder nicht\)  
  
-   [Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [Löschen aller Objekte in einer CObject\-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)