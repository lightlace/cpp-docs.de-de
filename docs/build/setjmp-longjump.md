---
title: Setjmp-Longjump | Microsoft-Dokumentation
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
ms.openlocfilehash: f53160a5deeb3ea0db111fc0aae7429b19b7cc86
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703273"
---
# <a name="setjmplongjump"></a>setjmp/longjump

Wenn Sie die setjmpex.h oder setjmp.h einschließen, alle Aufrufe von [Setjmp](../c-runtime-library/reference/setjmp.md) oder [Longjmp](../c-runtime-library/reference/longjmp.md) führt zu einer Entladung, Destruktoren aufgerufen und ruft schließlich.  Dies unterscheidet sich von X86, einschließlich der setjmp.h-Ergebnisse im finally-Klauseln und Destruktoren nicht aufgerufen wird.

Ein Aufruf von `setjmp` behält den aktuellen Stack-Pointer, nicht flüchtigen Register und MxCsr-Register.  Aufrufe von `longjmp` zurück zum zuletzt `setjmp` aufrufen, Standort und setzt die Stack-Pointer, nicht flüchtigen Register und MxCsr registriert, in den Zustand wie durch die die letzte beibehalten `setjmp` aufrufen.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)