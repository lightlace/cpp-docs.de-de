---
title: "// Implementierungskommentar"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kommentare, Implementierungskommentare"
  - "Kommentare, MFC"
  - "Implementierungskommentar in MFC-Quelldateien"
  - "MFC-Quelldateien, Implementierungskommentar"
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# // Implementierungskommentar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Abschnitt `// Implementation` ist der wichtigste Teil jeder MFC\-Klassen\-Deklaration.  
  
 diese beinhaltet alle Implementierungsdetails dieses Abschnitts.  können Membervariablen und Memberfunktionen in diesem Abschnitt enthalten.  Alle unter dieser Zeile kann in einer zukünftigen Version von MFC ändern.  Sofern, dass es nicht vermeiden können, sollten Sie nicht auf Details unter der `// Implementation` Zeile verlassen.  Außerdem werden die Member, die unter der Implementierungszeile deklariert, nicht dokumentiert, obwohl eine Implementierung in den Hinweisen technischen erläutert wird.  Überschreibungen virtueller Funktionen in der Basisklasse befinden sich in diesem Abschnitt, unabhängig vom Abschnitt die Basisklassenfunktion in definiert wurde, da die Tatsache, dass eine Funktion überschreibt, die Basisklassenimplementierung als ein Implementierungsdetail gilt.  Normalerweise werden diese Member, jedoch nicht immer geschützt.  
  
 Beachten Sie einer `CStdioFile`, die unter [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md) aufgeführt werden, das den Member möglicherweise, die unter der `// Implementation` Kommentars deklariert, als **public**, `protected` oder `private` deklariert werden.  Sie sollten dieser Member mit Vorsicht nur verwenden, da sie möglicherweise in der Zukunft ändern.  Das Deklarieren einer Gruppe Member als **public** ist möglicherweise erforderlich, damit die Klassenbibliotheksimplementierung ordnungsgemäß funktioniert.  Dies bedeutet nicht jedoch, dass es problemlos auf so deklarierten Member verwenden.  
  
> [!NOTE]
>  Sie suchen z Kommentare der verbleibenden Typen entweder über bzw. unter dem Kommentar `// Implementation`.  Grundsätzlich beschreiben sie die Arten aus Membern, die unterhalb sie deklariert werden.  Wenn sie unterhalb des `// Implementation` Kommentars auftreten, müssen Sie davon ausgehen, dass die Member kann in zukünftigen Versionen von MFC ändern.  
  
## Siehe auch  
 [Verwenden der MFC\-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)   
 [\/\/ Constructors\-Kommentar](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributes\-Kommentar](../mfc/decrement-attributes-comment.md)   
 [\/\/ Operations\-Kommentar](../mfc/decrement-operations-comment.md)   
 [\/\/ Overridables\-Kommentar](../mfc/decrement-overridables-comment.md)