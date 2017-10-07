---
title: Bool (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f2437d831ae155f916b69cc6b35d3b586be9819e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bool-c"></a>bool (C++)
Dieses Schlüsselwort ist ein integrierter Typ. Eine Variable dieses Typs kann Werte haben ["true"](../cpp/true-cpp.md) und ["false"](../cpp/false-cpp.md). Bedingte Ausdrücke weisen den Typ `bool` auf und haben daher Werte vom Typ `bool`. Beispielsweise `i!=0` verfügt jetzt über **"true"** oder **"false"** abhängig vom Wert des `i`.  

**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Präfix oder Postfix-Inkrement oder Dekrement Operator möglicherweise nicht vom Typ `bool`. 
  
 Die Werte **"true"** und **"false"** weisen folgende Beziehung:  
  
```  
!false == true  
!true == false  
```  
  
 Betrachten Sie folgende Anweisung:  
  
```  
if (condexpr1) statement1;   
```  
  
 Wenn `condexpr1` ist **"true"**, `statement1` wird immer ausgeführt; Wenn `condexpr1` ist **"false"**, `statement1` nie ausgeführt wird.  
  
 Wenn Sie einen Postfix- oder Präfix `++` Operator angewendet wird, um eine Variable vom Typ `bool`, die Variable wird festgelegt, um **"true"**. 
**Visual Studio 2017 15,3 und höher**: Operator++ für Bool wurde aus der Sprache entfernt und wird nicht mehr unterstützt.

Der Postfix- oder Präfix-Operator `--` kann nicht auf eine Variable dieses Typs angewendet werden.  
  
 Der `bool`-Typ ist an ganzzahligen Erweiterungen beteiligt. Ein rvalue vom Typ `bool` konvertiert werden kann, um einen Rvalue vom Typ `int`, mit **"false"** 0 (null) und **"true"** 1. Als gesonderter Typ ist `bool` an der Überladungsauflösung beteiligt.  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)
