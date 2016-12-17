---
title: "Compilerwarnung (Stufe 3) C4995"
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
  - "C4995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4995"
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': der Name, der als \#pragma markiert war, wurde verworfen  
  
 Der Compiler hat eine Funktion gefunden, die mit dem Pragma [deprecated](../../preprocessor/deprecated-c-cpp.md) gekennzeichnet war.  Die Funktion wird in zukünftigen Versionen u. U. nicht mehr unterstützt.  Sie können diese Warnung mit dem Pragma [warning](../../preprocessor/warning.md) deaktivieren \(nachfolgendes Beispiel\).  
  
## Beispiel  
 Im folgenden Beispiel wird C4995 generiert:  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```