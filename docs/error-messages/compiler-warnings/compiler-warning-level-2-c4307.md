---
title: "Compilerwarnung (Stufe 2) C4307"
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
  - "C4307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4307"
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Überlauf einer ganzzahligen Konstanten  
  
 Der Operator wird in einem Ausdruck verwendet, der eine Ganzzahlkonstante ergibt, durch die der zugeordnete Speicherplatz überschritten wird.  Möglicherweise müssen Sie einen größeren Typ für die Konstante verwenden.  Beispielsweise enthält ein **signed int** einen kleineren Wert als ein `unsigned int`, da **signed int** eines seiner Bits zur Darstellung des Symbols verwendet.  
  
 Im folgenden Beispiel wird C4307 generiert:  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```