---
title: Bool (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d5a8a86cfcc64b70e4910079461513c34fc7d0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2018
---
# <a name="bool-c"></a>bool (C++)

Dieses Schlüsselwort ist ein integrierter Typ. Eine Variable dieses Typs kann Werte haben ["true"](../cpp/true-cpp.md) und ["false"](../cpp/false-cpp.md). Bedingte Ausdrücke weisen den Typ `bool` auf und haben daher Werte vom Typ `bool`. Beispielsweise `i!=0` verfügt jetzt über **"true"** oder **"false"** abhängig vom Wert des `i`.  

**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Präfix oder Postfix-Inkrement oder Dekrement Operator möglicherweise nicht vom Typ **Bool**. Angenommen, dass heißt, eine Variable **b** des Typs **Bool**, diese Ausdrücke sind nicht mehr erlaubt:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Die Werte **"true"** und **"false"** weisen folgende Beziehung:  
  
```cpp  
!false == true  
!true == false  
```  
  
Betrachten Sie folgende Anweisung:  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Wenn `condexpr1` ist **"true"**, `statement1` wird immer ausgeführt; Wenn `condexpr1` ist **"false"**, `statement1` nie ausgeführt wird.  
  
Wenn Sie einen Postfix- oder Präfix **++** Operator angewendet wird, um eine Variable vom Typ **Bool**, die Variable wird festgelegt, um **"true"**. 
**Visual Studio 2017 15,3 und höher**: Operator++ für **Bool** wurde aus der Sprache entfernt und wird nicht mehr unterstützt.

Der Postfix- oder Präfix **--** Operator kann nicht auf eine Variable dieses Typs angewendet werden.  
  
 Die **Bool** Typ ganzzahligen Erweiterungen beteiligt. Ein rvalue vom Typ **Bool** konvertiert werden kann, um einen Rvalue vom Typ **Int**, mit **"false"** 0 (null) und **"true"** 1. Als gesonderter Typ ist **Bool** an der überladungsauflösung beteiligt ist.  
  
## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Grundlegende Typen](../cpp/fundamental-types-cpp.md)<br/>
