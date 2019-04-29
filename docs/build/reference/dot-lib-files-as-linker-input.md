---
title: .LIB-Dateien als Linkereingabe
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
ms.openlocfilehash: 02f719b3101b04ad6b219bf882a50a994061af0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293640"
---
# <a name="lib-files-as-linker-input"></a>.LIB-Dateien als Linkereingabe

LINK akzeptiert COFF-Standardbibliotheken und COFF-Bibliotheken, die in der Regel die Erweiterung jeweils. Lib. Standard-Bibliotheken Objekte enthalten und werden durch die LIB-Tool erstellt. Importbibliotheken enthalten Informationen über die Exporte in andere Programme, und es werden entweder durch LINK erstellt, wenn es sich um ein Programm erstellt, das Exporte enthält, oder durch die LIB-Tool. Weitere Informationen zur Verwendung von LIB standard erstellen oder importieren Sie die Bibliotheken, finden Sie unter [LIB-Referenz](lib-reference.md). Weitere Informationen zur Verwendung von LINK zum Erstellen einer Importbibliothek finden Sie unter den [/DLL](dll-build-a-dll.md) Option.

Eine Bibliothek ist als ein Dateiname als Argument oder eine Standardbibliothek Link angegeben. LINK externe Verweise aufgelöst, indem suchen, zuerst in Bibliotheken, die in der Befehlszeile angegeben, und klicken Sie dann in Bibliotheken angegeben, mit der [DEFAULTLIB](defaultlib-specify-default-library.md) Option, und klicken Sie dann in Bibliotheken mit dem Namen OBJ-Dateien. Wenn ein Pfad mit dem Namen der Typbibliothek angegeben ist, sucht LINK für die Bibliothek in diesem Verzeichnis aus. Wenn kein Pfad angegeben ist, sucht LINK zuerst im Verzeichnis, aus dem ist, und klicken Sie dann in den Verzeichnissen in der LIB-Umgebungsvariablen angegeben.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>LIB-Dateien als Linkereingabe in der Entwicklungsumgebung hinzufügen

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Eingabe** Eigenschaftenseite in der **Linker** Ordner.

1. Ändern der **zusätzliche Abhängigkeiten** Eigenschaft, die LIB-Dateien hinzuzufügen.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Das programmgesteuerte Hinzufügen von LIB-Dateien als Linkereingabe

- Finden Sie unter [AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Erstellen und verwenden Sie eine LIB-Datei. Erstellen Sie zuerst eine LIB-Datei ein:

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

Und kompilieren Sie dieses Beispiel mithilfe der LIB-Datei, die Sie gerade erstellt haben:

```cpp
// lib_link_input_2.cpp
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp
__declspec(dllimport) int Test();
#include <iostream>
int main() {
   std::cout << Test() << std::endl;
}
```

```Output
213
```

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](link-input-files.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
