---
title: "// Overridables-Kommentar"
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
  - "MFC-Quelldateien, Overridables-Kommentar"
  - "Overridables-Kommentar in MFC-Quelldateien"
  - "Überschreiben, Overridables-Kommentar in MFC-Quelldateien"
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# // Overridables-Kommentar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `// Overridables`\-Abschnitt einer MFC\-Klassen\-Deklaration enthält virtuelle Funktionen, die Sie in einer abgeleiteten Klasse überschreiben können, wenn Sie das Basisklassenverhalten ändern müssen.  Sie werden üblicherweise Starten mit "on", jedoch nicht zwingend erforderlich ist.  Funktionen sind hier entworfen überschrieben werden und häufig implementieren oder stellen eine Sortierung "des Rückrufs" oder "Sie verknüpfen." Normalerweise werden diese Member geschützt.  
  
 In MFC selbst, sind rein virtuelle Funktionen immer in diesen Abschnitt eingefügt.  Eine rein virtuelle Funktion in C\+\+ ist eine des Formulars:  
  
 `virtual void OnDraw( ) = 0;`  
  
 In den Beispiellisten von der Klasse `CStdioFile`, [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md), enthält die Liste keinen Abschnitt der schreibbaren Elemente.  Die von **CDocument** hingegen Listen etwa 10 überschreibbare Memberfunktionen.  
  
 In einigen Klassen finden Sie ebenfalls den Kommentar `// Advanced Overridables`.  Dies sind Funktionen, die nur erweiterte Programmierer versuchen sollten, um zu überschreiben.  Sie müssen möglicherweise nie sie überschreiben.  
  
> [!NOTE]
>  Die dazugehörigen Konventionen, die in diesem Artikel beschriebenen funktionieren auch, gut im Allgemeinen für Methoden und Eigenschaften mit Automatisierungsserver \(früher bekannt als OLE\-Automatisierung\).  Automatisierungsmethoden sind zu MFC\-Vorgängen ähnlich.  Automatisierungseigenschaften sind zu MFC\-Attributen ähnlich.  Die Automatisierungsereignisse \(unterstützt für ActiveX\-Steuerelemente, früher bekannt als OLE\-Steuerelemente\) sind für Memberfunktionen schreibbaren MFC ähnlich.  
  
## Siehe auch  
 [Verwenden der MFC\-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)   
 [\/\/ Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructors\-Kommentar](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributes\-Kommentar](../mfc/decrement-attributes-comment.md)   
 [\/\/ Operations\-Kommentar](../mfc/decrement-operations-comment.md)