---
title: "Festlegen von DLLs f&#252;r verz&#246;gertes Laden | Microsoft Docs"
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
  - "/DELAYLOAD (Linkeroption)"
  - "Verzögertes Laden von DLLs"
  - "Verzögertes Laden von DLLs, Angeben"
  - "DELAYLOAD (Linkeroption)"
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Festlegen von DLLs f&#252;r verz&#246;gertes Laden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können angeben, welche DLLs mit der [\/delayload](../../build/reference/delayload-delay-load-import.md):`dllname`\-Linkeroption verzögert geladen werden sollen.  Wenn Sie nicht beabsichtigen, Ihre eigene Version einer Hilfsfunktion zu verwenden, müssen Sie auch das Programm mit "delayimp.lib" \(für Desktopanwendungen\) oder "dloadhelper.lib" \(für Store\-Apps\) verknüpfen.  
  
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
  
 Erstellen Sie die Debugversion des Projekts.  Durchlaufen Sie den Code mithilfe des Debuggers schrittweise; Sie werden bemerken, dass "user32.dll" nur geladen wird, wenn Sie `MessageBox` aufrufen.  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)