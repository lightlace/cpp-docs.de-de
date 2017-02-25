---
title: "Compilerwarnung (Stufe 3) C4641 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4641"
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 3) C4641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der XML\-Dokumentkommentar enthält einen mehrdeutigen Querverweis  
  
 Der Compiler konnte einen Verweis nicht eindeutig auflösen.  Geben Sie zur Behebung des Problems die nötigen Parameterinformationen an, um den Verweis eindeutig zu machen.  
  
 Weitere Informationen finden Sie unter [XML\-Dokumentation](../../ide/xml-documentation-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4641 generiert.  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```