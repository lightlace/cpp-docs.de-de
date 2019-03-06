---
title: Festlegen von DLLs für verzögertes Laden
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: b1ca214d8c840d9e993d5a89823b63868a664bec
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424885"
---
# <a name="specifying-dlls-to-delay-load"></a>Festlegen von DLLs für verzögertes Laden

Sie können angeben, die DLLs für verzögertes Laden der [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md):`dllname` -Linkeroption. Wenn Sie nicht beabsichtigen, Ihre eigene Version einer Hilfsfunktion zu verwenden, müssen Sie auch das Programm mit "delayimp.lib" (für Desktopanwendungen) oder "dloadhelper.lib" (für Store-Apps) verknüpfen.

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

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)
