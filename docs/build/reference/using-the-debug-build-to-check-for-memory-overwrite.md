---
title: "Verwenden die Debugbuilds zur Suche nach Speicherüberschreibungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b8fc223a1e4e1162ce99bb3275152c49828aa99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen
Sie müssen Ihr Projekt für das Debuggen neu, um das Debugbuild verwenden, um nach speicherüberschreibungen zu überprüfen, erstellen. Wechseln Sie anschließend an den Anfang Ihrer Anwendung `InitInstance` Funktion, und fügen Sie die folgende Zeile hinzu:  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 Der Debug-Speicherreservierungsfunktion setzt Guard Bytes um aller speicherbelegungen. Diesen Schutz jedoch Bytes nicht gut ausführen, es sei denn, Sie überprüfen, ob sie geändert wurden (die eine speicherüberschreibungen hinweist). Andernfalls ermöglichen Sie dies nur einen Puffer bereitstellt, der in der Tat kann Ihnen, sofort mit einer Überschreibung Arbeitsspeicher abzurufen.  
  
 Durch das Einschalten der `checkAlwaysMemDF`, Sie erzwingen, dass MFC ermöglicht, einen Aufruf der `AfxCheckMemory` Funktion jedes Mal einen Aufruf von **neue** oder **löschen** erfolgt. Wenn ein speicherüberschreibungen erkannt wurde, wird eine Ablaufverfolgungsmeldung generiert, die in etwa wie folgt aussieht:  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Wenn Sie eine der folgenden Meldungen angezeigt wird, müssen Sie den Code zu ermitteln, wo die Beschädigung aufgetreten schrittweise durchlaufen. Um zu isolieren, genauer gesagt, in der speicherüberschreibungen aufgetreten ist, können Sie explizite Aufrufe vornehmen `AfxCheckMemory` selbst. Zum Beispiel:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Wenn die erste Bestätigung ist erfolgreich, und das zweite Argument fehlschlägt, bedeutet dies, dass das Überschreiben des Arbeitsspeichers in der Funktion zwischen den beiden aufrufen aufgetreten sind, muss.  
  
 Je nach Art der Anwendung, können Sie gefunden werden, `afxMemDF` bewirkt, dass das Programm zu langsam ausgeführt wird, um selbst zu testen. Die `afxMemDF` Variable bewirkt, dass `AfxCheckMemory` für jeden Aufruf zum neuen aufgerufen werden, und löschen. In diesem Fall sollten Sie Ihre eigenen Aufrufe für Punktdiagramm `AfxCheckMemory`(), wie oben dargestellt, und wiederholen Sie den Arbeitsspeicher zu isolieren, überschreiben Sie auf diese Weise.  
  
## <a name="see-also"></a>Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)