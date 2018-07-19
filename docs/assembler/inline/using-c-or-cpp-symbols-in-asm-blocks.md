---
title: Verwenden von C- oder C++-Symbolen in __asm-Blöcken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746614de653649747bf20ae4c223e5687ee53f5c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049426"
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