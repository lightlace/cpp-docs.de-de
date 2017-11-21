---
title: 'Vorgehensweise: Kompilieren von MFC und ATL-Code mithilfe von Clr-| Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 77e28bcd53d5f497edbbff938f428322a9400fee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>Gewusst wie: Kompilieren von MFC-Code und ATL-Code mit /clr
In diesem Thema wird erläutert, wie vorhandene MFC- und ATL-Programme, die Common Language Runtime kompiliert wird.  
  
### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>Eine MFC-ausführbare Datei oder eine reguläre MFC-DLL kompilieren mit/CLR  
  
1.  Mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** , und klicken Sie dann auf **Eigenschaften**.  
  
2.  In der **Projekteigenschaften** Dialogfeld erweitern Sie den Knoten neben **Konfigurationseigenschaften** , und wählen Sie **allgemeine**. Im rechten Bereich unter **Projektstandards**legen **Common Language Runtime-Unterstützung** auf **Common Language Runtime-Unterstützung (/ Clr)**.  
  
     Stellen Sie sicher, die im gleichen Bereich **Verwendung von MFC** festgelegt ist, um **MFC in einer gemeinsam genutzten DLL verwenden**.  
  
3.  Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Stellen Sie sicher, dass **Debuginformationsformat** festgelegt ist, um **Programmdatenbank/Zi** (nicht **/Zi**).  
  
4.  Wählen Sie die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** auf **Nein (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** auf **Standard**.  
  
5.  Klicken Sie unter **Konfigurationseigenschaften**Option **C/C++-** und dann **Codegenerierung**. Stellen Sie sicher, dass **-Laufzeitbibliothek** wird **Multithreaded-Debug-DLL (/ MDd)** oder **Multithreaded-DLL (/ MD)**.  
  
6.  Fügen Sie in "stdafx.h" die folgende Zeile ein.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>Eine MFC-Erweiterungs-DLL kompilieren mit/CLR  
  
1.  Führen Sie die Schritte in "Zum Kompilieren einer MFC-ausführbare Datei oder eine reguläre MFC-DLL mit" / CLR "" ein.  
  
2.  Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **vorkompilierte Header**. Legen Sie **vorkompilierten Header erstellen/verwenden** auf **vorkompilierte Header nicht verwenden**.  
  
     Als Alternative können in **Projektmappen-Explorer**mit der rechten Maustaste auf "stdafx.cpp", und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **kompilieren Sie mit der Common Language Runtime-Unterstützung** auf **keine Common Language Runtime-Unterstützung**.  
  
3.  Für die Datei, die DllMain und enthält er aufgerufen wird, im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Im rechten Bereich unter **Projektstandards**legen **kompilieren Sie mit der Common Language Runtime-Unterstützung** auf **keine Common Language Runtime-Unterstützung**.  
  
### <a name="to-compile-an-atl-executable-by-using-clr"></a>Eine ausführbare ATL-Datei kompilieren mit/CLR  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
2.  In der **Projekteigenschaften** Dialogfeld erweitern Sie den Knoten neben **Konfigurationseigenschaften** , und wählen Sie **allgemeine**. Im rechten Bereich unter **Projektstandards**legen **Common Language Runtime-Unterstützung** auf **Common Language Runtime-Unterstützung (/ Clr)**.  
  
3.  Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Stellen Sie sicher, dass **Debuginformationsformat** festgelegt ist, um **Programmdatenbank/Zi** (nicht **/Zi**).  
  
4.  Wählen Sie die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** auf **Nein (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** auf **Standard**.  
  
5.  Klicken Sie unter **Konfigurationseigenschaften**Option **C/C++-** und dann **Codegenerierung**. Stellen Sie sicher, dass **-Laufzeitbibliothek** wird **Multithreaded-Debug-DLL (/ MDd)** oder **Multithreaded-DLL (/ MD)**.  
  
6.  Jede MIDL-generierten Dateien (C-Dateien) mit der rechten Maustaste der Datei im **Projektmappen-Explorer** , und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **kompilieren Sie mit der Common Language Runtime-Unterstützung** auf **keine Common Language Runtime-Unterstützung**.  
  
### <a name="to-compile-an-atl-dll-by-using-clr"></a>Um eine ATL-DLL kompilieren mit/CLR  
  
1.  Führen Sie die Schritte im Abschnitt "So kompilieren Sie eine ausführbare ATL mithilfe von/CLR" aus.  
  
2.  Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **vorkompilierte Header**. Legen Sie **vorkompilierten Header erstellen/verwenden** auf **vorkompilierte Header nicht verwenden**.  
  
     Als Alternative können in **Projektmappen-Explorer**mit der rechten Maustaste auf "stdafx.cpp", und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Legen Sie **kompilieren Sie mit der Common Language Runtime-Unterstützung** auf **keine Common Language Runtime-Unterstützung**.  
  
3.  Für die Datei, die DllMain und enthält er aufgerufen wird, im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie dann auf **Eigenschaften**. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie den Knoten neben **C/C++-** , und wählen Sie **allgemeine**. Im rechten Bereich unter **Projektstandards**legen **kompilieren Sie mit der Common Language Runtime-Unterstützung** auf **keine Common Language Runtime-Unterstützung**.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)