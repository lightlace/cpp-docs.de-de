---
title: .NETMODULE-Dateien als Eingabe für den Linker
ms.date: 11/04/2016
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: fcba363cff567c69ac0fbd0a541953dfe2c8e910
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818101"
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-Dateien als Eingabe für den Linker

Jetzt werden in Link.exe MSIL .obj "und" NETMODULE-Dateien als Eingabe akzeptiert. Die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit die OBJ-oder NETMODULE-Dateien, die an den Linker eingegeben wurden.

NETMODULE-Dateien werden erstellt, indem der MSVC-Compiler mit [/ln (Create MSIL Module)](ln-create-msil-module.md) oder vom Linker mit [/NOASSEMBLY (MSIL-Modul erstellen)](noassembly-create-a-msil-module.md). OBJ-Dateien werden immer in einer Visual C++-Kompilierung erstellt. Verwenden Sie für andere Visual Studio-Compilern dem **/target: Module** -Compileroption.

Sie müssen an den Linker die OBJ-Datei aus der Visual C++-Kompilierung übergeben, die die NETMODULE-Datei erstellt. Übergeben einer NETMODULE-Datei wird nicht mehr unterstützt werden, da die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Informationen dazu, wie den Linker über die Befehlszeile aufrufen, finden Sie unter [Linker Command-Line Syntax](linking.md), [verwenden Sie das MSVC-Toolset, über die Befehlszeile](../building-on-the-command-line.md), und [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Einer NETMODULE-Datei oder DLL-Datei an den Linker übergeben, mit dem MSVC-Compiler kompilierte **"/ CLR"** kann dazu führen, ein Linker-Fehler. Weitere Informationen finden Sie unter [auswählen des Formats von .netmodule-Eingabedateien](choosing-the-format-of-netmodule-input-files.md).

Der Linker akzeptiert systemeigene OBJ-Dateien als auch MSIL-OBJ-Dateien mit kompiliert **"/ CLR"**. Beim Übergeben von gemischten OBJ-Dateien im selben Build wird die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig gleich der niedrigsten Ebene Überprüfbarkeitsstufe der Eingabemodule sein.

Wenn Sie derzeit eine Anwendung, die sich aus zwei oder mehrere Assemblys verfügen, und Sie die Anwendung in einer Assembly enthalten sein soll, müssen Sie die Assemblys neu kompilieren und verknüpfen dann die OBJ-Dateien oder NETMODULE-Dateien, die eine einzelne Assembly erzeugen.

Sie müssen angeben, einen Eintrag mithilfe [/Entry (Symbol für Einstiegspunkt)](entry-entry-point-symbol.md) beim ein ausführbares Image zu erstellen.

Verwenden Sie beim Verknüpfen mit einer MSIL-OBJ- oder NETMODULE-Datei [/LTCG (Link-Time Code Generation)](ltcg-link-time-code-generation.md), andernfalls Wenn der Linker die MSIL-OBJ- oder NETMODULE-Datei findet, er startet die Verknüpfung mit "/ LTCG".

MSIL-OBJ oder NETMODULE-Dateien können auch an cl.exe übergeben werden.

Eingabe MSIL OBJ oder NETMODULE-Dateien können nicht als Ressourcen eingebettet haben. Eine Ressource in eine Ausgabedatei (Modul oder Assembly) eingebettet ist, mit [/ASSEMBLYRESOURCE (verwaltete Ressource einbetten)](assemblyresource-embed-a-managed-resource.md) (Linkeroption) oder mit der **/Resource** -Compileroption in anderen Visual Studio-Compilern.

Beim Ausführen der MSIL-Verknüpfung, und wenn Sie nicht auch angeben [/LTCG (Link-Time Code Generation)](ltcg-link-time-code-generation.md), sehen Sie eine informative Meldung, die meldet, dass die Verknüpfung neu gestartet wird. Diese Meldung kann ignoriert werden, aber zur leistungsverbesserung Linker mit MSIL verknüpfen, geben Sie explizit **"/ LTCG"**.

## <a name="example"></a>Beispiel

In C++-Code der **catch** Codeblock ein entsprechendes **versuchen** für eine Ausnahme nicht aufgerufen werden. Die CLR umschließt jedoch standardmäßig nicht zum System Ausnahmen mit <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Wenn eine Assembly aus Visual C++ und nicht - Visual C++ Module erstellt wird und Sie möchten eine **catch** -block in C++-Code aus der entsprechenden aufgerufen werden **versuchen Sie es** Klausel bei der **versuchen**Block wird eine nicht-System-Ausnahme auslöst, müssen Sie hinzufügen, die `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` -Attribut auf den Quellcode für die nicht mit C++ Module.

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

Durch ändern den booleschen Wert, der die `WrapNonExceptionThrows` -Attribut, ändern Sie die Möglichkeit von der Visual C++-Code, um eine nicht-System-Ausnahme abzufangen.

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
