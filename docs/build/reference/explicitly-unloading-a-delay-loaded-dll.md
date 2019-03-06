---
title: Explizites Entladen einer verzögert geladenen DLL
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: f661694dd791ed8db3cd9f5b72a021c7470d17f3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420452"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Explizites Entladen einer verzögert geladenen DLL

Die [/delay](../../build/reference/delay-delay-load-import-settings.md): Unload (Linkeroption) können Sie eine DLL entladen, die verzögert geladen wurde. Wenn Ihr Code die DLL entladen wird, wird standardmäßig (mit/delay: Unload und **__FUnloadDelayLoadedDLL2**), der verzögert geladenen Importen bleiben in der Importadresstabelle (IAT). Jedoch wenn Sie auf der Befehlszeile des Linkers/Delay: UNLOAD verwenden, wird die Hilfsfunktion unterstützen das explizite Entladen der DLL, die IAT in ihre ursprüngliche Form zurückgesetzt; die nun ungültigen Zeiger werden überschrieben. IAT ist ein Feld in der [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) , die die Adresse einer Kopie des ursprünglichen IAT (falls vorhanden) enthält.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>Kommentare

Wichtige Hinweise für das Entladen einer verzögert geladenen DLL:

- Sie finden die Implementierung der **__FUnloadDelayLoadedDLL2** Funktion in der Datei \VC7\INCLUDE\DELAYHLP. CPP.

- Der Name-Parameter von der **__FUnloadDelayLoadedDLL2** Funktion muss genau (einschließlich der Fall) wie die Importbibliothek enthält (die Zeichenfolge auch in der Tabelle importieren, in der Abbildung ist). Sehen Sie den Inhalt der Importbibliothek mit [DUMPBIN/DEPENDENTS](../../build/reference/dependents.md). Wenn eine Übereinstimmung der Groß-/Kleinschreibung Zeichenfolge gewünscht ist, können Sie aktualisieren **__FUnloadDelayLoadedDLL2** die CRT-Zeichenfolgenfunktionen oder einem Windows-API-Aufruf verwenden.

Finden Sie unter [Entladen einer verzögert geladenen DLL](../../build/reference/unloading-a-delay-loaded-dll.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)
