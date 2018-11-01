---
title: Setjmp-longjump
ms.date: 11/04/2016
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
ms.openlocfilehash: 765cef3f02bed09bed0278aaeecdcdbd55d86b67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427897"
---
# <a name="setjmplongjump"></a>setjmp/longjump

Wenn Sie die setjmpex.h oder setjmp.h einschließen, alle Aufrufe von [Setjmp](../c-runtime-library/reference/setjmp.md) oder [Longjmp](../c-runtime-library/reference/longjmp.md) führt zu einer Entladung, Destruktoren aufgerufen und ruft schließlich.  Dies unterscheidet sich von X86, einschließlich der setjmp.h-Ergebnisse im finally-Klauseln und Destruktoren nicht aufgerufen wird.

Ein Aufruf von `setjmp` behält den aktuellen Stack-Pointer, nicht flüchtigen Register und MxCsr-Register.  Aufrufe von `longjmp` zurück zum zuletzt `setjmp` aufrufen, Standort und setzt die Stack-Pointer, nicht flüchtigen Register und MxCsr registriert, in den Zustand wie durch die die letzte beibehalten `setjmp` aufrufen.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)