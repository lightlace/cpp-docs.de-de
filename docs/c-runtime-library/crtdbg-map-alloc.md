---
title: _CRTDBG_MAP_ALLOC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c48095acceefa4bb4852dab18d35284492e7ba0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069402"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC

Wenn das **_CRTDBG_MAP_ALLOC**-Flag in der Debugversion einer Anwendung definiert ist, wird die Basisversion der Heapfunktionen den entsprechenden Debugversionen direkt zugeordnet. Das Flag wird in Crtdbg.h verwendet, um die Zuordnung vorzunehmen. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.

Weitere Informationen zum Verwenden der Debugversion im Vergleich zur Basisversion der Heapfunktion finden Sie unter [Using the Debug Version Versus the Base Version (Verwenden der Debugversion im Vergleich zur Basisversion)](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="see-also"></a>Siehe auch

[Steuerungsflags](../c-runtime-library/control-flags.md)