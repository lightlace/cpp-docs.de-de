---
title: Prozess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: process_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6754adcb348cb6eb061e32fc58e78f43663b1a90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="process"></a>process
Gibt an, dass der verwaltete Anwendungsprozess eine einzelne Kopie einer bestimmten globalen Variablen, einer statischen Membervariablen oder einer statischen lokalen Variablen haben soll, die von allen Anwendungsdomänen im Prozess verwendet wird. Dies wird hauptsächlich verwendet werden, bei der Kompilierung mit **/CLR: reine**, da unter **/CLR: reine** globale und statische Variablen pro Anwendungsdomäne, in der Standardeinstellung sind. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet. Beim Kompilieren mit **"/ CLR"**, globale und statische Variablen pro Prozess in der Standardeinstellung werden (nicht verwenden, müssen `__declspec(process)`.  
  
 Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable des systemeigenen Typs können durch `__declspec(process)` markiert werden.  
  
 Beim Kompilieren mit **/CLR: pure**, Variablen pro Prozess markiert sind, müssen auch als deklariert werden `const`. Dadurch wird sichergestellt, dass prozessspezifische Variablen nicht in einer Anwendungsdomäne geändert werden und in einer anderen Anwendungsdomäne unerwartete Ergebnisse liefern. Der wichtigste Verwendungszweck von `__declspec(process)` ist die Aktivierung der Kompilierung Initialisierung einer globalen Variablen, statischen Membervariablen oder statischen lokalen Variablen unter **/CLR: pure**.  
  
 `process`gilt nur beim Kompilieren mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) oder **/CLR: pure** und ist nicht zulässig, bei der Kompilierung mit **/CLR: safe**.  
  
 Wenn Sie jede Anwendungsdomäne eine eigene Kopie einer globalen Variablen haben soll, verwenden Sie [Appdomain](../cpp/appdomain.md).  
  
 Finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)