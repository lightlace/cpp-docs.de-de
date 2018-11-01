---
title: Exportieren von C-Funktionen zur Verwendung in ausführbaren C- oder C++-Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: 0b7347ee29e973e1043a153f8284baa47b674a4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631815"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Exportieren von C-Funktionen zur Verwendung in ausführbaren C- oder C++-Dateien

Wenn Sie Funktionen in einer DLL, die in C geschrieben ist, dass Sie ein c- oder C++-Sprachmodul zugreifen möchten, verwenden Sie haben die **__cplusplus** Präprozessor-Makro, um zu bestimmen, welche Sprache wird kompiliert, und deklarieren Sie diese Funktionen mit C-Bindung, wenn von einem C++-Sprache-Modul verwendet wird. Wenn Sie verwenden Sie dieses Verfahren, und geben Sie die Headerdateien für die DLL, können diese Funktionen von C und C++-Benutzern ohne Änderung verwendet werden.

Der folgende Code zeigt eine Headerdatei, die von Clientanwendungen für C- und C++ verwendet werden kann:

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

Wenn Sie C-Funktionen mit einer ausführbaren C++ verknüpfen müssen, und die Headerdateien nicht das obige Verfahren, in der C++-Quelldatei verwendet haben, führen Sie Folgendes ein, um zu verhindern, dass den Compiler ergänzen Sie den Namen der C-Funktionen:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Bestimmen Sie die Exportmethode verwendet werden](../build/determining-which-exporting-method-to-use.md)

- [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Ergänzte Namen](../build/reference/decorated-names.md)

- [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](../build/exporting-from-a-dll.md)