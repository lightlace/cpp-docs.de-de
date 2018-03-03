---
title: --Overridables-Kommentar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca52bcc3846971af1811551411199785c3d4e102
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="-overridables-comment"></a>// Overridables-Kommentar
Die `// Overridables` Abschnitt der Deklaration eines MFC-Klasse enthält virtuelle Funktionen, die Sie in einer abgeleiteten Klasse überschreiben können, wenn Sie das Verhalten der Basisklasse ändern müssen. Sie sind in der Regel mit dem Namen beginnend mit "On", obwohl dies nicht unbedingt erforderlich ist. Hier Funktionen dienen zur außer Kraft gesetzt werden, und häufig zu implementieren oder geben Sie irgendeine der "Callback" oder "verknüpfen". In der Regel sind diese Member geschützt.  
  
 In MFC selbst werden reine virtuelle Funktionen immer in diesem Abschnitt platziert. Eine reine virtuelle Funktion in C++ ist eine von der Form:  
  
 `virtual void OnDraw( ) = 0;`  
  
 In der Stichprobe, die von Klasse auflisten `CStdioFile`im [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md), die Liste enthält keine Overridables-Abschnitt. Klasse **CDocument**, andererseits, ungefähr 10 überschreibbare Memberfunktionen aufgeführt.  
  
 In einige Klassen möglicherweise auch den Kommentar angezeigt `// Advanced Overridables`. Hierbei handelt es sich um Funktionen, die nur von erfahrenen Programmierern sollten versuchen, um zu überschreiben. Sie benötigen wahrscheinlich nie sie zu überschreiben.  
  
> [!NOTE]
>  Die Konventionen, die in diesem Artikel beschriebenen auch funktionieren gut, im Allgemeinen für Automation (früher OLE-Automatisierung) Methoden und Eigenschaften. Automatisierungsmethoden ähneln MFC-Vorgänge. Automatisierungseigenschaften ähneln MFC-Attribute. Überschreibbare Memberfunktionen von MFC ähneln Automatisierungsereignisse (unterstützt für ActiveX-Steuerelemente, früher OLE-Steuerelemente).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)   
 [/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [Konstruktoren Kommentar](../mfc/decrement-constructors-comment.md)   
 [Attributekommentar](../mfc/decrement-attributes-comment.md)   
 [Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)

