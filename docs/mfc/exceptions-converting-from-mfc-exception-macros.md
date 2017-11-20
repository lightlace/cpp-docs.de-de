---
title: 'Ausnahmen: Umwandeln von MFC-Ausnahmemakros | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 51c48e486eb3636d2151fb52ba301b1057d5f3e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Ausnahmen: Umwandeln von MFC-Ausnahmemakros
Dies ist ein-Thema für fortgeschrittene.  
  
 In diesem Artikel wird erläutert, wie das Konvertieren von vorhandenem Code, die mit Microsoft Foundation Class-Makros geschrieben – **versuchen Sie es**, **CATCH**, **AUSLÖSEN**usw. – verwenden Sie die C++-Ausnahmebehandlung Schlüsselwörter **versuchen**, **catch**, und `throw`. Folgende Themen werden behandelt:  
  
-   [Vorteile der Konvertierung](#_core_advantages_of_converting)  
  
-   [Konvertieren von Code mit von Ausnahmemakros mit C++-Ausnahmen](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a>Vorteile der Konvertierung  
 Eher führen Sie nicht notwendig zum Konvertieren von vorhandenem Code, obwohl Sie Unterschiede zwischen der Implementierung in früheren Versionen und die Makro-Implementierungen in MFC-Version 3.0 bewusst sein sollten. Diese Unterschiede und die nachfolgenden Änderungen im Code Verhalten werden in erläutert [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
 Die Hauptvorteile von konvertiert werden:  
  
-   Code, in der C++-Schlüsselwörter für die Ausnahmebehandlung verwendet, die in einer etwas kleiner kompiliert werden. EXE-Datei oder. DLL.  
  
-   Die C++-Ausnahmebehandlung Schlüsselwörter sind flexibler: sie können Behandeln von Ausnahmen eines beliebigen Datentyps, die kopiert werden können (`int`, **"float"**, `char`usw.), während die Makros Klasse nurAusnahmenbehandeln`CException` und davon abgeleitete Klassen.  
  
 Der Hauptunterschied zwischen die Makros und die Schlüsselwörter ist, verwenden die Makros "automatisch" Code eine abgefangene Ausnahme gelöscht, wenn die Ausnahme den Gültigkeitsbereich verlässt. Code mit die Schlüsselwörtern nicht der Fall, können Sie eine abgefangene Ausnahme explizit löschen müssen. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Ein weiterer Unterschied ist die Syntax. Die Syntax für Schlüsselwörter und Makros unterscheidet sich in drei Hinsicht:  
  
1.  Makroargumente und Ausnahmedeklarationen:  
  
     Ein **CATCH** Makroaufruf hat die folgende Syntax:  
  
     **CATCH (** *Exception_class*, *Exception_object_pointer_name* **)**  
  
     Beachten Sie das Komma zwischen den Klassennamen und den Objektnamen des Zeigers ein.  
  
     Die Ausnahmedeklaration für die **catch** -Schlüsselwort verwendet diese Syntax:  
  
     **catch (** *Exception_type* *Exception_name***)**  
  
     Diese Ausnahme deklarationsanweisung gibt den Typ der Ausnahme im Catch-Block behandelt.  
  
2.  Trennung von Catch-Blöcken:  
  
     Mit den Makros die **CATCH** Makros (mit den Argumenten) beginnt, den ersten Catch-Block; das `AND_CATCH` Makros beginnt nachfolgende Catch-Blöcke und die `END_CATCH` Makro beendet die Abfolge der Catch-Blöcken.  
  
     Mit den Schlüsselwörtern die **catch** -Schlüsselwort (mit der Ausnahmedeklaration) beginnt jede Catch-Block. Es gibt keine Entsprechung, um die `END_CATCH` -Makro; Catch blockieren endet mit der schließenden Klammer.  
  
3.  Der Throw-Ausdruck:  
  
     Verwenden Sie die Makros `THROW_LAST` die aktuelle Ausnahme erneut ausgelöst. Die `throw` -Schlüsselwort, ohne Argument hat dieselbe Wirkung.  
  
##  <a name="_core_doing_the_conversion"></a>Die Konvertierung  
  
#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>So konvertieren Sie Code mithilfe von Makros zur Verwendung der C++-Ausnahmebehandlung-Schlüsselwörter  
  
1.  Suchen Sie alle Vorkommen von MFC-Makros **versuchen**, **CATCH**, `AND_CATCH`, `END_CATCH`, **AUSLÖSEN**, und `THROW_LAST`.  
  
2.  Ersetzen Sie oder löschen Sie alle Vorkommen der folgenden Makros:  
  
     **Wiederholen Sie den** (ersetzen Sie diesen **versuchen**)  
  
     **ABFANGEN** (ersetzen Sie diesen **catch**)  
  
     `AND_CATCH`(Ersetzen Sie diesen **catch**)  
  
     `END_CATCH`(Löschen)  
  
     **LÖST** (ersetzen Sie diesen `throw`)  
  
     `THROW_LAST`(Ersetzen Sie diesen `throw`)  
  
3.  Ändern Sie das Makroargumente, sodass diese Ausnahmedeklarationen ungültig bilden.  
  
     Ändern Sie z. B.  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     auf  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  Ändern Sie den Code im Catch-Blöcken, sodass Ausnahmeobjekte nach Bedarf löscht. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Hier ist ein Beispiel für Ausnahmebehandlungscode mithilfe von MFC-Ausnahmemakros. Beachten Sie, dass, da der Code im folgenden Beispiel wird die Makros, die Ausnahme verwendet `e` automatisch gelöscht wird:  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 Der Code im nächsten Beispiel verwendet die C++-Ausnahmeschlüsselwörter, damit die Ausnahme muss explizit gelöscht werden:  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

