---
title: "Auto-Schlüsselwort | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: auto_cpp
dev_langs: C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3508217e7dc333543fa2dbff9cf0643d6faff060
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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