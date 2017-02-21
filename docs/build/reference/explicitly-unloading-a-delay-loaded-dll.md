---
title: "Explizites Entladen einer verz&#246;gert geladenen DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY:UNLOAD (Linkeroption)"
  - "__FUnloadDelayLoadedDLL2"
  - "DELAY:UNLOAD (Linkeroption)"
  - "Verzögertes Laden von DLLs, Entladen"
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Explizites Entladen einer verz&#246;gert geladenen DLL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit der Linkeroption [\/delay](../../build/reference/delay-delay-load-import-settings.md):unload können Sie eine verzögert geladene DLL entladen.  Standardmäßig verbleiben die verzögert geladenen Importe in der Importadressentabelle \(IAT\), wenn die DLL \(mit **\/delay:unload** und \_\_FUnloadDelayLoadedDLL2\) durch den Code entladen wird.  Wenn jedoch **\/delay:unload** in der Linkerbefehlszeile verwendet wird, wird das explizite Entladen der DLL von der Hilfsfunktion unterstützt. Hierbei wird die IAT in ihren ursprünglichen Zustand zurückgesetzt, und die nun ungültigen Zeiger werden überschrieben.  Bei der IAT handelt es sich um ein Feld in [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md), das die Adresse einer Kopie der ursprünglichen IAT enthält \(falls vorhanden\).  
  
## Beispiel  
  
### Code  
  
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
  
### Kommentare  
 Wichtige Hinweise zum Entladen einer verzögert geladenen DLL:  
  
-   Die Implementierung der **\_\_FUnloadDelayLoadedDLL2**\-Funktion finden Sie in der Datei **\\VC7\\INCLUDE\\DELAYHLP.CPP**.  
  
-   Der Namensparameter der **\_\_FUnloadDelayLoadedDLL2**\-Funktion muss \(einschließlich der Groß\-\/Kleinschreibung\) exakt mit dem Inhalt der Importbibliothek, also der Zeichenfolge in der Importtabelle des Abbilds, übereinstimmen.  Die Inhalte von Importbibliotheken können mit [DUMPBIN \/DEPENDENTS](../../build/reference/dependents.md) angezeigt werden.  Wenn eine Zeichenfolgenübereinstimmung ohne Beachtung von Groß\-\/Kleinschreibung erwünscht ist, können Sie **\_\_FUnloadDelayLoadedDLL2** aktualisieren, um eine der CRT\-Zeichenfolgenfunktionen oder einen Windows\-API\-Aufruf zu verwenden.  
  
 Weitere Informationen finden Sie unter [Entladen einer verzögert geladenen DLL](../../build/reference/unloading-a-delay-loaded-dll.md).  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)