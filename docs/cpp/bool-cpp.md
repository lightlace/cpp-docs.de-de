---
title: Bool (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 058979420e5bb1426879522e70ec8b1ac768d9cc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407402"
---
# <a name="bool-c"></a>bool (C++)

Dieses Schlüsselwort ist ein integrierter Typ. Eine Variable dieses Typs kann Werte haben ["true"](../cpp/true-cpp.md) und ["false"](../cpp/false-cpp.md). Bedingte Ausdrücke weisen den Typ **"bool"** und haben daher Werte vom Typ **"bool"**. Z. B. `i!=0` hat jetzt abhängig vom Wert "true" oder "false" `i`.  

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Präfix oder Postfix-Inkrement oder Dekrement Operator möglicherweise nicht vom Typ **"bool"**. Angenommen, das heißt, eine Variable `b` des Typs **"bool"**, diese Ausdrücke sind nicht mehr erlaubt:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Die Werte "true" und "false" haben folgende Beziehung:  
  
```cpp  
!false == true  
!true == false  
```  
  
Betrachten Sie folgende Anweisung:  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Wenn `condexpr1` ist "true", `statement1` wird immer ausgeführt; Wenn `condexpr1` ist "false", `statement1` niemals ausgeführt.  
  
Wenn Sie einen Postfix- oder Präfix **++** Operator angewendet wird, um eine Variable vom Typ **"bool"**, die Variable auf "true" festgelegt ist. 
**Visual Studio 2017 Version 15.3 und höher**: "Operator++" für **"bool"** wurde von der Sprache entfernt und wird nicht mehr unterstützt.

Der Postfix- oder Präfix **--** Operator kann nicht auf eine Variable dieses Typs angewendet werden.  
  
 Die **"bool"** Typ ganzzahligen Erweiterungen beteiligt. Ein rvalue vom Typ **"bool"** konvertiert werden kann, um einen Rvalue vom Typ **Int**, mit "false" immer 0 (null) und "true" 1. Als gesonderter Typ ist **"bool"** an der überladungsauflösung beteiligt ist.  
  
## <a name="see-also"></a>Siehe auch
[Schlüsselwörter](../cpp/keywords-cpp.md)  
[Grundlegende Typen](../cpp/fundamental-types-cpp.md)  