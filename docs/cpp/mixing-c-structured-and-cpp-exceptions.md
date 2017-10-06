---
title: Mischen von C (strukturiert)- und C++-Ausnahmen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 074ff13ed281d30caeede227cdab2cff090fab1e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="mixing-c-structured-and-c-exceptions"></a>Kombination von C (strukturiert)- und C++-Ausnahmen
Wenn Sie besser portierbaren Code schreiben möchten, wird das Verwenden der strukturierten Ausnahmebehandlung in einem C++-Programm nicht empfohlen. Möchten Sie jedoch möglicherweise manchmal mit Kompilieren **/EHa** strukturierte Ausnahmen und C++-Quellcode kombinieren und benötigen daher einige Funktionen zur Behandlung beider Arten von Ausnahmen. Da ein strukturierter Ausnahmehandler kein Konzept von Objekten oder typisierten Ausnahmen verfügt, wird es kann nicht von C++-Code ausgelöste Ausnahmen behandelt; Allerdings C++ **catch** Handler strukturierte Ausnahmen behandeln können. Als solche, C++-ausnahmebehandlungssyntax (**versuchen**, `throw`, **catch**) wird nicht akzeptiert, durch den C-Compiler, aber strukturierte ausnahmebehandlungssyntax (`__try`, `__except`, `__finally`) wird vom C++-Compiler unterstützt.  
  
 Finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Informationen zur Behandlung von strukturierte Ausnahmen als C++-Ausnahmen.  
  
 Wenn Sie strukturierte und C++-Ausnahmen kombinieren, beachten Sie Folgendes:  
  
1.  C++-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.  
  
2.  Beendigungshandler (`__finally`-Blöcke) werden immer ausgeführt, sogar während des Entladens, nachdem eine Ausnahme ausgelöst wird.  
  
3.  C++-Ausnahmebehandlung abfangen und Beibehalten von entladungssemantik in allen Modulen mit kompiliert die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption (diese Option aktiviert die entladungssemantik).  
  
4.  Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden. Wenn beispielsweise eine strukturierte Ausnahme beim Versuch auftritt, einen Funktionsaufruf über einen nicht initialisierten Funktionszeiger auszuführen, und diese Funktion Objekte als Parameter nutzt, die vor dem Aufruf erstellt wurden, werden die Destruktoren dieser Objekte nicht während der Stapelentladung aufgerufen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von Setjmp oder Longjmp in C++-Programmen](../cpp/using-setjmp-longjmp.md)  
  
-   [Unterschiede zwischen SEH und C++ EH](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
