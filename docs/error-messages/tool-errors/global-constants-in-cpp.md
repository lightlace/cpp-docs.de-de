---
title: "Globale Konstanten in C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstanten, Global"
  - "Globale Konstanten"
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Globale Konstanten in C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Globale Konstanten in C\+\+ sind anders als in C statisch verknüpft.  Dies unterscheidet sich von C.  Wenn Sie in C\+\+ versuchen, eine globale Konstante in mehreren Dateien zu verwenden, erhalten Sie einen Fehler aufgrund eines unaufgelösten externen Verweises.  Globale Konstanten werden durch den Compiler optimiert, sodass kein Platz für die Variable reserviert ist.  
  
 Eine Möglichkeit zur Behebung des Fehlers besteht darin, die const\-Initialisierungen in eine Headerdatei einzufügen und diesen Header – so als würde es sich um einen Funktionsprototyp handeln – ggf. in die CPP\-Dateien einzulesen.  Alternativ können Sie die Variable als nicht konstante Variable erstellen und einen konstanten Verweis verwenden, wenn sie darauf zugreifen.  
  
 Im folgenden Beispiel wird C2019 generiert:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 und anschließend  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)