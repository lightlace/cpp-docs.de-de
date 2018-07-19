---
title: Explizites Entladen einer verzögert geladenen DLL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 171acf9689c01649b86c2383d17136c926e25c57
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374173"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Explizites Entladen einer verzögert geladenen DLL
Die [/delay](../../build/reference/delay-delay-load-import-settings.md): Unload (Linkeroption) können Sie eine DLL entladen, die verzögert geladen wurde. Wenn Ihr Code die DLL entladen wird standardmäßig (mithilfe von/delay: Unload und **__FUnloadDelayLoadedDLL2**), die verzögert geladene Importe in die Importadresstabelle (IAT) bleiben. Allerdings bei Verwendung von/delay: unload in der Linker-Befehlszeile wird die Hilfsfunktion unterstützen das explizite Entladen der DLL, die IAT in ihr ursprüngliches Format zurückgesetzt; der Zeiger für das jetzt ungültig werden überschrieben. Die IAT ist ein Feld in der [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) , enthält die Adresse einer Kopie der ursprünglichen IAT (falls vorhanden).  
  
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
 Wichtige Hinweise zum Entladen einer verzögert geladenen DLL:  
  
-   Sie finden die Implementierung der **__FUnloadDelayLoadedDLL2** Funktion in der Datei \VC7\INCLUDE\DELAYHLP. CPP.  
  
-   Die Name-Parameter von der **__FUnloadDelayLoadedDLL2** Funktion muss genau (einschließlich der Fall) wie die Importbibliothek enthält (die Zeichenfolge auch in der Tabelle importieren, in der Abbildung ist). Sie können den Inhalt des mit der Importbibliothek anzeigen [DUMPBIN/DEPENDENTS](../../build/reference/dependents.md). Wenn eine Übereinstimmung der Groß-/Kleinschreibung Zeichenfolge gewünscht ist, können Sie aktualisieren **__FUnloadDelayLoadedDLL2** die CRT-Zeichenfolgenfunktionen oder ein Aufruf der Windows-API verwenden.  
  
 Finden Sie unter [Entladen einer verzögert geladenen DLL](../../build/reference/unloading-a-delay-loaded-dll.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)