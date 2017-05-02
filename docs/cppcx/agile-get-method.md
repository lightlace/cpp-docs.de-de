---
title: "Agile::Get-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Get"
ms.assetid: d6295e21-ddbe-4302-9158-3498da4d9669
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Get-Methode
Gibt den Handle auf das Objekt zurück, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
## Syntax  
  
```cpp  
  
          T^ Get() const  
;  
```  
  
## Rückgabewert  
 Ein Handle auf das Objekt, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
 Der Typ des Rückgabewerts ist eigentlich ein nicht genannter interner Typ. Eine einfache Möglichkeit, den Rückgabewert aufzunehmen, besteht darin, in einer Variablen zuzuweisen, die mit dem [automatischen](~/cpp/auto-cpp.md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myAgileTvariable->Get();`.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)