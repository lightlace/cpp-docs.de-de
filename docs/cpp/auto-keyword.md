---
title: "Auto-Schlüsselwort | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0413fd47b486cf1613b7c249b93e6a3507a5577c
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="auto-keyword"></a>Auto-Schlüsselwort
Das `auto`-Schlüsselwort ist ein Deklarationsspezifizierer. Der C++-Standard definiert jedoch eine ursprüngliche und eine überarbeitete Bedeutung für dieses Schlüsselwort. Vor Visual C++ 2010 die `auto` -Schlüsselwort deklariert eine Variable in der *automatische* Speicherklasse, d. h. eine Variable, die eine lokale Lebensdauer verfügt. Ab Visual C++ 2010 die `auto` -Schlüsselwort deklariert eine Variable, deren Typ, aus der Initialisierungsausdruck in der Deklaration abgeleitet wird. Die [/Zc: Auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) -Compileroption steuert die Bedeutung der `auto` Schlüsselwort.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Definition des `auto`-Schlüsselworts ändert sich in der Programmiersprache C++, aber nicht in der Programmiersprache C.  
  
 In den folgenden Themen wird das `auto`-Schlüsselwort und die entsprechende Compileroption beschrieben:  
  
-   [automatische](../cpp/auto-cpp.md) beschreibt die neue Definition die `auto` Schlüsselwort.  
  
  
-   [/ Zc: Auto (Variablentyp ableiten)](../build/reference/zc-auto-deduce-variable-type.md) wird beschrieben, die Compileroption ", die dem Compiler, die Definition anweist der `auto` Schlüsselwort zu verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
