---
title: "Compilerwarnung (Stufe 3) C4073"
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
  - "C4073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4073"
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierungen stehen im Initialisierungsbereich einer Bibliothek  
  
 Der Initialisierungsbereich einer Bibliothek, der durch [\#pragma init\_seg](../../preprocessor/init-seg.md) festgelegt wird, sollte nur von Entwicklern verwendet werden, die Bibliotheken anderer Hersteller entwickeln.  Im folgenden Beispiel wird C4073 generiert:  
  
```  
// C4073.cpp  
// compile with: /W3  
#pragma init_seg(lib)   // C4073  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```