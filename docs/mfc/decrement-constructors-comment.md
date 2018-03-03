---
title: --Konstruktoren Kommentar | Microsoft Docs
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
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6425252df34936d4ba3c9013664205b0038d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="-constructors-comment"></a>// Constructors-Kommentar
Die `// Constructors` Teil einer MFC-Klassendeklaration deklariert, Konstruktoren (in dem Sinne C++) sowie Initialisierungsfunktionen erforderlich, um das Objekt tatsächlich verwenden. Beispielsweise `CWnd::Create` wird im Abschnitt Konstruktoren, da vor der Verwendung der `CWnd` Objekt ist, wird er erstellt werden muss"vollständig" durch den ersten Aufruf des C++-Konstruktors und dem anschließenden Aufrufen der **erstellen** Funktion. In der Regel sind diese Member öffentlich.  
  
 Beispielsweise `CStdioFile` verfügt über drei Konstruktoren, von denen, in der Liste unter angezeigt wird [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)   
 [/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)   
 [Attributekommentar](../mfc/decrement-attributes-comment.md)   
 [Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)   
 [Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

