---
title: Compilerfehler C3744 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f96b8445c343bdd4f606157e692c4d6ce262e369
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744
__unhook muss mindestens 3 Argumente für verwaltete Ereignisse haben.  
  
 Die [__unhook](../../cpp/unhook.md) -Funktion muss akzeptiert drei Parameter bei Verwendung in einem Programm, das für Managed Extensions für C++ kompiliert wird.  
  
 `__hook` und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.  
  
 C3744 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
