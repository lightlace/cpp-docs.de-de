---
title: 'Ausnahmen: Ausnahmen in Konstruktoren | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336700cc0137efe3bc106871ebd76b8de7a99af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-exceptions-in-constructors"></a>Ausnahmen: Ausnahmen in Konstruktoren
Beim Auslösen einer Ausnahme in einem Konstruktor, beliebige Objekte und die speicherbelegungen vorgenommenen vor dem Auslösen der Ausnahme, wie in beschrieben Bereinigen [Ausnahmen: Auslösen von Ausnahmen aus Ihrer eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 Beim Auslösen einer Ausnahme in einem Konstruktor wurde der Speicher für das Objekt selbst bereits von der Zeit zugeordnet, wenn der Konstruktor aufgerufen wird. Deshalb wird der Compiler automatisch Aufheben der Zuordnung des Arbeitsspeichers, die vom Objekt belegt wird, nachdem die Ausnahme ausgelöst wird.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

