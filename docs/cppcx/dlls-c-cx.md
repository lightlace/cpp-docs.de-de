---
title: DLLs (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 02/06/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39c334c659980dccdca670ab91501f0e30c4e6d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dlls-ccx"></a>DLLs (C++/CX)

Sie können Visual Studio verwenden, erstellen Sie eine standardmäßige Win32-DLL oder eine Windows-Runtime-Komponenten-DLL, die von den apps der universellen Windows-Plattform (UWP) genutzt werden kann. Eine standard-DLL, die mit einer Version von Visual Studio oder Visual C++-Compiler, die älter als Visual Studio 2012 in einer uwp-app möglicherweise nicht ordnungsgemäß geladen und die app-Überprüfungstest kann nicht in Microsoft Store übergeben erstellt wurde.

## <a name="windows-runtime-component-dlls"></a>Windows-Runtime-Komponenten-DLLs

In fast allen Fällen Wenn erstellt werden soll eine DLL für in einer uwp-app verwenden, erstellen Sie ihn als eine Windows-Runtime-Komponente mithilfe der Projektvorlage dieses Namens. Sie können ein Windows-Runtime-Komponentenprojekt für DLLs erstellen, die öffentliche oder private Windows-Runtime-Typen aufweisen. Eine Windows-Runtime-Komponente kann von apps zugegriffen werden, die in einer beliebigen Windows-Runtime-kompatiblen Sprache geschrieben werden. Standardmäßig Projekt die compilereinstellungen für ein Windows-Runtime-Komponente verwendet die **/Zw** wechseln. Eine WinMD-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD-Datei übereinstimmen.

Weitere Informationen finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Um einen Drittanbieter-Windows-Runtime-Komponente binäre in Ihrem Projekt zu verweisen

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .

1. Eine Windows-Runtime-Komponente besteht aus einer DLL- und einer winmd-Datei, die die Metadaten enthält. In der Regel sind diese Dateien im selben Ordner. Klicken Sie im linken Bereich des Dialogfelds **Verweis hinzufügen** auf die Schaltfläche **Durchsuchen** , und navigieren Sie dann zum Speicherort der DLL und der WINMD-Datei. Weitere Informationen finden Sie unter [Erweiterungs-SDKs](/visualstudio/extensibility/creating-a-software-development-kit#ExtensionSDKs).

## <a name="standard-dlls"></a>Standard-DLLs

Sie können eine standard-DLL für C++-Code erstellen, die nicht verarbeiten oder öffentliche Windows-Runtime-Typen zu erzeugen und ihn in einer uwp-app nutzen. Verwenden Sie den Projekttyp Dynamic Link Library (DLL), wenn Sie nur um in dieser Version von Visual Studio kompiliert, aber nicht den Code in ein Windows-Runtime-Komponentenprojekt konvertieren eine vorhandene DLL migrieren möchten. Wenn Sie die folgenden Schritte durchführen, wird die DLL neben Ihrer App bereitgestellt und kann im APPX-Paket ausgeführt werden.

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Erstellen einer Standard-DLL in Visual Studio

1. Wählen Sie in der Menüleiste **Datei**, **neu**, **Projekt**, und wählen Sie dann die **Dynamic Link Library (DLL)** Vorlage.

1. Geben Sie einen Namen für das Projekt ein und wählen Sie dann die Schaltfläche **OK** aus.

1. Fügen Sie den Code hinzu. Stellen Sie sicher, dass Sie `__declspec(dllexport)` für Funktionen verwenden, die Sie exportieren möchten, z. B. `__declspec(dllexport) Add(int I, in j);`.

1. Hinzufügen `#include winapifamily.h` , fügen Sie diese Headerdatei aus dem Windows SDK für uwp-apps, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>So verweisen Sie auf ein Standard-DLL-Projekt aus derselben Projektmappe

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .

1. Wählen Sie im linken Bereich **Projektmappe**aus, und aktivieren Sie dann das entsprechende Kontrollkästchen im rechten Bereich.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.

### <a name="to-reference-a-standard-dll-binary"></a>So verweisen Sie auf eine standardmäßige DLL-Binärdatei

1. Kopieren Sie die DLL-Datei, die LIB-Datei und die Headerdatei. Fügen Sie sie an einem bekannten Speicherort ein, z. B. in den aktuellen Projektordner.

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Fügen Sie die LIB-Datei auf der Seite **Konfigurationseigenschaften**, **Linker**, **Eingabe** als Abhängigkeit hinzu.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>Migrieren Sie eine vorhandene Win32-DLL für uwp-app-Kompatibilität

1. Erstellen Sie ein Projekt des Typs DLL (Uwp), und fügen Sie den vorhandenen Quellcode hinzu.

1. Hinzufügen `#include winapifamily.h` , fügen Sie diese Headerdatei aus dem Windows SDK für uwp-apps, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.
