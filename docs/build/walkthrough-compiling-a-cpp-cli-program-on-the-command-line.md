---
title: 'Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile'
ms.date: 09/24/2018
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
ms.openlocfilehash: e8841600fd61aacfe5b942ac4a4305619dff7e90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451024"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile

Sie können Visual C++-Programme erstellen, die auf die Common Language Runtime (CLR) abzielen und .NET Framework verwenden, und diese in der Befehlszeile erstellen. Visual C++ unterstützt die the C++/CLI-Programmiersprache, die über zusätzliche Typen und Operatoren für das .NET-Programmiermodell verfügt. Allgemeine Informationen zu C++ / CLI-Sprache finden Sie unter [.NET-Programmierung mit C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C++/CLI-Programms und kompilieren es dann auf der Befehlszeile. (Sie können Sie Ihr C++/CLI-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein C++/CLI-Codebeispiel aus einem anderen Hilfeartikel verwenden. Dieses Verfahren ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente verfügen.)

> [!NOTE]
> Sie können auch die Visual Studio IDE für die Kompilierung von C++/CLI-Programmen verwenden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines C++-Programms, die die CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).

## <a name="prerequisites"></a>Vorraussetzungen

Sie kennen die Grundlagen der Programmiersprache C++.

## <a name="compiling-a-ccli-program"></a>Kompilieren eines C++/CLI-Programms

Die folgenden Schritte zeigen, wie Sie eine C++/CLI-Konsolenanwendung kompilieren, die .NET Framework-Klassen verwendet.

Zur Aktivierung der Kompilierung für C++ / CLI, verwenden Sie die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption. Der Visual C++-Compiler generiert eine .exe-Datei, die MSIL-Code oder gemischten MSIL- oder nativen Code sowie Links zu den erforderlichen .NET-Framework-Bibliotheken enthält.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>So kompilieren Sie eine C++/CLI-Anwendung in der Befehlszeile

1. Öffnen einer **Developer-Eingabeaufforderung** Fenster. Ausführliche Anweisungen finden Sie unter [, öffnen Sie ein Developer-Eingabeaufforderungsfenster](../build/building-on-the-command-line.md#developer_command_prompt).

   Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren. Führen Sie im Eingabeaufforderungsfenster als Administrator mit der rechten Maustaste das Kontextmenü für die Eingabeaufforderung zu öffnen, und wählen Sie dann **weitere** > **als Administrator ausführen**.

1. Geben Sie an der Eingabeaufforderung `notepad basicclr.cpp` ein.

   Wählen Sie **Ja** Wenn Sie aufgefordert werden, eine Datei zu erstellen.

1. Geben Sie die folgenden Zeilen in Notepad ein:

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. Wählen Sie auf der Menüleiste **Datei** > **speichern**.

   Sie erstellt haben, die .NET Framework-Klasse verwendet Visual C++-Quelldatei (<xref:System.Console>) in der <xref:System> Namespace.

1. Geben Sie an der Eingabeaufforderung `cl /clr basicclr.cpp` ein. Der cl.exe-Compiler kompiliert den Quellcode in eine .obj-Datei, die MSIL enthält, und führt dann den Linker aus, um ein ausführbares Programm namens basicclr.exe zu generieren.

1. Geben Sie zum Ausführen des basicclr.exe-Programms an der Eingabeaufforderung `basicclr` ein.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br/>
[Compileroptionen](../build/reference/compiler-options.md)
