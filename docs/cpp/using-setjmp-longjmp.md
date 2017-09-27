---
title: Verwenden von Setjmp Longjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- longjmp
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- SETJMPEX.H
- longjmp function in C++ programs
- SETJMP.H
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
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
ms.openlocfilehash: 356924c0a93f6d9d21bb417f84836385491b2144
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="using-setjmplongjmp"></a>Verwenden von "setjmp/longjmp"
Wenn [Setjmp](../c-runtime-library/reference/setjmp.md) und [Longjmp](../c-runtime-library/reference/longjmp.md) werden zusammen verwendet werden, sie bieten eine Möglichkeit zum Ausführen eines nicht lokalen `goto`. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen zu verwenden.  
  
> [!CAUTION]
>  `setjmp` und `longjmp` unterstützen jedoch die C++-Objektsemantik nicht und beeinträchtigen möglicherweise die Leistung, indem sie die Optimierung für lokale Variablen verhindern. Aus diesem Grund wird empfohlen, sie nicht in C++-Programmen zu verwenden. Wir empfehlen die Verwendung `try` / `catch` stattdessen erstellt.  
  
 Wenn Sie verwenden möchten `setjmp` / `longjmp` auch SETJMP in einem C++-Programm einschließen. H oder SETJMPEX. H, um die ordnungsgemäße Interaktion zwischen den Funktionen und C++-Ausnahmebehandlung zu gewährleisten. Bei Verwendung von [/EH](../build/reference/eh-exception-handling-model.md) zum Kompilieren, werden Destruktoren für lokale Objekte während der stapelentladung aufgerufen. Bei Verwendung von **/EHs** zu kompilieren, und eine der Funktionen-Aufrufe eine Funktion, die verwendet [Nothrow](../cpp/nothrow-cpp.md) und die Funktion, die verwendet `nothrow` Aufrufe `longjmp`, und klicken Sie dann die Entladung Destruktor nicht auftreten kann, Abhängig von der Optimierer.  
  
 In portablem Code ist bei Ausführung eines nicht lokalen `goto`, das `longjmp` aufruft, die ordnungsgemäße Zerstörung von framebasierten Objekten möglicherweise unzuverlässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)
