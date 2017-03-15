---
title: "Compilerfehler C3807 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3807"
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Eine Klasse mit dem ComImport\-Attribut kann nicht von 'Typ2' abgeleitet werden, nur eine Schnittstellenimplementierung ist zulässig  
  
 Ein von <xref:System.Runtime.InteropServices.ComImportAttribute> abgeleiteter Typ kann nur eine Schnittstelle implementieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C3807 generiert.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```