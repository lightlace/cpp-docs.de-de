---
title: Überschreiben des Standardbefehlsroutings | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13f6c8f262061477da95a4863965c04e9d75c49a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-the-standard-command-routing"></a>Überschreiben des Standardbefehlsroutings
In seltenen Fällen, wenn Sie eine Variante des standardframeworkressourcen routing implementieren müssen können Sie sie überschreiben. Das Konzept ist so ändern Sie das routing in eine oder mehrere Klassen durch Außerkraftsetzen von `OnCmdMsg` in diesen Klassen. Wenn Sie dies tun:  
  
-   In der Klasse, die die Reihenfolge der Übergabe an ein nicht standardmäßiges-Objekt zu beeinträchtigen.  
  
-   Neues Objekt in den nicht standardmäßigen oder in Befehlsziele kann wiederum Befehle übergeben werden.  
  
 Wenn Sie ein neues Objekt in das routing einfügen, muss die Klasse einen Befehlsziel Klasse. In der überschreibenden Versionen von `OnCmdMsg`, achten Sie darauf, dass Sie die Version abzurufen, die Sie überschreiben möchten. Finden Sie unter der [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) Memberfunktion der Klasse `CCmdTarget` in der *MFC-Referenz* und die Versionen in Klassen wie `CView` und **CDocument** in der Beispiele für Quellcode zur Verfügung gestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

