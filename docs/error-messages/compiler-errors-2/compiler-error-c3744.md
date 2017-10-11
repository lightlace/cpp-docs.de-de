---
title: Compilerfehler C3744 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 87df3fd92ac3fcad9b3e87f02f16b8151e678b77
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744
__unhook muss mindestens 3 Argumente für verwaltete Ereignisse haben.  
  
 Die [__unhook](../../cpp/unhook.md) -Funktion muss akzeptiert drei Parameter bei Verwendung in einem Programm, das für Managed Extensions für C++ kompiliert wird.  
  
 `__hook`und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.  
  
 C3744 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  

