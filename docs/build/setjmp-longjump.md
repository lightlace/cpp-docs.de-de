---
title: Setjmp-Longjump | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 744b855d1b867507b54973f17e2a4f98b63e2b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
Wenn Sie setjmpex.h oder setjmp.h einfügen, alle Aufrufe von [Setjmp](../c-runtime-library/reference/setjmp.md) oder [Longjmp](../c-runtime-library/reference/longjmp.md) führt zu einer Entladung, ruft Destruktoren und zum Schluss ruft.  Dies unterscheidet sich von X86, einschließlich setjmp.h Ergebnisse finally-Klauseln und Destruktoren nicht aufgerufen wird.  
  
 Ein Aufruf von `setjmp` behält den aktuellen Stack-Pointer, nicht flüchtigen Register und MxCsr-Register.  Aufrufe von `longjmp` zurück zum zuletzt `setjmp` aufrufen, Standort und setzt die Stack-Pointer, nicht flüchtigen Register und MxCsr registriert hat, in den Zustand wie nach der letzten beibehalten `setjmp` aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)