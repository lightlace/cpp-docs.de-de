---
title: Setjmp-Longjump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55cf6a2503367777464f09f92e3e3614c3d9f11b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379834"
---
# <a name="setjmplongjump"></a>setjmp/longjump
Wenn Sie setjmpex.h oder setjmp.h einfügen, alle Aufrufe von [Setjmp](../c-runtime-library/reference/setjmp.md) oder [Longjmp](../c-runtime-library/reference/longjmp.md) führt zu einer Entladung, ruft Destruktoren und zum Schluss ruft.  Dies unterscheidet sich von X86, einschließlich setjmp.h Ergebnisse finally-Klauseln und Destruktoren nicht aufgerufen wird.  
  
 Ein Aufruf von `setjmp` behält den aktuellen Stack-Pointer, nicht flüchtigen Register und MxCsr-Register.  Aufrufe von `longjmp` zurück zum zuletzt `setjmp` aufrufen, Standort und setzt die Stack-Pointer, nicht flüchtigen Register und MxCsr registriert hat, in den Zustand wie nach der letzten beibehalten `setjmp` aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)