---
title: 'Exemplarische Vorgehensweise: Kompilieren eines c++ / CLI-Programms in der Befehlszeile | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46e4b8d6341ad659596f7e83ab3cdcb89b18df2d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705305"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile

Sie können Visual C++-Programme erstellen, die auf die Common Language Runtime (CLR) abzielen und .NET Framework verwenden, und diese in der Befehlszeile erstellen. Visual C++ unterstützt die the C++/CLI-Programmiersprache, die über zusätzliche Typen und Operatoren für das .NET-Programmiermodell verfügt. Allgemeine Informationen über die C + c++ / CLI-Sprache finden Sie unter [.NET Framework-Programmierung mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C++/CLI-Programms und kompilieren es dann auf der Befehlszeile. (Sie können Sie Ihr C++/CLI-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein C++/CLI-Codebeispiel aus einem anderen Hilfeartikel verwenden. Diese Technik ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente enthalten.)

> [!NOTE]
> Sie können auch die Visual Studio IDE für die Kompilierung von C++/CLI-Programmen verwenden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines C++-Programms, die die CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie benötigen grundlegende Kenntnisse der Programmiersprache C++.

## <a name="compiling-a-ccli-program"></a>Kompilieren eines C++/CLI-Programms

Die folgenden Schritte zeigen, wie Sie eine C++/CLI-Konsolenanwendung kompilieren, die .NET Framework-Klassen verwendet.

So aktivieren Sie die Kompilierung für c++ / CLI, verwenden Sie die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption). Der Visual C++-Compiler generiert eine .exe-Datei, die MSIL-Code oder gemischten MSIL- oder nativen Code sowie Links zu den erforderlichen .NET-Framework-Bibliotheken enthält.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>So kompilieren Sie eine C++/CLI-Anwendung in der Befehlszeile

1. Öffnen einer **Entwicklereingabeaufforderung** Fenster. Ausführliche Anweisungen finden Sie unter [, öffnen Sie ein Developer-Eingabeaufforderungsfenster](../build/building-on-the-command-line.md#developer_command_prompt).

   Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren. Um das Eingabeaufforderungsfenster als Administrator ausführen, mit der rechten Maustaste das Kontextmenü für die Eingabeaufforderung zu öffnen, und wählen Sie dann **weitere**, **als Administrator ausführen**.

1. Geben Sie an der Eingabeaufforderung **Editor basicclr.cpp**.

   Wählen Sie **Ja** Wenn Sie zum Erstellen einer Datei aufgefordert werden.

1. Geben Sie die folgenden Zeilen in Notepad ein:

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. Wählen Sie in der Menüleiste **Datei**, **speichern**.

   Sie haben nun eine Visual C++-Quelldatei erstellt, die eine .NET-Framework-Klasse (<xref:System.Console>) im Namespace <xref:System> enthält.

1. Geben Sie an der Eingabeaufforderung **cl/CLR basicclr.cpp**. Der cl.exe-Compiler kompiliert den Quellcode in eine .obj-Datei, die MSIL enthält, und führt dann den Linker aus, um ein ausführbares Programm namens basicclr.exe zu generieren.

1. Zum Ausführen des basicclr.exe-Programms an der Eingabeaufforderung eingeben **Basicclr**.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>Siehe auch

- [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)
- [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)
- [Compileroptionen](../build/reference/compiler-options.md)
