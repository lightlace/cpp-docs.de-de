---
title: "Compilerfehler C2581"
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
  - "C2581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2581"
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Statische Funktion mit 'Operator \=' nicht zulässig  
  
 Der Zuweisungsoperator \(`=`\) wurde unzulässigerweise als `static` deklariert.  Zuweisungsoperatoren können nicht `static` sein.  Weitere Informationen finden Sie unter [Benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2581 generiert.  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```