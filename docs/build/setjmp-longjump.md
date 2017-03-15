---
title: "setjmp/longjump | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# setjmp/longjump
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie setjmpex.h oder setjmp.h einbinden, führen alle Aufrufe von [setjmp](../c-runtime-library/reference/setjmp.md) oder [longjmp](../c-runtime-library/reference/longjmp.md) zu einer Entladung, durch die Destruktoren und finally\-Aufrufe ausgeführt werden.  Im Gegensatz dazu hat beim x86\-Compiler die Einbindung von stejmp.h zur Folge, das finally\-Klauseln und Destruktoren nicht ausgeführt werden.  
  
 Durch einen Aufruf von `setjmp` werden der aktuelle Stapelzeiger, nicht flüchtige Register und MxCsr\-Register beibehalten.  Aufrufe von `longjmp` werden an die aktuelle `setjmp`\-Aufrufsite zurückgegeben. Des Weiteren werden der Stapelzeiger, nicht flüchtige Register und MxCsr\-Register auf den Zustand zurückgesetzt, der durch den letzten `setjmp`\-Aufruf beibehalten wurde.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)