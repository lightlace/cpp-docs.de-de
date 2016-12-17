---
title: "Verwenden der MFC-Quelldateien"
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
  - "Kommentare, MFC"
  - "MFC-Quelldateien"
  - "MFC, Quelldateien"
  - "privater Memberzugriff"
  - "geschützter Memberzugriff"
  - "öffentliche Member"
  - "Quelldateien"
  - "Quelldateien, MFC"
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden der MFC-Quelldateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) bietet vollständigen Quellcode.  Headerdateien \(.h\) befinden sich im Verzeichnis \\atlmfc\\include; Implementierungsdateien \(.cpp\) befinden sich im Verzeichnis \\atlmfc\\src\\mfc.  
  
 Diese Gruppe von Elementen werden die Konventionen, die MFC verwendet, um die verschiedenen Teile der einzelnen Klassen zu vermerken, was Durchschnitt dieser Kommentare und was Sie erwarten sollten, um in jedem Abschnitt zu suchen.  Die Visual C\+\+\-Assistenten verwenden ähnliche Konventionen für die Klassen, die für Sie erstellen, und Sie werden wahrscheinlich diese Konventionen, die für eigenen Code hilfreich sind.  
  
 Sie können möglicherweise mit **public**, `protected` und Schlüsselwörtern `private` C\+\+ vertraut.  Wenn Sie die MFC\-Headerdateien berücksichtigen, suchen Sie, dass jede Klasse möglicherweise mehrere von jeweiligen hat.  Beispielweise kann Variablen des öffentlichen Members und Features anhand mehr als ein **public**\-Schlüsselwort.  Dies ist, da MFC Membervariablen und Features anhand ihrer Verwendung trennt, nicht nach Typ des Zugriffs zulässig.  MFC verwendet `private` sparsam; sogar Elemente sollten Implementierungsdetails werden geschützt im Allgemeinen und oft sind öffentlich.  Obwohl Zugriff auf den Implementierungsdetails ist abzuraten, überlässt MFC der Entscheidung Sie.  
  
 in den MFC\-Quelldateien und in Dateien, die vom MFC\-Anwendungs\-Assistenten erstellt, suchen Sie Kommentare wie diese innerhalb der Klassendeklarationen \(normalerweise in dieser Reihenfolge\):  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 Themen beschrieben in dieser Kategorie des Artikeleinschließung:  
  
-   [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)  
  
-   [Der Implementierungskommentar \/\/\-](../mfc/decrement-implementation-comment.md)  
  
-   [Der Konstruktorkommentar \/\/\-](../mfc/decrement-constructors-comment.md)  
  
-   [Der Attributkommentar \/\/\-](../mfc/decrement-attributes-comment.md)  
  
-   [Der Vorgangskommentar \/\/\-](../mfc/decrement-operations-comment.md)  
  
-   [Der Kommentar \/\/\-überschreibbarer Elemente](../mfc/decrement-overridables-comment.md)  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)