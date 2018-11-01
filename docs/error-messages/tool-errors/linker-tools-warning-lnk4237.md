---
title: Linkertoolwarnung LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 62ce0a0edc7f15bc5a19e4630133976f413da35a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588616"
---
# <a name="linker-tools-warning-lnk4237"></a>Linkertoolwarnung LNK4237

/ Subsystem: native wurde beim Importieren von 'Dll'; angegeben Verwenden Sie Subsystem: Console oder native.

[/ Subsystem: native](../../build/reference/subsystem-specify-subsystem.md) angegeben wurde, beim Erstellen einer Windows (Win32)-Anwendung, die direkt eine oder mehrere der folgenden verwendet:

- kernel32.dll

- Gdi32.dll

- user32.dll

- eines der Msvcrt\* Dlls.

Diese Warnung beheben, indem Sie nicht angeben **/Subsystem: native**.