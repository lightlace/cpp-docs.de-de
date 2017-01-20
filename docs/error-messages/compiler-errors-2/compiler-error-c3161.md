---
title: "Compilerfehler C3161"
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
  - "C3161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3161"
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle' : Es ist nicht erlaubt, eine Klasse, Struktur, Union oder eine Schnittstelle in einer Schnittstelle zu schachteln. Das Gleiche gilt für das Schachteln einer Schnittstelle in einer Klasse, Struktur oder Union  
  
 [\_\_interface](../../cpp/interface.md) kann nur im globalen Gültigkeitsbereich oder innerhalb eines Namespaces vorkommen.  Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle vorkommen.  
  
## Beispiel  
 Im folgenden Beispiel wird C3161 generiert.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```