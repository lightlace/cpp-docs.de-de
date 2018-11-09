---
title: _CRTDBG_MAP_ALLOC
ms.date: 11/04/2016
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
ms.openlocfilehash: a6b6ca5d3e6fdc1bac43d082b0d7df5a87830050
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453438"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC

Wenn das **_CRTDBG_MAP_ALLOC**-Flag in der Debugversion einer Anwendung definiert ist, wird die Basisversion der Heapfunktionen den entsprechenden Debugversionen direkt zugeordnet. Das Flag wird in Crtdbg.h verwendet, um die Zuordnung vorzunehmen. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.

Weitere Informationen zum Verwenden der Debugversion im Vergleich zur Basisversion der Heapfunktion finden Sie unter [Using the Debug Version Versus the Base Version (Verwenden der Debugversion im Vergleich zur Basisversion)](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="see-also"></a>Siehe auch

[Steuerungsflags](../c-runtime-library/control-flags.md)