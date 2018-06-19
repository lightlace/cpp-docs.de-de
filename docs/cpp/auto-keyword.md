---
title: Auto-Schlüsselwort | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93b2f5e28dc0306a996b4c8bdb799122fe4646ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409998"
---
# <a name="auto-keyword"></a>Auto-Schlüsselwort
Das `auto`-Schlüsselwort ist ein Deklarationsspezifizierer. Der C++-Standard definiert jedoch eine ursprüngliche und eine überarbeitete Bedeutung für dieses Schlüsselwort. Vor Visual C++ 2010 die `auto` -Schlüsselwort deklariert eine Variable in der *automatische* Speicherklasse, d. h. eine Variable, die eine lokale Lebensdauer verfügt. Ab Visual C++ 2010 die `auto` -Schlüsselwort deklariert eine Variable, deren Typ, aus der Initialisierungsausdruck in der Deklaration abgeleitet wird. Die [/Zc: Auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) -Compileroption steuert die Bedeutung der `auto` Schlüsselwort.  
  
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