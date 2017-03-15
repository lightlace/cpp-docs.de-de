---
title: "Compilerfehler C3675 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3675"
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Ist reserviert, da 'Eigenschaft' definiert ist  
  
 Wenn Sie eine einfache Eigenschaft deklarieren, generiert der Compiler die get\-Accessormethode und die set\-Accessormethode. Diese Namen sind im Gültigkeitsbereich des Programms vorhanden.  Die vom Compiler generierten Namen werden gebildet, indem get\_ und set\_ dem Eigenschaftennamen vorangestellt wird.  Daher können keine Funktionen mit gleichem Namen wie die vom Compiler generierten Accessoren deklariert werden.  
  
 Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3675 generiert.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```