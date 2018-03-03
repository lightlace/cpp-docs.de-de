---
title: Verwendung von strukturierter Ausnahmebehandlung in C++ | Microsoft Docs
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
- C++ exception handling, mixed with SEH
- structured exception handling [C++], with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db5d067a391512d56a2d01ce3052ac3fab061f28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-structured-exception-handling-with-c"></a>Verwendung von strukturierter Ausnahmebehandlung in C++
Die in diesen Artikeln beschriebene strukturierte Ausnahmebehandlung funktioniert sowohl mit C- als auch mit C++-Quelldateien. Sie wurde jedoch nicht speziell für C++ entwickelt und wird daher nicht empfohlen. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Der C++-Ausnahmebehandlungsmechanismus ist außerdem flexibler, da er Ausnahmen eines beliebigen Typs behandeln kann.  
  
 Microsoft C++ unterstützt jetzt das C++-Ausnahmebehandlungsmodell auf Grundlage des ANSI C++-Standards. Dieser Mechanismus behandelt automatisch die Zerstörung lokaler Objekte während der Stapelentladung. Wenn Sie fehlertoleranten C++-Code schreiben und die Ausnahmebehandlung implementieren möchten, wird dringend empfohlen, die C++-Ausnahmebehandlung zu verwenden und nicht die strukturierte Ausnahmebehandlung. (Beachten Sie Folgendes: Der C++-Compiler unterstützt Konstrukte für die strukturierte Ausnahmebehandlung, wie in diesen Artikeln beschrieben, der standardmäßige C-Compiler unterstützt die C++-Ausnahmebehandlungssyntax jedoch nicht.) Ausführliche Informationen über die C++-Ausnahmebehandlung finden Sie unter [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md) und *Annotated C++ Reference Manual* von Margaret Ellis und Bjarne Stroustrup.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)