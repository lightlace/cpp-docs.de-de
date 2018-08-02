---
title: Verwenden von Setjmp-Longjmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2073729fc5445fc36e3d8a6f52c4f69b079c8b47
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462130"
---
# <a name="using-setjmplongjmp"></a>Verwenden von "setjmp/longjmp"
Wenn [Setjmp](../c-runtime-library/reference/setjmp.md) und [Longjmp](../c-runtime-library/reference/longjmp.md) werden zusammen verwendet werden, sie bieten eine Möglichkeit zum Ausführen eines nicht lokalen **Goto**. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen zu verwenden.  
  
> [!CAUTION]
>  Aber da **Setjmp** und **Longjmp** C++-Objektsemantik nicht unterstützt, und da möglicherweise die Leistung beeinträchtigen durch Verhindern von Optimierung für lokale Variablen, es wird empfohlen, dass Sie nicht verwenden Diese im C++-Programme. Wir empfehlen die Verwendung **versuchen**/**catch** stattdessen erstellt.  
  
 Wenn Sie verwenden möchten **Setjmp**/**Longjmp** auch in einem C++-Programm enthalten \<setjmp.h > oder \<setjmpex.h > um ordnungsgemäße Interaktion zwischen gewährleisten die Funktionen und C++-Ausnahmebehandlung. Bei Verwendung von [/EH](../build/reference/eh-exception-handling-model.md) zum Kompilieren, werden die Destruktoren für lokale Objekte während der stapelentladung aufgerufen. Bei Verwendung von **/EHs** kompilieren und eine Ihrer Functions-Aufrufe, eine Funktion, die verwendet [Nothrow](../cpp/nothrow-cpp.md) und die Funktion, die verwendet **Nothrow** Aufrufe **Longjmp**, und klicken Sie dann die Entladung der Destruktor nicht abhängig vom Optimierer auftreten kann.  
  
 In übertragbarem Code, wenn eine nicht lokale **Goto** aufruft, **Longjmp** ausgeführt wird, ordnungsgemäße Zerstörung von framebasierten Objekten möglicherweise unzuverlässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)