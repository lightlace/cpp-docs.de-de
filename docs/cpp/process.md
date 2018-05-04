---
title: Prozess | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa1ba2676ebbd04d1fc1a59d210d69efeab6658
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="process"></a>process
Gibt an, dass der verwaltete Anwendungsprozess eine einzelne Kopie einer bestimmten globalen Variablen, einer statischen Membervariablen oder einer statischen lokalen Variablen haben soll, die von allen Anwendungsdomänen im Prozess verwendet wird. Dies wurde hauptsächlich verwendet werden, bei der Kompilierung mit **/CLR: pure**, die ist inzwischen veraltet und wird in einer zukünftigen Version des Compilers entfernt. Beim Kompilieren mit **"/ CLR"**, globale und statische Variablen pro Prozess in der Standardeinstellung werden (nicht verwenden, müssen `__declspec(process)`.  
  
 Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable des systemeigenen Typs können durch `__declspec(process)` markiert werden.  
  
  
 `process` gilt nur beim Kompilieren mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Wenn Sie jede Anwendungsdomäne eine eigene Kopie einer globalen Variablen haben soll, verwenden Sie [Appdomain](../cpp/appdomain.md).  
  
 Finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)