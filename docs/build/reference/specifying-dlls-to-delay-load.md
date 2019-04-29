---
title: Festlegen von DLLs für verzögertes Laden
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: 2b6737abd76c03186881e83bbd2bf286be6ffe2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318146"
---
# <a name="specifying-dlls-to-delay-load"></a>Festlegen von DLLs für verzögertes Laden

Sie können angeben, die DLLs für verzögertes Laden der [/DELAYLOAD](delayload-delay-load-import.md):`dllname` -Linkeroption. Wenn Sie nicht beabsichtigen, Ihre eigene Version einer Hilfsfunktion zu verwenden, müssen Sie auch das Programm mit "delayimp.lib" (für Desktopanwendungen) oder "dloadhelper.lib" (für Store-Apps) verknüpfen.

Im Folgenden finden Sie ein einfaches Beispiel für das verzögerte Laden einer DLL:

```
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Erstellen Sie die Debugversion des Projekts. Durchlaufen Sie den Code mithilfe des Debuggers schrittweise; Sie werden bemerken, dass "user32.dll" nur geladen wird, wenn Sie `MessageBox` aufrufen.

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](linker-support-for-delay-loaded-dlls.md)
