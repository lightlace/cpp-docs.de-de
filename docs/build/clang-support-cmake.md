---
title: Clang/LLVM-Unterstützung in Visual Studio-CMake-Projekten
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++
ms.openlocfilehash: 6773d9cdb076ef305ba635306f3bc9c6575d2203
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67517105"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Clang/LLVM-Unterstützung in Visual Studio-CMake-Projekten

::: moniker range="<=vs-2017"

Clang-Unterstützung ist in Visual Studio-2019 verfügbar.

::: moniker-end

::: moniker range="vs-2019"

Sie können Visual Studio mit Clang verwenden, bearbeiten und Debuggen C++ CMake-Projekte, die Ziel-Windows oder Linux.

**Windows:** Visual Studio 2019 Version 16.1 enthält Unterstützung für bearbeiten und Debuggen mit Clang/LLVM in CMake-Projekten, die mit Windows. 

**Linux**: Für Linux CMake-Projekten ist keine besondere Unterstützung für Visual Studio erforderlich. Sie können instalovat Clang, die mit Ihrer Distribution des Paket-Manager und die entsprechenden Befehle in der Datei "CMakeLists.txt" hinzufügen.

## <a name="install"></a>Installieren

Es wird empfohlen, für die beste IDE-Unterstützung in Visual Studio verwenden die neuesten Clang Compiler-Tools für Windows. Wenn Sie diese nicht bereits haben, können Sie sie installieren, öffnen Visual Studio-Installer und wählen **Clang-Compiler für Windows** unter **Desktop-Entwicklung mit C++**  optionalen Komponenten.

![Clang-Komponenteninstallation](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Erstellen einer neuen Konfigurations

So fügen eine neue Clang-Konfiguration eines CMake-Projekts hinzu:

1. Mit der rechten Maustaste auf die Datei "cmakelists.txt" im **Projektmappen-Explorer** , und wählen Sie **CMake-Einstellungen für Projekt**.

1. Klicken Sie unter **Konfigurationen**, drücken Sie die **-Konfiguration hinzufügen** Schaltfläche:

   ![Konfiguration hinzufügen](media/cmake-add-config-icon.png)

1. Wählen Sie die gewünschte Clang-Konfiguration (Beachten Sie, dass separate Clang-Konfigurationen für Windows und Linux bereitgestellt werden), drücken Sie dann die **wählen**:

   ![CMake, Clang-Konfiguration](media/cmake-clang-configuration.png)

1. Um Änderungen an dieser Konfiguration vorzunehmen, verwenden die **CMake-Einstellungs-Editor**. Weitere Informationen finden Sie unter [CMake anpassen, Erstellen von Einstellungen in Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Ändern einer vorhandenen Konfigurations zur Verwendung von Clang

Um eine vorhandene Konfiguration zur Verwendung von Clang zu ändern, gehen Sie folgendermaßen vor:

1. Mit der rechten Maustaste auf die Datei "cmakelists.txt" im **Projektmappen-Explorer** , und wählen Sie **CMake-Einstellungen für Projekt**.

1. Klicken Sie unter **allgemeine** wählen Sie die **Toolset** Dropdownliste, und wählen Sie das gewünschte Clang-Toolset:

   ![CMake, Clang-toolset](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Benutzerdefinierte Clang-Speicherorte

Standardmäßig sucht Clang an zwei Orten Visual Studio:

- (Windows) Die intern installierte Kopie von Clang/LLVM, die in Visual Studio-Installer enthalten ist.
- (Windows und Linux) PATH-Umgebungsvariablen.

Sie können einen anderen Speicherort angeben, durch Festlegen der **CMAKE_C_COMPILER** und **CMAKE_CXX_COMPILER** CMake-Variablen in **CMake-Einstellungen**:

![CMake, Clang-toolset](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang-Kompatibilitätsmodus

Für Windows-Konfigurationen, ruft CMake standardmäßig Clang in [Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) -Modus und Links mit der Microsoft-Implementierung der Standard-Bibliothek. In der Standardeinstellung **Clang-cl.exe** befindet sich im `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

 Sie können diese Werte in **CMake-Einstellungen** unter **CMake-Variablen und Cache**. Klicken Sie auf **erweiterte Variablen anzeigen**. Führen Sie einen Bildlauf nach unten zur Option **CMAKE_CXX_COMPILER**, klicken Sie dann auf die **Durchsuchen** Schaltfläche, um einen anderen Compiler-Pfad angeben.

## <a name="edit-build-and-debug"></a>Bearbeiten, erstellen und Debuggen

Nachdem Sie eine Clang-Konfiguration eingerichtet haben, können Sie erstellen und Debuggen des Projekts. Visual Studio erkennt, dass Sie den Clang-Compiler verwenden und IntelliSense bietet, hervorheben, Navigation und weitere Bearbeitungsfunktionen. Fehler und Warnungen werden angezeigt, der **Fenster "Ausgabe"** .

Beim Debuggen, können Sie Haltepunkte, Arbeitsspeicher und Visualisierung von Daten und die meisten anderen Debugfunktionen verwenden. Einige Funktionen vom Compiler abhängig, wie z. B. bearbeiten und Fortfahren sind nicht für die Clang-Konfigurationen verfügbar.

![CMake-Clang Debuggen](media/clang-debug-visualize.png)

::: moniker-end
