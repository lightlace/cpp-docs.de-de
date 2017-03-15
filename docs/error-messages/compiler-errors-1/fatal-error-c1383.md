---
title: "Schwerwiegender Fehler C1383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1383"
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Schwerwiegender Fehler C1383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Compileroption \/GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.  
  
 C1383 tritt auf, wenn Sie eine frühere Version der Common Language Runtime mit einem neueren Compiler verwenden und bei der Kompilierung **\/clr** und **\/GL.** verwenden.  
  
 Verwenden Sie entweder nicht **\/GL** mit **\/clr**, oder installieren Sie die im Lieferumfang des Compilers enthaltene Version der Common Language Runtime.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) und [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md).