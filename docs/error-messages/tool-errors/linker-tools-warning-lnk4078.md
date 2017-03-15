---
title: "Linkertoolwarnung LNK4078 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4078"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4078"
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolwarnung LNK4078
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurden mehrere 'Abschnittsname'\-Abschnitte mit unterschiedlichen Attributen gefunden.  
  
 LINK hat mindestens zwei Abschnitte gefunden, die einen identischen Namen, aber unterschiedliche Attribute besitzen.  
  
 Diese Warnung kann durch eine Importbibliothek oder Exportdatei verursacht werden, die mit einer früheren Version von LINK oder LIB erstellt wurde.  
  
 Erstellen und verknüpfen Sie die Datei neu.  
  
## Beispiel  
 LNK4078 kann außerdem durch eine wichtige Änderung verursacht werden: Der unter x86 von [init\_seg](../../preprocessor/init-seg.md) benannte Abschnitt konnte zuvor gelesen und überschrieben werden und ist nun schreibgeschützt.  
  
 Im folgenden Beispiel wird LNK4078 generiert.  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```