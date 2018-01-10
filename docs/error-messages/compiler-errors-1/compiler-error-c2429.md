---
title: Compilerfehler Fehler C2429 | Microsoft Docs
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2429
dev_langs: C++
helpviewer_keywords: C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6882804d1ddf2e4f83947e310cde4c8c114120d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2429"></a>Compilerfehler Fehler C2429

> "*Sprachfunktion*"erfordert compilerkennzeichen"*Compileroption*"

Die Language-Funktion erfordert eine bestimmte Compileroption für die Unterstützung.

Der Fehler **C2429: Sprachfunktion 'geschachtelt-Namespace-Definition' erfordert compilerkennzeichen "/ Std:c ++ 17'** wird generiert, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere enthält, Bereich geschachtelt Namespacenamen, Visual Studio 2015 Update 5 ab. (In Visual Studio 2017 Version 15.3, die **/std:c ++ neueste** Schalter ist erforderlich.) Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Der Compiler unterstützt zusammengesetzten Namespacedefinitionen bei der [/std:c ++ 17](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben ist:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
