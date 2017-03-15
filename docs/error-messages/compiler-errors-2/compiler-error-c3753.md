---
title: "Compilerfehler C3753 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3753"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3753"
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Compilerfehler C3753
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine generische Eigenschaft ist nicht zulässig  
  
 Generische Parameterlisten können nur in verwalteten Klassen, Strukturen oder Funktionen stehen.  
  
 Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md) und [property](../../windows/property-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3753 generiert.  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```