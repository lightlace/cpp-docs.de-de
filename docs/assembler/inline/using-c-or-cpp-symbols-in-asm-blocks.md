---
title: "Verwenden von C- oder C++-Symbolen in __asm-Blöcken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6a39b747c8c576d148bafff19a664a95fcb43e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>Verwenden von C- oder C++-Symbolen in __asm-Blöcken
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Ein `__asm` Block kann finden Sie in einem C- oder C++-Symbol im Bereich, in dem der Block wird angezeigt. (C und C++ Symbole sind, Variablennamen, Funktionsnamen, und Bezeichnungen; die Namen, die keine symbolische Konstanten sind oder `enum` Elemente. Sie können keine C++ Memberfunktionen aufrufen.)  
  
 Die Verwendung von C und C++-Symbolen gelten einige Einschränkungen:  
  
-   Jede assemblysprachanweisung darf nur eine C- oder C++-Symbol. Mehrere Symbole angezeigt werden können, in der gleichen Assemblyanweisung nur mit **Länge**, **Typ**, und **Größe** Ausdrücke.  
  
-   Funktionen, die auf die verwiesen wird einer `__asm` Block muss zuvor in der Anwendung (Prototypen) deklariert werden. Andernfalls der Compiler kann nicht unterschieden Funktionsnamen und Bezeichnungen in der `__asm` Block.  
  
-   Ein `__asm` Block kann keine Symbole C- oder C++ verwenden, mit der gleichen Schreibweise wie MASM reservierte Wörter (unabhängig von der Schreibweise). MASM-reservierte Wörter enthalten Anweisungsnamen, z. B. **PUSH** und Namen, z. B. SI zu registrieren.  
  
-   Struktur- und Union-Tags werden nicht erkannt. `__asm` blockiert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)