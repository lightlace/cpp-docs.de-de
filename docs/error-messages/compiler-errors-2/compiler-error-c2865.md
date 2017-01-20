---
title: "Compilerfehler C2865"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2865"
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': ungültiger Vergleich für handle\_or\_pointer  
  
 Verweise auf [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) oder [\_\_gc](../../misc/gc.md)\-Typen können nur auf Gleichheit überprüft werden, um festzustellen, ob sie sich auf dasselbe Objekt \(\=\=\) oder auf andere Objekte \(\!\=\) beziehen.  
  
 Die Reihenfolge dieser Typen kann nicht verglichen werden, da verwaltete Objekte von der .NET\-Laufzeit jederzeit verschoben werden können, was zu einem anderen Testergebnis führen könnte.