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
ms.openlocfilehash: 8bcb0f5ea26218b74034eb0a41199a1104ba944d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739781"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC

Wenn das **_CRTDBG_MAP_ALLOC**-Flag in der Debugversion einer Anwendung definiert ist, wird die Basisversion der Heapfunktionen den entsprechenden Debugversionen direkt zugeordnet. Das Flag wird in Crtdbg.h verwendet, um die Zuordnung vorzunehmen. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.

Weitere Informationen zum Verwenden der Debugversion im Vergleich zur Basisversion der Heapfunktion finden Sie unter [Using the Debug Version Versus the Base Version (Verwenden der Debugversion im Vergleich zur Basisversion)](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="see-also"></a>Siehe auch

[Steuerungsflags](../c-runtime-library/control-flags.md)
