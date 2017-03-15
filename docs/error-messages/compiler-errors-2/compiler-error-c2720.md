---
title: "Compilerfehler C2720 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2720"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2720"
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2720
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Bezeichner“: Speicherklassenspezifizierer „Spezifizierer“ ist für Member unzulässig.  
  
 Die Speicherklasse kann für Klassenmember außerhalb der Variablendeklaration verwendet werden.  Entfernen Sie den nicht benötigten [Speicherklassenspezifizierer](assetId:///10b3d22d-cb40-450b-994b-08cf9a211b6c) aus der Definition des Members außerhalb der Klassendeklaration, um diesen Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2720 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
  
```