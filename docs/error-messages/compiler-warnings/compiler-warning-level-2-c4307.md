---
title: "Compilerwarnung (Stufe 2) C4307 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4307"
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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