---
title: "Compiler Error C3386"
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
  - "C3386"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3386"
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3386
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Typ“: \_\_declspec\(dllexport\)\/\_\_declspec\(dllimport\) kann nicht auf einen verwalteten oder WinRT\-Typ angewendet werden.  
  
 Die `dllimport`\-und [dllexport](../../cpp/dllexport-dllimport.md)`__declspec`\-Modifizierer sind für einen verwalteten oder WinRT\-Typ nicht zulässig .  
  
 Im folgenden Beispiel wird C3386 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```