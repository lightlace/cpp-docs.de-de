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
ms.openlocfilehash: 58156f6d1c361c24dc6cf04a9208157d614f91a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929009"
---
# <a name="overriding-the-standard-command-routing"></a>Überschreiben des Standardbefehlsroutings
In seltenen Fällen, wenn Sie eine Variante des standardframeworkressourcen routing implementieren müssen können Sie sie überschreiben. Das Konzept ist so ändern Sie das routing in eine oder mehrere Klassen durch Außerkraftsetzen von `OnCmdMsg` in diesen Klassen. Wenn Sie dies tun:  
  
-   In der Klasse, die die Reihenfolge der Übergabe an ein nicht standardmäßiges-Objekt zu beeinträchtigen.  
  
-   Neues Objekt in den nicht standardmäßigen oder in Befehlsziele kann wiederum Befehle übergeben werden.  
  
 Wenn Sie ein neues Objekt in das routing einfügen, muss die Klasse einen Befehlsziel Klasse. In der überschreibenden Versionen von `OnCmdMsg`, achten Sie darauf, dass Sie die Version abzurufen, die Sie überschreiben möchten. Finden Sie unter der [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) Memberfunktion der Klasse `CCmdTarget` in der *MFC-Referenz* und die Versionen in Klassen wie `CView` und `CDocument` in den angegebenen Quellcode Beispiele.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

