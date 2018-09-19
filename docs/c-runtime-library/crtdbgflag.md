---
title: _crtDbgFlag | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d9900d42a5bae3c7a613028a7ae4ffe4bdc0333
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044911"
---
# <a name="crtdbgflag"></a>_crtDbgFlag

Das Flag **_crtDbgFlag** besteht aus fünf Bitfeldern, die steuern, wie Speicherbelegungen in der Debugversion des Heaps nachverfolgt, geprüft, gemeldet und gesichert werden. Die Bitfelder des Flags werden mithilfe der Funktion [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) festgelegt. Dieses Flag und seine Bitfelder werden in Crtdbg.h deklariert. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.

Weitere Informationen zur Verwendung dieses Flags in Verbindung mit anderen Debugfunktionen finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>Siehe auch

[Steuerungsflags](../c-runtime-library/control-flags.md)