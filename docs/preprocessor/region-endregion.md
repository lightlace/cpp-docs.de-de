---
title: "region, endregion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.endregion"
  - "endregion_CPP"
  - "region_CPP"
  - "vc-pragma.region"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "endregion-Pragma"
  - "Pragmas, endregion"
  - "Pragmas, Bereich"
  - "region-Pragma"
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# region, endregion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit **\#pragma region** können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](../Topic/Outlining.md) des Code\-Editors von Visual Studio erweitert oder reduziert werden kann.  
  
## Syntax  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### Parameter  
 `comment`\(optional\)  
 Ein Kommentar, der im Code\-Editor angezeigt wird.  
  
 *name*\(optional\)  
 Der Name der Region.  Dieser Name wird im Code\-Editor angezeigt.  
  
## Hinweise  
 **\#pragma endregion** kennzeichnet das Ende eines **\#pragma region**\-Blocks.  
  
 Ein `#region`\-Block muss mit **\#pragma endregion** beendet werden.  
  
## Beispiel  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)