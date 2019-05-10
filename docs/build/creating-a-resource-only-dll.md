---
title: Erstellen einer DLL als reine Ressource
ms.date: 11/04/2016
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
ms.openlocfilehash: 0d729be60ebec7a37d07fed1d14c4fd5330c7242
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220835"
---
# <a name="creating-a-resource-only-dll"></a>Erstellen einer DLL als reine Ressource

Eine reine Ressourcen-DLL ist eine DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder. Die Verwendung einer reinen Ressourcen-DLL bietet eine gute Möglichkeit, dieselben Ressourcen von mehreren Programmen gemeinsam nutzen zu lassen. Es ist auch eine gute Möglichkeit, eine Anwendung mit mehreren Sprachen lokalisierte Ressourcen bereitstellen (siehe [lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs](localized-resources-in-mfc-applications-satellite-dlls.md)).

Um eine reine Ressourcen-DLL zu erstellen, erstellen Sie ein neues Win32-DLL-Projekt (MFC-fremd) und fügen dem Projekt die Ressourcen hinzu.

- Wählen Sie Win32-Projekt in der **neues Projekt** Dialogfeld ein, und geben Sie im Win32-Projekt-Assistenten einen DLL-Projekttyp.

- Erstellen Sie für die DLL ein neues Ressourcenskript, das die Ressourcen (z. B. eine Zeichenfolge oder ein Menü) enthält, und speichern Sie es als RC-Datei.

- Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**, und klicken Sie dann die neuen RC-Datei in das Projekt einfügen.

- Geben Sie die [/NOENTRY](reference/noentry-no-entry-point.md) -Linkeroption. / NOENTRY verhindert, dass den Linker einen Verweis auf `_main` in die DLL; diese Option muss eine reine Ressourcen-DLL zu erstellen.

- Erstellen Sie die DLL.

Die Anwendung, die reine Ressourcen-DLL verwendet, sollten Aufrufen [LoadLibrary](loadlibrary-and-afxloadlibrary.md) explizit auf die DLL verknüpfen. Um die Ressourcen zuzugreifen, rufen Sie die generischen Funktionen `FindResource` und `LoadResource`, die für jede Art von Ressource zu arbeiten, oder rufen Sie eine der folgenden ressourcenspezifischen Funktionen:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Die Anwendung sollte Aufrufen `FreeLibrary` nach Abschluss die Ressourcen verwenden.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
