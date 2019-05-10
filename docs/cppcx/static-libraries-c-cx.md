---
title: Statische Bibliotheken (C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 188ba06518bf6cdd154b7d6bd61216ed1e4ffad3
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877245"
---
# <a name="static-libraries-ccx"></a>Statische Bibliotheken (C++/CX)

Eine statische Bibliothek, die in einer app (Universelle Windows Plattform) verwendet wird, kann ISO-Standard C++-Code, einschließlich der STL-Typen, und außerdem Aufrufe für Win32-APIs, die von der Windows-Runtime-app-Plattform nicht ausgeschlossen sind enthalten. Eine statische Bibliothek nutzt Windows-Runtime-Komponenten und kann Windows-Runtime-Komponenten mit bestimmten Einschränkungen erstellen.

## <a name="creating-static-libraries"></a>Erstellen von statischen Bibliotheken


Anweisungen zum Erstellen eines neuen Projekts hängt davon ab, welche Version von Visual Studio, die Sie installiert haben. Stellen Sie sicher, dass Sie die Auswahl für die Version in der Zielauswahl oben links auf die richtige Version festgelegt haben.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Zum Erstellen von UWP statischen Bibliothek in Visual Studio-2019

1. Wählen Sie auf der Menüleiste **Datei** > **neu** > **Projekt** zum Öffnen der **Erstellen eines neuen Projekts** Dialogfeld.

1. Legen Sie am oberen Rand des Dialogfelds, **Sprache** zu **C++** legen **Plattform** zu **Windows**, und legen Sie **Projekttyp** zu **UWP**. 

1. Wählen Sie die gefilterte Liste der Projekttypen, **statische Bibliothek (Universal Windows - C++/CX)** wählen Sie dann **Weiter**. Benennen Sie dem Projekt, und geben Sie den Speicherort des Projekts aus, falls gewünscht, in der nächsten Seite.

1. Wählen Sie die **erstellen** klicken, um das Projekt zu erstellen.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Zum Erstellen von UWP statischen Bibliothek in Visual Studio 2017 oder Visual Studio 2015

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**. Klicken Sie unter **Visual C++** > **Windows Universal** wählen **statische Bibliothek (Universal Windows)**.

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus. In der **Eigenschaften** Dialogfeld auf die **Konfigurationseigenschaften** > **C/C++-** Seite **Nutzen von Windows Runtime-Erweiterung** zu **Ja (/ Zw)**.

::: moniker-end

Wenn Sie eine neue statische Bibliothek kompilieren, wenn Sie eine Win32-API aufrufen, die für UWP-apps ausgeschlossen wird, löst der Compiler Fehler C3861 aus, die "Bezeichner wurde nicht gefunden." Suchen Sie nach einer alternativen Methode, die für die Windows-Runtime unterstützt wird, finden Sie unter [Alternativen zu Windows-APIs in UWP-apps](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Wenn Sie eine UWP-app-Projektmappe ein statisches C++-Bibliotheksprojekt hinzufügen, müssen Sie möglicherweise eigenschafteneinstellungen des Bibliotheksprojekts aktualisieren, damit die UWP-Support-Eigenschaft festgelegt ist, um **Ja**. Der Code aufgebaut und verknüpft, jedoch ein Fehler tritt auf, wenn Sie versuchen, die app für den Microsoft Store zu überprüfen, ohne diese Einstellung. Die statische Bibliothek sollte mit den gleichen Compilereinstellungen wie das Projekt kompiliert werden, in dem sie verwendet werden.

Wenn Sie eine statische Bibliothek nutzen, die öffentliche `ref` -Klassen, öffentliche Schnittstellenklassen oder öffentliche Wertklassen erstellt, gibt der Linker folgende Warnung aus:

> **Warnung LNK4264:** in einer statischen Bibliothek; mit/zw kompilierte Objektdatei wird archiviert Beachten Sie, dass beim Erstellen von Windows-Runtime-Typen nicht empfohlen wird, mit einer statischen Bibliothek verknüpft werden, die Windows-Runtime-Metadaten enthält.

Sie können die Warnung ignorieren, wenn die statische Bibliothek nicht-Windows-Runtime-Komponenten erstellt, die außerhalb der Bibliothek selbst genutzt werden. Wenn die Bibliothek keine Komponenten verwendet, die sie definiert, kann der Linker die Implementierung optimieren, obwohl die öffentlichen Metadaten die Typinformationen enthalten. Das bedeutet, dass öffentliche Komponenten in einer statischen Bibliothek kompiliert, aber nicht zur Laufzeit aktiviert werden. Aus diesem Grund muss jede Komponente des Windows-Runtime, die für die Nutzung vorgesehen ist, von anderen Komponenten oder apps in einer Dynamic Link Library (DLL) implementiert werden.

## <a name="see-also"></a>Siehe auch

[Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)
