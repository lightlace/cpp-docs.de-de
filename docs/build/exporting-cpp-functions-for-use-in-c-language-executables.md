---
title: "Exportieren von C++-Funktionen zur Verwendung in ausf&#252;hrbaren C-Dateien"
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
  - "Exportieren von DLLs [C++], C++-Funktionen in ausführbaren C-Dateien"
  - "Exportieren von Funktionen [C++], C++-Funktionen in ausführbaren C-Dateien"
  - "Funktionen [C++], C++-Funktionen in ausführbaren C-Dateien"
  - "Funktionen [C++], Exportieren"
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Exportieren von C++-Funktionen zur Verwendung in ausf&#252;hrbaren C-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Falls eine DLL in C\+\+ geschriebene Funktionen enthält und auf diese Funktionen über ein C\-Sprachmodul zugegriffen werden soll, sollten Sie diese Funktionen mit C\-Bindung anstatt mit C\+\+\-Bindung deklarieren.  Sofern nicht anders angegeben, verwendet der C\+\+\-Compiler die typsichere Namensgebung \(auch Namensergänzung genannt\) sowie die Aufrufkonventionen von C\+\+, wodurch ein von C durchgeführter Aufruf sich schwierig gestalten kann.  
  
 Um die C\-Bindung anzugeben, verwenden Sie **extern "C"** für die Funktionsdeklarationen.  Beispiel:  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Bindungsangaben \(nur auf Englisch verfügbar\)](assetId:///d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)