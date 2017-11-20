---
title: 'Vorgehensweise: erstellen eine typsicheren Auflistung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f8ba8df138cf45ac38ac17a48d5c711f53c8fe5d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-make-a-type-safe-collection"></a>Gewusst wie: Erstellen einer typsicheren Auflistung
In diesem Artikel erläutert die typsichere Auflistungen für Ihre eigenen Datentypen zu stellen. Folgende Themen werden behandelt:  
  
-   [Mithilfe von Template-basierten Klassen typsicherheit](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [Implementieren Hilfsfunktionen](#_core_implementing_helper_functions)  
  
-   [Verwenden von Auflistungsklassen](#_core_using_nontemplate_collection_classes)  
  
 Die Microsoft Foundation Class-Bibliothek bietet vordefinierte typsichere Auflistungen basierend auf C++-Vorlagen. Da diese Vorlagen sind, tragen zu dieser Klassen typsicherheit und einfache Verwendung ohne die Typumwandlung und andere zusätzliche Arbeit, die in einer nicht auf Vorlagen basierende Klasse zu diesem Zweck verwenden. Das MFC-Beispiel [sammeln](../visual-cpp-samples.md) veranschaulicht die Verwendung von vorlagenbasierte Auflistungsklassen in einer MFC_Anwendung. Verwenden Sie diese Klassen im Allgemeinen wird jedes Mal, wenn Sie neue Sammlungen Code schreiben.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a>Mithilfe von Template-basierten Klassen typsicherheit  
  
#### <a name="to-use-template-based-classes"></a>Vorlagenbasierte Klassen  
  
1.  Deklarieren Sie eine Variable des Klassentyps Auflistung. Zum Beispiel:  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  Rufen Sie die Memberfunktionen des Auflistungsobjekts. Zum Beispiel:  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  Implementieren Sie bei Bedarf die [Hilfsfunktionen](../mfc/reference/collection-class-helpers.md) und [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements). Informationen zum Implementieren dieser Funktionen finden Sie unter [Hilfsfunktionen implementieren](#_core_implementing_helper_functions).  
  
 Dieses Beispiel zeigt die Deklaration einer Liste von ganzen Zahlen. Der erste Parameter in Schritt 1 ist der Typ der Daten, die als Elemente der Liste gespeichert. Der zweite Parameter gibt an, wie die Daten zu übergeben und von Memberfunktionen der Auflistungsklasse, z. B. **hinzufügen** und `GetAt`.  
  
##  <a name="_core_implementing_helper_functions"></a>Implementieren Hilfsfunktionen  
 Die vorlagenbasierte Auflistungsklassen `CArray`, `CList`, und `CMap` verwenden fünf globale Hilfsfunktionen, die Sie für Ihre abgeleiteten Auflistungsklasse nach Bedarf anpassen können. Informationen zu diesen Hilfsfunktionen finden Sie unter [Auflistungsklasse](../mfc/reference/collection-class-helpers.md) in der *MFC-Referenz*. Implementierung der Serialisierungsfunktion ist für die meisten Verwendungen von die vorlagenbasierte Auflistungsklassen erforderlich.  
  
###  <a name="_core_serializing_elements"></a>Serialisieren von Elementen  
 Die `CArray`, `CList`, und `CMap` Klassen Aufruf `SerializeElements` Elemente der Auflistung zu speichern oder aus einem Archiv zu lesen.  
  
 Die standardmäßige Implementierung des der `SerializeElements` Hilfsfunktion wird eine bitweise Schreiben von Objekten in das Archiv oder eine bitweise aus dem Archiv gelesen werden, um die Objekte, abhängig davon, ob die Objekte in gespeichert werden oder aus dem Archiv abgerufen. Überschreiben Sie `SerializeElements` Wenn diese Aktion nicht geeignet ist.  
  
 Wenn die Auflistung von abgeleitete Objekte speichert `CObject` und verwenden Sie die `IMPLEMENT_SERIAL` Makros in der Implementierung der Element-Auflistungsklasse, profitieren Sie von integrierten Funktionen für die Serialisierung `CArchive` und `CObject`:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]  
  
 Die überladenen Einfügeoperatoren für `CArchive` Aufrufen `CObject::Serialize` (oder eine Überschreibung dieser Funktion) für die einzelnen **CPerson** Objekt.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a>Verwenden von Auflistungsklassen  
 MFC unterstützt auch die Auflistungsklassen, die mit MFC, Version 1.0 eingeführt wurden. Diese Klassen basieren nicht auf Vorlagen. Sie können verwendet werden, um die unterstützten Datentypen enthalten `CObject*`, **"uint"**, `DWORD`, und `CString`. Sie können diese vordefinierten Sammlungen (z. B. `CObList`) zum Speichern von Sammlungen von Objekten von abgeleiteten `CObject`. MFC bietet auch andere vordefinierten Sammlungen um primitive Typen enthalten, wie z. B. **"uint"** und void-Zeiger (`void`*). Im Allgemeinen ist es jedoch oft hilfreich, um eine eigene typsichere Auflistungen zum Speichern von Objekten der einen spezifischeren Klasse und die Ableitung zu definieren. Beachten Sie, dass auf diese Weise mit der Auflistungsklassen nicht auf Basis der Vorlagen mehr als die Template-basierten Klassen verwenden arbeiten.  
  
 Es gibt zwei Möglichkeiten, typsichere Auflistungen nicht auf Vorlagen basierende Sammlungen zu erstellen:  
  
1.  Verwenden Sie die Sammlungen nicht auf Vorlagen basierende mit Typ umwandeln, falls erforderlich. Dies ist einfacher Ansatz.  
  
2.  Leiten Sie ab und erweitern Sie eine nicht auf Vorlagen basierende typsicheren Auflistung.  
  
#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Verwenden Sie die nicht auf Vorlagen basierende Auflistungen mit Typumwandlung  
  
1.  Verwenden Sie eine der nicht auf Vorlagen basierende Klassen, z. B. `CWordArray`direkt.  
  
     Sie können z. B. Erstellen einer `CWordArray` fügen Sie eine beliebige 32-Bit-Werte hinzu, und diese abrufen. Es ist nichts mehr zu tun. Sie verwenden einfach die vordefinierte Funktionen.  
  
     Sie können auch eine vordefinierte Auflistung verwenden, z. B. `CObList`, um alle Objekte, die von abgeleiteten aufnehmen `CObject`. Ein `CObList` Auflistung definiert ist, zum Speichern von Zeigern auf `CObject`. Wenn Sie ein Objekt aus der Liste abrufen, müssen Sie möglicherweise das Ergebnis in den richtigen Typ seit Umwandeln der `CObList` Funktionen geben Zeiger zu `CObject`. Angenommen, Sie speichern `CPerson` Objekte in einem `CObList` Sammlung, Sie müssen einen Zeiger auf ein abgerufenes Element Umwandeln einer `CPerson` Objekt. Im folgenden Beispiel wird eine `CObList` Auflistung zum Speichern `CPerson` Objekte:  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]  
  
     Dieses Verfahren mithilfe einen vordefinierten Sammlungstyp und Umwandlung bei Bedarf kann für viele der Ihren Anforderungen Auflistung verwendet werden. Wenn Sie weitere Funktionen oder weitere typsicherheit benötigen, verwenden Sie eine Template-basierten Klasse, oder verwenden Sie das nächste Verfahren.  
  
#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Ableiten und erweitern eine nicht auf Vorlagen basierende typsicheren Auflistung  
  
1.  Leiten Sie eine eigene Auflistungsklasse aus einer der vordefinierten nicht auf Vorlagen basierende Klassen.  
  
     Wenn Sie eine Klasse ableiten, können Sie typsichere Wrapperfunktionen zum Bereitstellen einer typsicheren-Schnittstelle, um vorhandene Funktionen hinzufügen.  
  
     Angenommen, wenn Sie eine Liste von abgeleiteten `CObList` zum Speichern `CPerson` Objekte aufweist, können Sie die Wrapperfunktionen hinzufügen `AddHeadPerson` und `GetHeadPerson`, wie unten dargestellt.  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]  
  
     Diese Wrapperfunktionen bieten eine typsichere Möglichkeit zum Hinzufügen und Abrufen von `CPerson` aus der Liste der abgeleiteten Objekte. Sie sehen, dass für die `GetHeadPerson` -Funktion, werden Sie einfach die Typumwandlung kapseln.  
  
     Sie können auch neue Funktionen hinzufügen, indem Definieren neuer Funktionen, die die Funktionen der Auflistung zu erweitern, statt vorhandene Funktionalität in typsicheren Wrapper umschließen. Z. B. die Artikel [Löschen aller Objekte in einer CObject-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md) beschreibt eine Funktion zum Löschen aller Objekte, die in einer Liste enthalten. Diese Funktion konnte als Memberfunktion der abgeleiteten Klasse hinzugefügt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Sammlungen](../mfc/collections.md)

