---
title: "Compilerwarnung (Stufe 1) C4965 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4965"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4965"
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Compilerwarnung (Stufe 1) C4965
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implizites Feld von integer 0; nullptr oder explizite Typumwandlung verwenden  
  
 Visual C\+\+ verfügt über implizites Boxing von Werttypen.  Eine Anweisung, die unter Managed Extensions for C\+\+ eine NULL\-Zuweisung ergibt, wird nun zu einer Zuweisung an einen geschachtelten int\-Wert.  
  
 Weitere Informationen finden Sie unter [Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4965 generiert.  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```