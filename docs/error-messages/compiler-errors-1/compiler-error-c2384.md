---
title: "Compiler Error C2384"
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
  - "C2384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2384"
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Member“ : \_\_declspec\(thread\) kann nicht auf einen Member einer managed\- oder WinRT\-Klasse angewendet werden.  
  
 Der [Thread](../../cpp/thread.md) `__declspec`\-Modifizierer kann nicht für einen Member einer verwalteten bzw. Windows\-Runtime verwendet werden.  
  
 Statischer lokaler Threadspeicher kann im verwalteten Code nur für statisch geladene DLLs verwendet werden; die DLL muss bei Prozessstart statisch geladen sein.  Windows\-Runtime unterstützt keinen lokalen Threadspeicher.  
  
 Mit der folgenden Zeile wird C2384 generiert und gezeigt, wie dieser Fehler im C\+\+\-\/CLI\-Code behoben werden kann:  
  
```  
// C2384.cpp  
// compile with: /clr /c  
public ref class B {  
public:  
   __declspec( thread ) static int tls_i = 1;   // C2384  
  
   // OK - declare with attribute instead  
   [System::ThreadStaticAttribute]  
   static int tls_j;  
};  
```