---
title: --/ / Implementierungskommentar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 437b091b2237c7219a0afeee46d78164751e6d3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="-implementation-comment"></a>// Implementierungskommentar
Die `// Implementation` Abschnitt ist der wichtigste Teil der Deklaration einer MFC-Klasse.  
  
 Dieser Abschnitt enthält alle Implementierungsdetails. Membervariablen und Memberfunktionen können in diesem Abschnitt angezeigt. Alles unterhalb dieser Zeile konnte in einer zukünftigen Version von MFC geändert werden. Wenn Sie es nicht vermeiden lassen, Sie sollten auf "Details" unten nicht zu verlassen der `// Implementation` Zeile. Member, die unterhalb der Linie Implementierung deklariert sind darüber hinaus nicht dokumentiert, obwohl einige Implementierung in technische Hinweise erläutert wird. Überschreibungen virtueller Funktionen in der Basisklasse befinden sich in diesem Abschnitt, unabhängig davon, welcher Abschnitt Funktion der Basisklasse in definiert ist, da die Tatsache, dass eine Funktion Implementierung der Basisklasse überschreibt Implementierungsdetail betrachtet wird. In der Regel werden diese Elemente geschützt, aber nicht immer.  
  
 Beachten Sie, aus der `CStdioFile` unter auflisten [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md) unten Member deklariert, der die `// Implementation` Kommentar kann deklariert werden, als **öffentlichen**, `protected`, oder `private`. Da sich diese in der Zukunft ändern können, sollten Sie nur diese Member mit Vorsicht zu verwenden. Deklarieren eine Gruppe von Elementen als **öffentlichen** möglicherweise erforderlich, für die Implementierung der Klassenbibliothek ordnungsgemäß funktioniert. Dies bedeutet jedoch nicht, dass Sie problemlos so deklarierten Member verwenden können.  
  
> [!NOTE]
>  Kommentare zu den übrigen Typen oberhalb oder unterhalb der `// Implementation` Kommentar. In beiden Fällen beschreiben sie die Arten von Membern unter ihnen liegenden deklariert. Wenn sie unten auftreten der `// Implementation` kommentieren Sie davon ausgehen, dass die Elemente in künftigen Versionen der MFC ändern können.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)   
 [Konstruktoren Kommentar](../mfc/decrement-constructors-comment.md)   
 [Attributekommentar](../mfc/decrement-attributes-comment.md)   
 [Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)   
 [Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

