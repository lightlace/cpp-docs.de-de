---
title: Linkertoolwarnung LNK4104 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6304f3ea928c89f4756a4594270ebb7914324f85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057261"
---
# <a name="linker-tools-warning-lnk4104"></a>Linkertoolwarnung LNK4104

Export von Symbol 'Symbol' muss PRIVATE sein.

Die `symbol` kann einen der folgenden sein:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

Diese Warnung wird ausgegeben, wenn Sie eine Importbibliothek für eine DLL erstellen und Exportieren eine der oben genannten Funktionen ohne sie in der DEF-Datei als privat festzulegen. Im Allgemeinen werden diese Funktionen für die Verwendung nur durch OLE exportiert. Platzieren sie in der Importbibliothek kann beim aufruft, die sie ein Programm nicht ordnungsgemäß in der Bibliothek verknüpft ungewöhnliche Verhalten führen. Weitere Informationen über die PRIVATE-Schlüsselwort finden Sie unter [EXPORTE](../../build/reference/exports.md).