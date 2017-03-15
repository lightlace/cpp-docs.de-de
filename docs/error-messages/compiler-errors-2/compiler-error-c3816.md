---
title: "Compilerfehler C3816 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3816"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3816"
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3816
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' wurde zuvor mit einem anderen verwalteten oder WinRT\-Modifizierer deklariert oder definiert.  
  
 Für eine Vorwärts\- und eine tatsächliche Deklaration ist es erforderlich, dass in der Deklaration der Attribute keine Konflikte oder Inkonsistenzen vorliegen.  
  
 Im folgenden Beispiel wird C3816 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```