---
title: Linkertoolwarnung LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 3d89b27c32b33b917abb7fc140eebf5924142423
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298541"
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