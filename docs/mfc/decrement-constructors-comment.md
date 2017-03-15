---
title: "// Constructors-Kommentar"
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
  - "Kommentare, Konstruktorenkommentar"
  - "Kommentare, MFC"
  - "Konstruktoren [C++], Deklarieren"
  - "Konstruktorenkommentar"
  - "Deklarationen, Konstruktoren"
  - "Deklarieren von Konstruktoren, Codekommentare"
  - "Instanzkonstruktoren, Codekommentare"
  - "MFC-Quelldateien, Konstruktorenkommentar"
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# // Constructors-Kommentar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `// Constructors`\-Abschnitt einer MFC\-Klassen\-Deklaration deklariert Konstruktoren \(im C\+\+\-Sinn\) sowie alle Initialisierungsfunktionen, die erforderlich sind, das Objekt tatsächlich zu verwenden.  Beispielsweise ist `CWnd::Create` im Konstruktorabschnitt, da, bevor Sie das `CWnd`\-Objekt verwenden, wenn es vollständig "erstellt werden muss" indem zuerst den C\+\+\-Konstruktor aufgerufen und anschließend die Funktion **Erstellen** aufruft.  In der Regel sind diese Member öffentlich.  
  
 Beispielsweise hat Klasse `CStdioFile` drei Konstruktoren, von denen einer in den Listen unter [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md) gezeigt wird.  
  
## Siehe auch  
 [Verwenden der MFC\-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [\/\/ Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [\/\/ Attributes\-Kommentar](../mfc/decrement-attributes-comment.md)   
 [\/\/ Operations\-Kommentar](../mfc/decrement-operations-comment.md)   
 [\/\/ Overridables\-Kommentar](../mfc/decrement-overridables-comment.md)