---
title: 'Ausnahmen: Untersuchen von Ausnahmeinhalten | Microsoft Docs'
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
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 953dd61247f7d14ad04d5d5f85529c89f3aaad9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-examining-exception-contents"></a>Ausnahmen: Untersuchen von Ausnahmeinhalten
Obwohl eine **catch** des Blocks-Argument des fast jeden Datentyps sein, die MFC-Funktionen Ausnahmen von Typen, die von der Klasse abgeleitet `CException`. Um eine von einer MFC-Funktion ausgelöste Ausnahme abzufangen, klicken Sie dann, Sie schreiben eine **catch** blockieren, deren Argument ein Zeiger ist, auf eine `CException` Objekt (oder ein Objekt abgeleitet `CException`, wie z. B. `CMemoryException`). Untersuchen Sie je nach den genauen Typ der Ausnahme die Datenmember des Ausnahmeobjekts, um Informationen über die Ursache der Ausnahme zu erfassen.  
  
 Z. B. die `CFileException` Typ verfügt über die `m_cause` Datenmember, die einen enumerierten Typ enthält, der die Ursache der Ausnahme Datei angibt. Einige Beispiele für die möglichen Rückgabewerte sind **CFileException:: FileNotFound** und **CFileException:: ReadOnly**.  
  
 Im folgende Beispiel wird gezeigt, wie auf den Inhalt untersuchen eine `CFileException`. Andere Ausnahmetypen können auf ähnliche Weise untersucht werden.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md) und [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

