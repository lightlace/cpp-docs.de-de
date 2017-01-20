---
title: "Exportieren von C-Funktionen zur Verwendung in ausf&#252;hrbaren C- oder C++-Dateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__cplusplus-Makro"
  - "Exportieren von DLLs [C++], C-Funktionen in ausführbaren C++-Dateien"
  - "Exportieren von Funktionen [C++], C-Funktionen in ausführbaren C++-Dateien"
  - "Funktionen [C], Ausführbare C- oder C++-Dateien"
  - "Funktionen [C], Exportieren"
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Exportieren von C-Funktionen zur Verwendung in ausf&#252;hrbaren C- oder C++-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine DLL in C geschriebene Funktionen enthält und auf diese Funktionen über ein C\- oder C\+\+\-Sprachmodul zugegriffen werden soll, sollten Sie das **\_\_cplusplus**\-Präprozessormakro verwenden, um zu bestimmen, welche Sprache kompiliert wird. Anschließend sollten Sie diese Funktionen mit C\-Bindung deklarieren, sofern sie von einem C\+\+\-Sprachmodul verwendet werden.  Wenn Sie diese Technik anwenden und Headerdateien für die DLL bereitstellen, können diese Funktionen ohne weitere Änderungen von C\- und C\+\+\-Benutzern verwendet werden.  
  
 Der folgende Code stellt eine Headerdatei dar, die sowohl von C\- als auch von C\+\+\-Clientanwendungen verwendet werden kann:  
  
```  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 Wenn Sie C\-Funktionen mit einer ausführbaren C\+\+\-Datei verknüpfen müssen und die oben beschriebene Methode in den Headerdateien mit den Funktionsdeklarationen nicht verwendet wurde, können Sie wie folgt verhindern, dass die C\-Funktionsnamen vom Compiler ergänzt werden:  
  
```  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Bindungsangaben \(nur auf Englisch verfügbar\)](assetId:///d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)