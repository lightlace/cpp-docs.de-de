---
title: "Agile::operator-&gt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator->"
ms.assetid: 570f4b0b-1735-49b3-8a30-4a302ac57074
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator-&gt;-Operator
Ruft ein Handle auf das Objekt ab, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
## Syntax  
  
```cpp  
  
       T^ operator->()   
const throw();  
```  
  
## Rückgabewert  
 Ein Handle auf das Objekt, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
 Dieser Operator gibt tatsächlich einen nicht veröffentlichten internen Typ zurück. Eine einfache Möglichkeit, den Rückgabewert aufzunehmen, besteht darin, ihn einer Variablen zuzuweisen, die mit dem [automatischen](~/cpp/auto-cpp.md) Typableitungsschlüsselwort deklariert wird.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)