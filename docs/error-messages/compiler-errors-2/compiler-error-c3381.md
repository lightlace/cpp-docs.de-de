---
title: "Compilerfehler C3381 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3381"
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Assembly': Assemblyzugriffsspezifizierer sind nur in Code verfügbar, der mit einer \/clr\-Option kompiliert wurde  
  
 Systemeigene Typen können außerhalb der Assembly sichtbar sein, der Assemblyzugriff für systemeigene Typen kann jedoch nur in einer **\/clr**\-Kompilierung festgelegt werden.  
  
 Weitere Informationen finden Sie unter [Typsichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3381 generiert.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```