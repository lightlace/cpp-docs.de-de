---
title: --Attribute Kommentar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74398d731c51223ea74fc6b827b0626af89286b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-attributes-comment"></a>// Attributes-Kommentar
Die `// Attributes` Teil der Deklaration eines MFC-Klasse enthält den öffentlichen Attributen (oder Eigenschaften) des Objekts. In der Regel sind dies Membervariablen oder Get/Set-Funktionen. Die "Get" und "Set"-Funktion können oder nicht virtuell sein. Die "Get"-Funktionen sind in der Regel **const**, da in den meisten Fällen sie keine Nebeneffekte haben. Diese Elemente sind normalerweise public. geschützte und private Attribute werden in der Regel im Umsetzungsabschnitt gefunden.  
  
 In der Stichprobe, die von Klasse auflisten `CStdioFile`unter [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md), die Liste enthält eine Membervariable zu `m_pStream`. Klasse `CDC` listet beinahe 20 Elemente unterhalb des Kommentars.  
  
> [!NOTE]
>  Große Klassen, z. B. `CDC` und `CWnd`, möglicherweise so viele Elemente, die einfach Auflisten aller Attribute in einer Gruppe keine Klarheit hinzufügen würden. In solchen Fällen werden die Klassenbibliothek andere Kommentare als Überschriften aus, um weitere Elemente voneinander abzugrenzen. Beispielsweise `CDC` verwendet `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`, und vieles mehr. Gruppen, die Attribute darstellen, werden die übliche Syntax, die oben beschriebenen folgen. Zahlreiche OLE-Klassen müssen einen Implementierungsabschnitt aufgerufen `// Interface Maps`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)   
 [/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [Konstruktoren Kommentar](../mfc/decrement-constructors-comment.md)   
 [Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)   
 [Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

