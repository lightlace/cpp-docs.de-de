---
title: Kombination von C (strukturiert)- und C++-Ausnahmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495f0fe9faf0c75257f2ac7bbe0a3457438ffdf9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942041"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Kombination von C (strukturiert)- und C++-Ausnahmen
Wenn Sie besser portierbaren Code schreiben möchten, wird das Verwenden der strukturierten Ausnahmebehandlung in einem C++-Programm nicht empfohlen. Allerdings unter Umständen möchten Sie Kompilieren mit **/EHa** und strukturierte Ausnahmen und C++-Quellcode kombinieren und benötigen daher einige Funktionen zur Behandlung beider Arten von Ausnahmen. Da ein strukturierter Ausnahmehandler kein Konzept für die Objekte oder von typisierten Ausnahmen verfügt, kann nicht es von C++-Code ausgelöste Ausnahmen zu behandeln; jedoch C++ **catch** Handler können strukturierte Ausnahmen behandeln. Als solche, C++-ausnahmebehandlungssyntax (**versuchen**, **auslösen**, **catch**) wird nicht akzeptiert werden, durch den C-Compiler, aber strukturierte ausnahmebehandlungssyntax (**__try** , **__except**, **__finally**) wird von der C++-Compiler unterstützt.  
  
 Finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Informationen zur Behandlung strukturierter Ausnahmen als C++-Ausnahmen.  
  
 Wenn Sie strukturierte und C++-Ausnahmen kombinieren, beachten Sie Folgendes:  
  
1.  C++-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.  
  
2.  Beendigungshandler (**__finally** Blöcke) werden immer ausgeführt, sogar während des Entladens, nachdem eine Ausnahme ausgelöst wird.  
  
3.  C++-Ausnahmebehandlung kann abfangen und Beibehalten von entladungssemantik in allen Modulen mit kompiliert die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption (diese Option aktiviert die entladungssemantik).  
  
4.  Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden. Wenn beispielsweise eine strukturierte Ausnahme beim Versuch auftritt, einen Funktionsaufruf über einen nicht initialisierten Funktionszeiger auszuführen, und diese Funktion Objekte als Parameter nutzt, die vor dem Aufruf erstellt wurden, werden die Destruktoren dieser Objekte nicht während der Stapelentladung aufgerufen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von Setjmp oder Longjmp in C++-Programmen](../cpp/using-setjmp-longjmp.md)  
  
-   [Unterschiede zwischen SEH und C++-EH](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)