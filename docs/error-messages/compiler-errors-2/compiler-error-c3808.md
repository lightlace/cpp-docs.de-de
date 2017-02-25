---
title: "Compilerfehler C3808 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3808"
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Eine Klasse mit dem ComImport\-Attribut kann keinen Member 'Member' definieren. Es sind nur abstrakte oder dllimport\-Funktionen zulässig  
  
 Ein von <xref:System.Runtime.InteropServices.ComImportAttribute> abgeleiteter Typ kann keinen `member` definieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C3808 generiert.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```