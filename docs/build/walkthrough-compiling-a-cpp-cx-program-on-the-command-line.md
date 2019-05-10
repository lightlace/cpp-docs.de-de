---
title: 'Exemplarische Vorgehensweise: Kompilieren eines C++ / CX-Programms in der Befehlszeile'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: cbf5a48de3c029e36fc6daabe2b3f0db55dc173c
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877164"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C++ / CX-Programms in der Befehlszeile

> [!NOTE] 
> Für neue UWP-apps und Komponenten, empfehlen wir die Verwendung von [ C++"/ WinRT"](/windows/uwp/cpp-and-winrt-apis/), eine C ++ 17-standardsprachprojektion für Windows-Runtime-APIs. C++ / WinRT finden Sie in das Windows 10 SDK Version 1803 gerechnet. C++ / WinRT ist nur in Headerdateien implementiert wird, und soll Sie mit erstklassigen Zugriff auf die moderne Windows-API bereitstellen.

Microsoft C++ (MSVC)-Compiler unterstützt C++ komponentenerweiterungen (C++/CX), verfügt über zusätzliche Typen und Operatoren für die Windows-Runtime-Programmiermodell bereitstellen. Sie können C++/CX zum Erstellen von apps für universelle Windows-Plattform (UWP) und Windows-Desktop. Weitere Informationen finden Sie unter [eine Einführung in c++ / CX](https://msdn.microsoft.com/magazine/dn166929.aspx) und [Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md).

In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C++/CX-Programms und kompilieren es dann auf der Befehlszeile. (Sie können Sie Ihr C++/CX-Programm verwenden, statt das gezeigte einzugeben oder Sie können ein C++/CX-Codebeispiel aus einem anderen Hilfeartikel verwenden. Dieses Verfahren ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente verfügen.)

> [!NOTE]
> Sie können auch die Visual Studio IDE für die Kompilierung von C++/CX-Programmen verwenden. Da die IDE enthält, Design, Debuggen, Emulation und Unterstützung für die Bereitstellung, die nicht in der Befehlszeile zur Verfügung steht, empfehlen wir die Verwendung der IDE zum Erstellen von apps für universelle Windows-Plattform (UWP). Weitere Informationen finden Sie unter [Erstellen einer UWP-app in C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

## <a name="prerequisites"></a>Vorraussetzungen

Sie kennen die Grundlagen der Programmiersprache C++.

## <a name="compiling-a-ccx-program"></a>Kompilieren eines C++/CX-Programms

Zur Aktivierung der Kompilierung für C++ / CX verwenden, müssen Sie verwenden die [/Zw](reference/zw-windows-runtime-compilation.md) -Compileroption. Der MSVC-Compiler generiert eine .exe-Datei, die auf die Windows-Runtime abzielt und enthält links zu den erforderlichen Bibliotheken.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>So kompilieren Sie eine C++/CX-Anwendung in der Befehlszeile

1. Öffnen einer **Developer-Eingabeaufforderung** Fenster. (Auf der **starten** geöffnete Fenster **Apps**. Öffnen der **Visual Studio-Tools** Ordner unter Ihrer Version von Visual Studio, und wählen Sie dann die **Developer-Eingabeaufforderung** Tastenkombination.) Weitere Informationen dazu, wie Sie ein Developer-Eingabeaufforderungsfenster zu öffnen, finden Sie unter [verwenden Sie das MSVC-Toolset, über die Befehlszeile](building-on-the-command-line.md).

   Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren. Führen Sie im Eingabeaufforderungsfenster als Administrator öffnen Sie das Kontextmenü für **Developer-Eingabeaufforderung** und wählen Sie dann **als Administrator ausführen**.

1. Geben Sie an der Eingabeaufforderung den Befehl **Notepad basiccx.cpp ein**.

   Wählen Sie **Ja** Wenn Sie aufgefordert werden, eine Datei zu erstellen.

1. Geben Sie die folgenden Zeilen in Notepad ein:

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. Wählen Sie auf der Menüleiste **Datei** > **speichern**.

   Sie erstellt haben, haben eine C++ Quelldatei, die die Windows-Runtime verwendet [plattformnamespace](../cppcx/platform-namespace-c-cx.md) Namespace.

1. Geben Sie an der Eingabeaufforderung den Befehl **cl/EHsc/Zw basiccx.cpp/Link / Subsystem: Console**. Der cl.exe-Compiler kompiliert den Quellcode in eine .obj-Datei und führt dann den Linker aus, um ein ausführbares Programm namens basiccx.exe zu generieren. (Die [/EHsc](reference/eh-exception-handling-model.md) Compiler-Option gibt an, die C++-Ausnahmebehandlungsmodell und das [/link](reference/link-pass-options-to-linker.md) -Flag gibt an, eine Konsolenanwendung.)

1. Geben Sie zum Ausführen des basiccx.exe-Programms an der Eingabeaufforderung **basiccx ein**.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>Siehe auch

[Projekte und Buildsysteme](projects-and-build-systems-cpp.md)<br/>
[MSVC-Compileroptionen](reference/compiler-options.md)
