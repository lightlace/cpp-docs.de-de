---
title: "Überschreiben des Standardbefehlsroutings | Microsoft Docs"
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
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a8f926a2aa9ed48dac24f75850876bbd1e04ef4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-the-standard-command-routing"></a>Überschreiben des Standardbefehlsroutings
In seltenen Fällen, wenn Sie eine Variante des standardframeworkressourcen routing implementieren müssen können Sie sie überschreiben. Das Konzept ist so ändern Sie das routing in eine oder mehrere Klassen durch Außerkraftsetzen von `OnCmdMsg` in diesen Klassen. Wenn Sie dies tun:  
  
-   In der Klasse, die die Reihenfolge der Übergabe an ein nicht standardmäßiges-Objekt zu beeinträchtigen.  
  
-   Neues Objekt in den nicht standardmäßigen oder in Befehlsziele kann wiederum Befehle übergeben werden.  
  
 Wenn Sie ein neues Objekt in das routing einfügen, muss die Klasse einen Befehlsziel Klasse. In der überschreibenden Versionen von `OnCmdMsg`, achten Sie darauf, dass Sie die Version abzurufen, die Sie überschreiben möchten. Finden Sie unter der [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) Memberfunktion der Klasse `CCmdTarget` in der *MFC-Referenz* und die Versionen in Klassen wie `CView` und **CDocument** in der Beispiele für Quellcode zur Verfügung gestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

