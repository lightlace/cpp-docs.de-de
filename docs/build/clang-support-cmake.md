---
title: Clang/llvm-Unterstützung in Visual Studio cmake-Projekten
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: a71f9dc98f74247788558d1b7dccf3e117f43072
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416024"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Clang/llvm-Unterstützung in Visual Studio cmake-Projekten

::: moniker range="<=vs-2017"

Clang-Unterstützung ist in Visual Studio 2019 verfügbar.

::: moniker-end

::: moniker range="vs-2019"

Sie können Visual Studio mit clang zum Bearbeiten und Debuggen C++ von cmake-Projekten verwenden, die auf Windows oder Linux abzielen.

**Windows**: Visual Studio 2019 Version 16,1 bietet Unterstützung für das Bearbeiten, erstellen und Debuggen mit clang/llvm in cmake-Projekten, die auf Windows abzielen.

**Linux**: für Linux cmake-Projekte ist keine besondere Visual Studio-Unterstützung erforderlich. Sie können clang mit dem Paket-Manager Ihrer Distribution installieren und die entsprechenden Befehle in der Datei "CMakeLists. txt" hinzufügen.

## <a name="install"></a>Installieren

Für eine optimale IDE-Unterstützung in Visual Studio wird empfohlen, die neuesten clang-Compilertools für Windows zu verwenden. Wenn Sie diese noch nicht kennen, können Sie Sie installieren, indem Sie die Visual Studio-Installer öffnen und den  **C++ clang-Compiler für Windows** unter **Desktop Entwicklung mit C++**  optionalen Komponenten auswählen. Wenn Sie eine benutzerdefinierte clang-Installation verwenden, überprüfen Sie die  **C++ Komponente clang-CL für v142 Build Tools** .

![Installation der clang-Komponente](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Neue Konfiguration erstellen

So fügen Sie einem cmake-Projekt eine neue clang-Konfiguration hinzu:

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf CMakeLists. txt, und wählen Sie **cmake Settings for Project aus**.

1. Klicken Sie unter **Konfigurationen**auf die Schaltfläche **Konfiguration hinzufügen** :

   ![Konfiguration hinzufügen](media/cmake-add-config-icon.png)

1. Wählen Sie die gewünschte clang-Konfiguration (Beachten Sie, dass separate clang-Konfigurationen für Windows und Linux bereitgestellt werden), und klicken Sie dann auf **auswählen**:

   ![Cmake-clang-Konfiguration](media/cmake-clang-configuration.png)

1. Wenn Sie Änderungen an dieser Konfiguration vornehmen möchten, verwenden Sie den Editor für die **cmake-Einstellungen**. Weitere Informationen finden Sie unter [Anpassen von cmake-Buildeinstellungen in Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Ändern einer vorhandenen Konfiguration zur Verwendung von clang

Führen Sie die folgenden Schritte aus, um eine vorhandene Konfiguration für die Verwendung von clang zu ändern:

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf CMakeLists. txt, und wählen Sie **cmake Settings for Project aus**.

1. Wählen Sie unter **Allgemein** die Dropdown **Liste Toolset** aus, und wählen Sie das gewünschte clang-Toolset aus:

   ![Clang-Toolset clang](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Benutzerdefinierte clang-Speicherorte

Standardmäßig sucht Visual Studio an zwei Stellen nach clang:

- Windows Die intern installierte Kopie von clang/llvm, die im Visual Studio-Installer verfügbar ist.
- (Windows und Linux) Die PATH-Umgebungsvariable.

Sie können einen anderen Speicherort angeben, indem Sie die **CMAKE_C_COMPILER** -und **CMAKE_CXX_COMPILER** cmake-Variablen in den **cmake-Einstellungen**festlegen:

![Clang-Toolset clang](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang-Kompatibilitäts Modi

Für Windows-Konfigurationen ruft cmake standardmäßig clang im [clang-cl-](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) Modus auf und verknüpft mit der Microsoft-Implementierung der Standard Bibliothek. **Clang-cl. exe** befindet sich standardmäßig in `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Sie können diese Werte in den **cmake-Einstellungen** unter **cmake-Variablen und Cache**ändern. Klicken Sie auf **Erweiterte Variablen anzeigen**. Scrollen Sie nach **CMAKE_CXX_COMPILER**unten, und klicken Sie dann auf die Schaltfläche **Durchsuchen** , um einen anderen compilerpfad anzugeben.

## <a name="edit-build-and-debug"></a>Bearbeiten, erstellen und Debuggen

Nachdem Sie eine clang-Konfiguration eingerichtet haben, können Sie das Projekt erstellen und Debuggen. Visual Studio erkennt, dass Sie den clang-Compiler verwenden, und stellt IntelliSense, Hervorhebung, Navigation und andere Bearbeitungsfunktionen bereit. Fehler und Warnungen werden in der **Ausgabefenster**angezeigt.

Beim Debuggen können Sie Breakpoints, die Arbeitsspeicher-und Datenvisualisierung und die meisten anderen Debuggingfunktionen verwenden. Einige compilerabhängige Features, wie z. b. Bearbeiten und fortfahren, sind für clang-Konfigurationen nicht verfügbar.

![Clang-Debuggen](media/clang-debug-visualize.png)

::: moniker-end
