---
title: "Prozess"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "Process"
  - "process_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], Prozess"
  - "process __declspec-Schlüsselwort"
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Prozess
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass der verwaltete Anwendungsprozess eine einzelne Kopie einer bestimmten globalen Variablen, einer statischen Membervariablen oder einer statischen lokalen Variablen haben soll, die von allen Anwendungsdomänen im Prozess verwendet wird.  Dies ist in erster Linie für die Verwendung bei der Kompilierung mit **\/clr:pure** vorgesehen, da bei **\/clr:pure** standardmäßig globale und statische Variablen in der Anwendungsdomäne gültig sind.  Beim Kompilieren mit **\/clr** sind globale und statische Variablen standardmäßig Variablen pro Prozess \(`__declspec(process)` muss nicht verwendet werden\).  
  
 Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable des systemeigenen Typs können durch `__declspec(process)` markiert werden.  
  
 Beim Kompilieren mit **\/clr:pure** müssen die Variablen, die als Variablen pro Prozess markiert sind, ebenfalls als `const` deklariert werden.  Dadurch wird sichergestellt, dass prozessspezifische Variablen nicht in einer Anwendungsdomäne geändert werden und in einer anderen Anwendungsdomäne unerwartete Ergebnisse liefern.  Der wichtigste Verwendungszweck von `__declspec(process)` besteht in der Initialisierung einer globalen Variablen, statischen Membervariablen oder statischen lokalen Variablen unter **\/clr:pure** zur Kompilierungszeit.  
  
 `process` ist nur gültig beim Kompilieren mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md) oder **\/clr:pure** und ist beim Kompilieren mit **\/clr:safe** ungültig.  
  
 Wenn jede Anwendungsdomäne eine eigene Kopie einer globalen Variablen haben soll, verwenden Sie [appdomain](../cpp/appdomain.md).  
  
 Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)