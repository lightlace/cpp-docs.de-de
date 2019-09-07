---
title: DLLs (C++/CX)
ms.date: 02/06/2018
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
ms.openlocfilehash: 4db0ed4f11f03c65c440c7b654653347da1d4536
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740261"
---
# <a name="dlls-ccx"></a>DLLs (C++/CX)

Sie können Visual Studio verwenden, um entweder eine Standard-Win32-DLL oder eine Windows-Runtime Komponenten-DLL zu erstellen, die von universelle Windows-Plattform-Apps (UWP) verwendet werden kann. Eine Standard-dll, die mit einer Version von Visual Studio oder dem Microsoft C++ -Compiler vor Visual Studio 2012 erstellt wurde, wird möglicherweise nicht ordnungsgemäß in einer UWP-App geladen und übergibt den App-Überprüfungs Test nicht im Microsoft Store.

## <a name="windows-runtime-component-dlls"></a>Komponenten-DLLs Windows-Runtime

Wenn Sie in fast allen Fällen eine DLL für die Verwendung in einer UWP-app erstellen möchten, erstellen Sie Sie als Windows-Runtime Komponente, indem Sie die Projektvorlage dieses Namens verwenden. Sie können ein Windows-Runtime-Komponenten Projekt für DLLs erstellen, die öffentliche oder private Windows-Runtime Typen aufweisen. Auf eine Windows-Runtime Komponente kann von apps zugegriffen werden, die in jeder Windows-Runtime kompatiblen Sprache geschrieben sind. Standardmäßig verwenden die Compilereinstellungen für ein Windows-Runtime Komponenten Projekt den **/ZW** -Schalter. Eine WinMD-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD-Datei übereinstimmen.

Weitere Informationen finden Sie unter [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>So verweisen Sie in Ihrem Projekt auf eine Drittanbieter-Windows-Runtime Komponenten Binärdatei

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .

1. Eine Windows-Runtime Komponente besteht aus einer DLL-Datei und einer winmd-Datei, die die Metadaten enthält. In der Regel sind diese Dateien im selben Ordner. Klicken Sie im linken Bereich des Dialogfelds **Verweis hinzufügen** auf die Schaltfläche **Durchsuchen** , und navigieren Sie dann zum Speicherort der DLL und der WINMD-Datei. Weitere Informationen finden Sie unter [Erweiterungs-sdche](/visualstudio/extensibility/creating-a-software-development-kit#extension-sdks).

## <a name="standard-dlls"></a>Standard-DLLs

Sie können eine Standard-dll für C++ Code erstellen, der keine öffentlichen Windows-Runtime Typen verwendet oder erzeugt und ihn aus einer UWP-App nutzt. Verwenden Sie den Projekttyp Dynamic-Link Library (dll), wenn Sie nur eine vorhandene DLL zur Kompilierung in dieser Version von Visual Studio migrieren möchten, den Code jedoch nicht in ein Windows-Runtime Komponenten Projekt konvertieren. Wenn Sie die folgenden Schritte durchführen, wird die DLL neben Ihrer App bereitgestellt und kann im APPX-Paket ausgeführt werden.

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Erstellen einer Standard-DLL in Visual Studio

1. Wählen Sie in der Menüleiste **Datei**, **neu**, **Projekt**aus, und wählen Sie dann die Vorlage **Dynamic Link Library (dll)** aus.

1. Geben Sie einen Namen für das Projekt ein und wählen Sie dann die Schaltfläche **OK** aus.

1. Fügen Sie den Code hinzu. Stellen Sie sicher, dass Sie `__declspec(dllexport)` für Funktionen verwenden, die Sie exportieren möchten, z. B. `__declspec(dllexport) Add(int I, in j);`.

1. Fügen `#include winapifamily.h` Sie hinzu, um diese Header Datei aus dem Windows SDK für UWP-apps einzuschließen und das-Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`festzulegen.

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>So verweisen Sie auf ein Standard-DLL-Projekt aus derselben Projektmappe

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .

1. Wählen Sie im linken Bereich **Projektmappe**aus, und aktivieren Sie dann das entsprechende Kontrollkästchen im rechten Bereich.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.

### <a name="to-reference-a-standard-dll-binary"></a>So verweisen Sie auf eine standardmäßige DLL-Binärdatei

1. Kopieren Sie die DLL-Datei, die LIB-Datei und die Headerdatei. Fügen Sie sie an einem bekannten Speicherort ein, z. B. in den aktuellen Projektordner.

1. Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Fügen Sie die LIB-Datei auf der Seite **Konfigurationseigenschaften**, **Linker**, **Eingabe** als Abhängigkeit hinzu.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>So migrieren Sie eine vorhandene Win32-DLL für UWP-APP-Kompatibilität

1. Erstellen Sie ein Projekt des dll-Typs (Universal Windows), und fügen Sie den vorhandenen Quellcode hinzu.

1. Fügen `#include winapifamily.h` Sie hinzu, um diese Header Datei aus dem Windows SDK für UWP-apps einzuschließen und das-Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`festzulegen.

1. Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.
