---
title: "A.9   Using single Directives"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.9   Using single Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird die `single`\-Direktive \([2.4.3 Abschnitt](../../parallel/openmp/2-4-3-single-construct.md) auf Seite 15\).  Im Beispiel werden nur ein Thread \(normalerweise der erste Thread, der die `single`\-Direktive trifft\), die Statusmeldung.  Der Benutzer ausführen darf keine Annahmen über deren Thread den `single`\-Abschnitt ausführt.  Alle anderen Threads überspringenden `single`\-Abschnitt und überwachen an der Grenze am Ende des `single` Konstrukts auf.  Wenn andere Threads fortsetzen können, ohne auf den Thread zu warten, der den `single`\-Abschnitt ausgeführt wird, kann eine `nowait`\-Klausel auf den `single`\-Direktive angegeben sind.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```