---
title: Compiler-Fehler C3744 | Microsoft-Dokumentation
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: f6cd256454b51a103d9c4249b050c8c05781bc78
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744
__unhook muss wenigstens 3 Argumente für verwaltete Ereignisse haben  
  
 Die [__unhook](../../cpp/unhook.md) Funktion muss akzeptiert drei Parameter, wenn Sie in einem Programm verwendet werden soll, die für Managed Extensions for C++ kompiliert wird.  
  
 `__hook`und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.  
  
 C3744 ist nur erreichbar, mit der veralteten-Compileroption **/CLR: oldSyntax**.  

