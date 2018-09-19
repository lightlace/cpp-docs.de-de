---
title: Linkertoolwarnung LNK4237 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 479bd4ff8a4f48da679c9e17ec100668de84d089
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113707"
---
# <a name="linker-tools-warning-lnk4237"></a>Linkertoolwarnung LNK4237

/ Subsystem: native wurde beim Importieren von 'Dll'; angegeben Verwenden Sie Subsystem: Console oder native.

[/ Subsystem: native](../../build/reference/subsystem-specify-subsystem.md) angegeben wurde, beim Erstellen einer Windows (Win32)-Anwendung, die direkt eine oder mehrere der folgenden verwendet:

- kernel32.dll

- Gdi32.dll

- user32.dll

- eines der Msvcrt\* Dlls.

Diese Warnung beheben, indem Sie nicht angeben **/Subsystem: native**.