---
title: "Compilerfehler C2364"
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
  - "C2364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2364"
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Unzulässiger Typ für benutzerdefiniertes Attribut  
  
 Namensargumente für benutzerdefinierte Attribute sind auf Konstanten zur Kompilierungszeit beschränkt,  beispielsweise auf ganzzahlige Typen \(int, char usw.\), System::Type^, and System::Object^.  
  
## Beispiel  
 Im folgenden Beispiel wird C2364 generiert.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```