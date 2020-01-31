---
title: Erstellen einer DLL als reine Ressource
description: Erstellen einer reinen Ressourcen-DLL in Visual Studio
ms.date: 01/27/2020
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
no-loc:
- noentry
ms.openlocfilehash: ef79de77e35cbef6acd4af1cec82a4edc1b7d105
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821342"
---
# <a name="creating-a-resource-only-dll"></a>Erstellen einer DLL als reine Ressource

Eine reine Ressourcen-DLL ist eine DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder. Die Verwendung einer reinen Ressourcen-DLL bietet eine gute Möglichkeit, dieselben Ressourcen von mehreren Programmen gemeinsam nutzen zu lassen. Es ist auch eine gute Möglichkeit, eine Anwendung mit Ressourcen bereitzustellen, die für mehrere Sprachen lokalisiert sind. Weitere Informationen finden Sie unter [lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs](localized-resources-in-mfc-applications-satellite-dlls.md).

## <a name="create-a-resource-only-dll"></a>Erstellen einer reinen Ressourcen-DLL

Um eine reine Ressourcen-DLL zu erstellen, erstellen Sie ein neues Windows-DLL-Projekt (nicht-MFC), und fügen Sie dem Projekt Ihre Ressourcen hinzu:

::: moniker range="vs-2015"

1. Wählen Sie im Dialogfeld **Neues Projekt** die Option **Win32-Projekt** aus. Geben Sie die Projekt-und Projektmappennamen ein, und wählen Sie **OK**

1. Wählen Sie im **Win32-Anwendungs-Assistenten**die Option **Anwendungseinstellungen**aus. Wählen Sie den **Anwendungstyp** **dll**aus. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **Fertig** stellen aus, um das Projekt zu erstellen.

1. Erstellen Sie ein neues Ressourcen Skript, das die Ressourcen für die dll enthält (z. b. eine Zeichenfolge oder ein Menü). Speichern Sie die `.rc` Datei.

1. Wählen Sie im Menü **Projekt** die Option **Vorhandenes Element hinzufügen**aus, und fügen Sie dann die neue `.rc` Datei in das Projekt ein.

1. Geben Sie die [/NOENTRY](reference/noentry-no-entry-point.md) -Linkeroption an. `/NOENTRY` verhindert, dass der Linker einen Verweis auf `_main` in die DLL verknüpft. Diese Option ist erforderlich, um eine reine Ressourcen-DLL zu erstellen.

1. Erstellen Sie die DLL.

::: moniker-end
::: moniker range=">=vs-2017"

1. Wählen Sie im Dialogfeld **Neues Projekt** die Option **Windows-Desktop-Assistent** und **dann weiter**aus. Geben Sie auf der Seite **Neues Projekt konfigurieren** die Projekt-und Projektmappennamen ein, und klicken Sie auf **Erstellen**.

1. Wählen Sie im Dialogfeld **Windows-Desktop Projekt** einen **Anwendungstyp** von **Dynamic Link Library**aus. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** aus, um das Projekt zu erstellen.

1. Erstellen Sie ein neues Ressourcen Skript, das die Ressourcen für die dll enthält (z. b. eine Zeichenfolge oder ein Menü). Speichern Sie die `.rc` Datei.

1. Wählen Sie im Menü **Projekt** die Option **Vorhandenes Element hinzufügen**aus, und fügen Sie dann die neue `.rc` Datei in das Projekt ein.

1. Geben Sie die [/NOENTRY](reference/noentry-no-entry-point.md) -Linkeroption an. `/NOENTRY` verhindert, dass der Linker einen Verweis auf `_main` in die DLL verknüpft. Diese Option ist erforderlich, um eine reine Ressourcen-DLL zu erstellen.

1. Erstellen Sie die DLL.

::: moniker-end

## <a name="use-a-resource-only-dll"></a>Verwenden einer reinen Ressourcen-DLL

Die Anwendung, die die reine Ressourcen-DLL verwendet, sollte [LoadLibraryEx](loadlibrary-and-afxloadlibrary.md) oder eine verwandte Funktion aufrufen, um explizit mit der dll zu verknüpfen. Um auf die Ressourcen zuzugreifen, nennen Sie die generischen Funktionen `FindResource` und `LoadResource`, die für alle Arten von Ressourcen funktionieren. Oder Sie können eine der folgenden Ressourcen spezifischen Funktionen aufzurufen:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Die Anwendung sollte `FreeLibrary` abrufen, wenn Sie mit der Verwendung der Ressourcen fertig ist.

## <a name="see-also"></a>Siehe auch

[Working with Resource Files (Arbeiten mit Ressourcendateien)](../windows/working-with-resource-files.md)\
[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
