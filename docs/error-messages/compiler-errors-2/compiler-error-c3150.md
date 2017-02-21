---
title: "Compilerfehler C3150 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3150"
ms.assetid: c1ff28f5-52fe-4fd4-81d0-2e0ad8548631
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Element': 'Attribut' kann nur auf eine Klasse, eine Schnittstelle, ein Array oder einen Zeiger angewendet werden  
  
 [\_\_gc](../../misc/gc.md) kann nur auf eine Klasse, eine Schnittstelle oder ein Array angewendet werden.  
  
 C3150 ist nur mit **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3150 generiert:  
  
```  
// C3150.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc void f()   // C3150; function cannot be managed  
{  
}  
```