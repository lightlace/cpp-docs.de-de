---
title: 'Vorgehensweise: Kompilieren von MFC- und ATL-Code mit / clr'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], interoperability
- ATL [C++], interoperability
- mixed assemblies [C++], MFC code
- mixed assemblies [C++], ATL code
- /clr compiler option [C++], compiling ATL and MFC code
- interoperability [C++], /clr compiler option
- regular MFC DLLs [C++], /clr compiler option
- interop [C++], /clr compiler option
- extension DLLs [C++], /clr compiler option
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
ms.openlocfilehash: 9a24e82787eb0fce8ff668843e73de9f2d05e1ad
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751608"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>Vorgehensweise: Kompilieren von MFC und ATL-Code durch Verwendung von "/ CLR"

In diesem Thema wird erläutert, wie vorhandene MFC- und ATL-Programme, die die Common Language Runtime kompiliert wird.

### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>Eine MFC-ausführbare Datei oder eine reguläre MFC-DLL kompilieren mit/CLR

1. Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und klicken Sie dann auf **Eigenschaften**.

1. In der **Projekteigenschaften** Dialogfeld erweitern Sie den Knoten neben **Konfigurationseigenschaften** , und wählen Sie **allgemeine**. Klicken Sie im rechten Bereich unter **Projektstandards**legen **Common Language Runtime-Unterstützung** zu **Common Language Runtime-Unterstützung (/ Clr)**.

   Stellen Sie sicher, die im gleichen Bereich **Verwendung von MFC** nastaven NA hodnotu **MFC in einer gemeinsam genutzten DLL verwenden**.

1. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Stellen Sie sicher, dass **Debuginformationsformat** nastaven NA hodnotu **Programmdatenbank "/ Zi"** (nicht **"/ Zi"**).

1. Wählen Sie die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** zu **No (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** zu **Standard**.

1. Klicken Sie unter **Konfigurationseigenschaften**Option **C/C++-** und dann **Codegenerierung**. Stellen Sie sicher, dass **Laufzeitbibliothek** wird **Multithreaded-Debug-DLL (/ MDd)** oder **Multithreaded-DLL (/ MD)**.

1. Fügen Sie in "stdafx.h" die folgende Zeile hinzu.

    ```
    #using <System.Windows.Forms.dll>
    ```

### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>Eine MFC-Erweiterungs-DLL kompilieren mit/CLR

1. Führen Sie die Schritte in "Zum Kompilieren einer MFC-ausführbare Datei oder eine reguläre MFC-DLL mithilfe von" / CLR "verwenden" aus.

1. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **vorkompilierte Header**. Legen Sie **vorkompilierten Header erstellen/verwenden** zu **vorkompilierte Header nicht verwenden**.

   Als Alternative in **Projektmappen-Explorer**mit der rechten Maustaste auf "stdafx.cpp", und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **mit Unterstützung für die Common Language Runtime kompilieren** zu **keine Common Language Runtime-Unterstützung**.

1. Für die Datei mit DllMain und ruft, in **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Klicken Sie im rechten Bereich unter **Projektstandards**legen **mit Unterstützung für die Common Language Runtime kompilieren** zu **keine Common Language Runtime-Unterstützung**.

### <a name="to-compile-an-atl-executable-by-using-clr"></a>Um eine ausführbare ATL-Datei kompilieren mit/CLR

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.

1. In der **Projekteigenschaften** Dialogfeld erweitern Sie den Knoten neben **Konfigurationseigenschaften** , und wählen Sie **allgemeine**. Klicken Sie im rechten Bereich unter **Projektstandards**legen **Common Language Runtime-Unterstützung** zu **Common Language Runtime-Unterstützung (/ Clr)**.

1. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Stellen Sie sicher, dass **Debuginformationsformat** nastaven NA hodnotu **Programmdatenbank "/ Zi"** (nicht **"/ Zi"**).

1. Wählen Sie die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** zu **No (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** zu **Standard**.

1. Klicken Sie unter **Konfigurationseigenschaften**Option **C/C++-** und dann **Codegenerierung**. Stellen Sie sicher, dass **Laufzeitbibliothek** wird **Multithreaded-Debug-DLL (/ MDd)** oder **Multithreaded-DLL (/ MD)**.

1. Jeder MIDL-generierten-Datei (C#-Dateien), mit der rechten Maustaste der Datei im **Projektmappen-Explorer** , und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **mit Unterstützung für die Common Language Runtime kompilieren** zu **keine Common Language Runtime-Unterstützung**.

### <a name="to-compile-an-atl-dll-by-using-clr"></a>Um ein ATL-DLL kompilieren mit/CLR

1. Führen Sie die Schritte im Abschnitt "So kompilieren Sie eine ausführbare ATL, mithilfe von/CLR" aus.

1. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **vorkompilierte Header**. Legen Sie **vorkompilierten Header erstellen/verwenden** zu **vorkompilierte Header nicht verwenden**.

   Als Alternative in **Projektmappen-Explorer**mit der rechten Maustaste auf "stdafx.cpp", und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **mit Unterstützung für die Common Language Runtime kompilieren** zu **keine Common Language Runtime-Unterstützung**.

1. Für die Datei mit DllMain und ruft, in **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Klicken Sie im rechten Bereich unter **Projektstandards**legen **mit Unterstützung für die Common Language Runtime kompilieren** zu **keine Common Language Runtime-Unterstützung**.

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
