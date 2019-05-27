---
title: .NETMODULE-Dateien als Eingabe für den Linker
ms.date: 05/16/2019
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: 50a0f0a1ff5f65a7512e8372de2fe5296c866dca
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837424"
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-Dateien als Eingabe für den Linker

„link.exe“ akzeptiert jetzt OBJ- und NETMODULES-Dateien von MSIL als Eingabe. Die vom Linker erzeugte Ausgabedatei ist eine Assembly oder ein NETMODULE ohne Laufzeitabhängigkeiten zu einer der OBJ- oder NETMODULE-Dateien, die als Eingabe für den Linker dienten.

NETMODULE-Dateien werden vom MSVC-Compiler mit [/LN (MSIL-Modul erstellen)](ln-create-msil-module.md) oder vom Linker mit [/NOASSEMBLY (MSIL-Modul erstellen)](noassembly-create-a-msil-module.md) erstellt. OBJ-Dateien werden immer in einer Visual C++-Kompilierung erstellt. Verwenden Sie für andere Visual Studio-Compiler die Compileroption **/target:module**.

Sie müssen dem Linker die OBJ-Datei aus der Visual C++-Kompilierung übergeben, in der das NETMODULE erstellt wurde. Die Übergabe in einem NETMODULE wird nicht mehr unterstützt, da die Compileroptionen **/clr:pure** und **/clr:safe** in Visual Studio 2015 als veraltet definiert wurden und in Visual Studio 2017 und höher nicht mehr unterstützt werden.

Informationen zum Aufrufen des Linkers über die Befehlszeile finden Sie unter [Linker-Befehlszeilensyntax](linking.md), [Verwenden des MSVC-Toolsets über die Befehlszeile](../building-on-the-command-line.md) und [Festlegen von Pfad und Umgebungsvariablen für Befehlszeilenbuilds](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Das Übergeben einer NETMODULE- oder DLL-Datei an den Linker, die mit dem MSVC-Compiler mit **/clr** kompiliert wurde, kann zu einem Linkerfehler führen. Weitere Informationen finden Sie unter [Auswählen des Formats von .netmodule-Eingabedateien](choosing-the-format-of-netmodule-input-files.md).

Der Linker akzeptiert native OBJ-Dateien ebenso wie MSIL-OBJ-Dateien, die mit **/clr** kompiliert wurden. Bei der Übergabe gemischter OBJ-Dateien im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule.

Wenn eine Ihrer Anwendungen aktuell aus zwei oder mehr Assemblys zusammengesetzt ist und Sie wünschen, dass die Anwendung in einer Assembly enthalten ist, müssen Sie die Assemblys erneut Kompilieren und anschließend die OBJ- oder NETMODULE-Dateien linken, um eine einzelne Assembly zu erstellen.

Beim Erstellen eines ausführbaren Images müssen Sie mithilfe von [/ENTRY (Symbol für Einstiegspunkt)](entry-entry-point-symbol.md) einen Einstiegspunkt angeben.

Verwenden Sie beim Linken mit einer MSIL-OBJ- oder -NETMODULE-Datei [/LTCG (Codegenerierung zur Verknüpfungszeit)](ltcg-link-time-code-generation.md), andernfalls startet der Linker den Linkprozess erneut mit /LTCG, wenn er auf die MSIL-OBJ- oder NETMODULE-Datei trifft.

MSIL-OBJ- oder -NETMODULE-Dateien können außerdem an „cl.exe“ übergeben werden.

MSIL-OBJ- oder -NETMODULE-Dateien können keine eingebetteten Ressourcen aufweisen. In anderen Visual Studio-Compilern wird eine Ressource in eine Ausgabedatei (Modul oder Assembly) mit der Linkeroption [/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](assemblyresource-embed-a-managed-resource.md) oder der Compileroption **/resource** eingebettet.

Beim Ausführen eines MSIL-Linkprozesses ohne explizite Angabe von [/LTCG (Codegenerierung zur Verknüpfungszeit)](ltcg-link-time-code-generation.md) wird eine Informationsnachricht angezeigt, dass der Linkvorgang erneut gestartet wird. Diese Nachricht kann ignoriert werden, um die Linkerleistung beim MSIL-Linken zu verbessern, sollten Sie **/LTCG** explizit angeben.

## <a name="example"></a>Beispiel

In C++-Code wird der **catch**-Block einer entsprechenden **try**-Klausel für eine nicht vom System stammende Ausnahme aufgerufen. Allerdings umschließt die CLR nicht vom System stammende Ausnahmen standardmäßig mit <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Wenn eine Assembly aus Visual C++-Modulen und nicht aus Visual C++ stammenden Modulen erstellt wird und Sie möchten, dass ein **catch**-Block in C++-Code von seiner entsprechenden **try**-Klausel aufgerufen wird, wenn der **try**-Block eine nicht vom System stammende Ausnahme auslöst, müssen Sie dem Quellcode für die nicht aus C++ stammenden Module das Attribut `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` hinzufügen.

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

## <a name="example"></a>Beispiel

Durch Ändern des booleschen Werts des `WrapNonExceptionThrows`-Attributs ändern Sie die Fähigkeit des Visual C++-Codes, eine nicht vom System stammende Ausnahme abzufangen.

```cpp
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
