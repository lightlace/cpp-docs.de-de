---
title: 'Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c50e7358d29e04c81a5e443d5b1a03881fed7f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen
Dieser Artikel beschreibt Überlegungen zum Schreiben von Code, der die Behandlung von Ausnahmen von MFC-Makros und C++-Ausnahmebehandlung-Schlüsselwörter verwendet.  
  
 In diesem Artikel werden die folgenden Themen behandelt:  
  
-   [Das Mischen von Ausnahmeschlüsselwörter und Makros](#_core_mixing_exception_keywords_and_macros)  
  
-   [Try-Blöcke in Catch-Blöcken](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> Das Mischen von Ausnahmeschlüsselwörter und Makros  
 Sie können MFC-Ausnahmemakros und C++-Ausnahmeschlüsselwörter im selben Programm kombinieren. Aber Sie können nicht von MFC-Makros mit C++-Ausnahmeschlüsselwörter im selben Block kombinieren, da die Makros Ausnahmeobjekte automatisch gelöscht, wenn sie außerhalb des gültigen Bereichs, gehen Sie während der Code unter Verwendung der Schlüsselwörter für die Ausnahmebehandlung nicht der Fall ist. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Der Hauptunterschied zwischen die Makros und die Schlüsselwörter besteht darin, dass die Makros "automatisch" eine abgefangene Ausnahme löschen, wenn die Ausnahme den Gültigkeitsbereich verlässt. Code mit den Schlüsselwörtern nicht; Ausnahmen, die in einem Catchblock abgefangen müssen explizit gelöscht werden. Kombinieren von Makros und C++-Ausnahmeschlüsselwörter kann Speicherverluste verursachen, wenn ein Ausnahmeobjekt nicht gelöscht wird, oder zur Beschädigung des Heaps, wenn eine Ausnahme zweimal gelöscht wird.  
  
 Der folgende Code wird z. B. den Ausnahmezeiger ungültig:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 Das Problem tritt auf, weil `e` wird gelöscht, wenn die Ausführung außerhalb der "inneren" übergibt **CATCH** Block. Mithilfe der `THROW_LAST` Makro anstelle von der **AUSLÖSEN** Anweisung bewirkt, dass die "äußere" **CATCH** Block, um einen gültigen Zeiger zu erhalten:  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try-Blöcke in Catch-Blöcken  
 Sie können nicht die aktuelle Ausnahme erneut auslösen, innerhalb einer **versuchen** Block, der innerhalb einer **CATCH** Block. Im folgende Beispiel ist ungültig:  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

