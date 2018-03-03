---
title: "Exportieren von C-Funktionen zur Verwendung in C oder C++ ausführbaren | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232cfb3a65dfe3e65eaa2eeef0a4a55e723b7f7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Exportieren von C-Funktionen zur Verwendung in ausführbaren C- oder C++-Dateien  
  
Wenn Sie Funktionen in einer DLL, die in C# geschrieben ist, dass Sie über eine c- oder C++-Sprachmodul zugreifen möchten, verwenden Sie haben die **__cplusplus** Präprozessor-Makro, um zu bestimmen, welche Sprache kompiliert wird, und deklarieren Sie diese Funktionen mit C-Bindung, wenn von einem C++-Sprache-Modul verwendet wird. Wenn Sie diese Technik verwenden, geben Sie die Headerdateien für die DLL können diese Funktionen von C und C++ Benutzern ohne Änderungen verwendet werden.  
  
Der folgende Code zeigt eine Headerdatei, die von C und C++-Clientanwendungen verwendet werden kann:  
  
```h  
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
  
Führen Sie Folgendes ein, um zu verhindern, dass den Compiler die C-Funktionsnamen zu ergänzen, wenn müssen Sie die C-Funktionen mit einer ausführbaren C++ verknüpfen und die Funktion Deklaration Headerdateien haben nicht die oben genannten Verfahren, in der C++-Quelldatei verwendet:  
  
```cpp  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Welche Exportmethode ermitteln](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)