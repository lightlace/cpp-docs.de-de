---
title: "// Attributes-Kommentar"
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
  - "Attributekommentar in MFC-Quelldateien"
  - "Kommentare, Attribute"
  - "MFC-Quelldateien, Attributekommentar"
  - "Öffentlicher Attributekommentar"
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# // Attributes-Kommentar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `// Attributes`\-Abschnitt einer MFC\-Klassen\-Deklaration enthält die öffentliche Attribute \(oder die Eigenschaften des Objekts\).  In der Regel sind diese oder Membervariablen Get\/Set\-Funktionen.  "Abrufen" und "Set" Funktionen möglicherweise sind virtuell.  "Get" Funktionen sind normalerweise **const** auf, da in den meisten Fällen keine Nebeneffekte haben.  Diese Member sind normalerweise öffentlich; geschützte und private Attribute werden normalerweise im Implementierungsabschnitt gefunden.  
  
 In den Beispiellisten von der Klasse `CStdioFile`, unter [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md), enthält die Liste einköpfige Variablen, `m_pStream`.  Klasse `CDC` werden nahezu 20 Member unter diesem Kommentar auf.  
  
> [!NOTE]
>  Große Klassen, wie `CDC` und `CWnd`, verfügen so viele Member, die alle Attribute in einer Gruppe, nicht einfach, aufgeführt sind viel Verständlichkeit hinzugefügt würde.  In solchen Fällen wird die Klassenbibliothek andere Kommentare wie Überschriften, um die Member weiter abzugrenzen.  Beispielsweise verwendet `CDC``// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions` und mehr.  Gruppen, die Attribute darstellen, folgen der üblichen Syntax, die oben beschrieben wird.  Viele OLE\-Klassen haben einen Implementierungsabschnitt, der `// Interface Maps` aufgerufen wird.  
  
## Siehe auch  
 [Verwenden der MFC\-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)   
 [\/\/ Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructors\-Kommentar](../mfc/decrement-constructors-comment.md)   
 [\/\/ Operations\-Kommentar](../mfc/decrement-operations-comment.md)   
 [\/\/ Overridables\-Kommentar](../mfc/decrement-overridables-comment.md)