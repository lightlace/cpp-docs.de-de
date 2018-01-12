---
title: "--Vorgänge-Kommentar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 53d2470e0be0ca314da8486d74d8fc618e134c35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="-operations-comment"></a>// Operations-Kommentar
Die `// Operations` Abschnitt der Deklaration eines MFC-Klasse enthält, Memberfunktionen, die Sie, auf das Objekt aufrufen können, das Aktionen oder Aktionen, die (Vorgänge) erleichtern. Diese Funktionen befinden sich in der Regel nicht -**const** , da sie in der Regel Nebeneffekte haben. Sie können virtuell oder je nach den Anforderungen der Klasse nicht virtuell sein. In der Regel sind diese Member öffentlich.  
  
 In der Stichprobe, die von Klasse auflisten `CStdioFile`im [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md), die Liste enthält zwei Memberfunktionen unter dieser Kommentar: `ReadString` und `WriteString`.  
  
 Wie bei Attributen, können Vorgänge weiter unterteilt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)   
 [/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [Konstruktoren Kommentar](../mfc/decrement-constructors-comment.md)   
 [Attributekommentar](../mfc/decrement-attributes-comment.md)   
 [Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

