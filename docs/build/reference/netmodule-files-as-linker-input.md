---
title: .netmodule Dateien als Eingabe für den Linker
description: Beschreibt, wie gemischt verwendet wird.obj immer.netmodule Dateien als Linker-Eingabe beim Erstellen von .NET-Assemblys.
ms.date: 01/30/2020
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodule files
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
no-loc:
- obj
- netmodule
- clr
- pure
- safe
ms.openlocfilehash: 83eab25624bdb81ba9191e4efe6a774551502ee0
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912817"
---
# <a name="opno-locnetmodule-files-as-linker-input"></a>.netmodule Dateien als Eingabe für den Linker

"Link. exe" akzeptiert MSIL- *`.obj`* und *`.netmodule`* Dateien als Eingabe. Die vom Linker erstellte Ausgabedatei ist eine Assembly oder eine *`.netmodule`* Datei ohne Laufzeitabhängigkeit von einer der *`.obj`* -oder *`.netmodule`* Dateien, die für den Linker eingegeben wurden.

## <a name="remarks"></a>Hinweise

*`.netmodule`* Dateien werden vom MSVC-Compiler mit [/ln (Create MSIL Module)](ln-create-msil-module.md) oder vom Linker mit/noAssembly erstellt [(erstellen Sie ein MSIL-Modul)](noassembly-create-a-msil-module.md). *`.obj`* Dateien werden immer in einer C++ Kompilierung erstellt. Verwenden Sie für andere Visual Studio-Compiler die Compileroption **/target:module**.

Dem Linker muss die *`.obj`* Datei von der C++ Kompilierung, von der die *`.netmodule`* erstellt wurde, übermittelt werden. Das Übergeben eines *`.netmodule`* wird nicht mehr unterstützt, da die Compileroptionen **/clr:pure** und **/clr:safe** in Visual Studio 2015 als veraltet eingestuft und in Visual Studio 2017 und höher nicht unterstützt werden.

Informationen dazu, wie Sie den Linker von der Befehlszeile aufrufen, finden Sie unter [Befehlszeilen Syntax von linker](linking.md), [verwenden Sie das MSVC-Toolset von der Befehlszeile aus](../building-on-the-command-line.md), und legen Sie [die Pfad-und Umgebungsvariablen für Befehlszeilenbuilds fest](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Das übergeben einer *`.netmodule`* oder *`.dll`* Datei an den Linker, der vom MSVC-Compiler mit **/clr** kompiliert wurde, kann zu einem Linker-Fehler führen. Weitere Informationen finden Sie unter [auswählen des Formats dernetmodule-Eingabedateien](choosing-the-format-of-netmodule-input-files.md).

Der Linker nimmt sowohl systemeigene *`.obj`* Dateien als auch MSIL- *`.obj`* Dateien an, die mit **/clr** kompiliert wurden. Sie können gemischte *`.obj`* Dateien im gleichen Build übergeben. Die Standardüberprüfung der Ausgabedatei ist mit der über Prüfbarkeit des niedrigsten Eingabe Moduls identisch.

Sie können eine Anwendung ändern, die aus mindestens zwei Assemblys besteht, die in einer Assembly enthalten sein sollen. Kompilieren Sie die Quellen der Assembly neu, und verknüpfen Sie dann die *`.obj`* Dateien oder *`.netmodule`* Dateien, um eine einzelne Assembly zu erstellen.

Geben Sie einen Einstiegspunkt mit [/Entry (Einstiegspunkt Symbol)](entry-entry-point-symbol.md) an, wenn Sie ein ausführbares Image erstellen.

Verwenden Sie beim Verknüpfen mit einer MSIL- *`.obj`* oder *`.netmodule`* Datei [/LTCG (Link-Time Code Generation)](ltcg-link-time-code-generation.md), andernfalls wird der Link mit **/LTCG**neu gestartet, wenn der Linker die MSIL- *`.obj`* oder *`.netmodule`* trifft. Es wird eine Informations Meldung angezeigt, dass der Link neu gestartet wird. Sie können diese Meldung ignorieren, aber um die Linkerleistung zu verbessern, geben Sie **/LTCG**explizit an.

MSIL- *`.obj`* oder *`.netmodule`* Dateien können auch an cl. exe übermittelt werden.

Eingabe-MSIL- *`.obj`* oder *`.netmodule`* Dateien können keine eingebetteten Ressourcen aufweisen. Betten Sie Ressourcen in ein Ausgabemodul oder eine Assemblydatei ein, indem Sie die Linkeroption [/ASSEMBLYRESOURCE (verwaltete Ressource einbetten)](assemblyresource-embed-a-managed-resource.md) verwenden. Oder verwenden Sie die **/Resource** -Compileroption in anderen Visual Studio-Compilern.

## <a name="examples"></a>Beispiele

Im C++ Code wird der **`catch`** -Block eines entsprechenden **`try`** für eine nicht`System` Ausnahme aufgerufen. Standardmäßig umschließt die CLR jedoch nicht-`System` Ausnahmen mit <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Wenn eine C++ Assembly aus-und nicht--C++ Modulen erstellt wird und Sie möchten, dass ein C++ **`catch`** Block im Code aus der entsprechenden **`try`** -Klausel aufgerufen wird, wenn der **`try`** -Block eine nicht`System` Ausnahme auslöst, müssen Sie dem Quellcode für die nicht--C++ Module das `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]`-Attribut hinzufügen.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

Wenn Sie den `Boolean` Wert des `WrapNonExceptionThrows` Attributs ändern, ändern Sie die Fähigkeit des C++ Codes, eine nicht-`System` Ausnahme abzufangen.

```csharp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>Siehe auch

- [LINK-Eingabedateien](link-input-files.md)
- [MSVC-Linkeroptionen](linker-options.md)
