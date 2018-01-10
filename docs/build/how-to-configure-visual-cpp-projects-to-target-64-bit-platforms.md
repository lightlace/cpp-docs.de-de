---
title: "Vorgehensweise: Konfigurieren von Visual C++-Projekte für 64-Bit-X64 Plattformen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e651d28af3bd8635691d6a54d6c4cca8eb8c160
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-configure-visual-c-projects-to-target-64-bit-x64-platforms"></a>Vorgehensweise: Konfigurieren von Visual C++-Projekte für 64-Bit-X64 Plattformen

Sie können die Projektkonfigurationen in der Visual Studio-IDE verwenden, C++-Anwendungen für 64-Bit-Ziel X64 Plattformen einrichten. Außerdem können Sie Win32-Projekteinstellungen zu einer 64-Bit-Projektkonfiguration migrieren.  
  
### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>So richten Sie C++-Anwendungen für 64-Bit-Zielplattformen ein  
  
1.  Öffnen Sie das C++-Projekt, das Sie konfigurieren möchten.  
  
2.  Öffnen Sie die Eigenschaftenseiten für das betreffende Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
    > [!NOTE]
    >  Stellen sicher, dass bei der **Konfigurationseigenschaften** Knoten oder einer seiner Unterknoten ausgewählt ist die  **\<Projektname > Eigenschaftenseiten** (Dialogfeld), andernfalls der  **Configuration Manager** Schaltfläche nicht verfügbar bleibt.  
  
3.  Wählen Sie die Schaltfläche **Konfigurations-Manager** aus, um das Dialogfeld **Konfigurations-Manager** zu öffnen.  
  
4.  In der **Aktive Projektmappenplattform** Dropdown-Liste der  **\<neu... >** Option zum Öffnen der **neue Projektmappenplattform** (Dialogfeld).  
  
5.  In der **neue Plattform eingeben oder auswählen** Dropdown-Liste, wählen Sie eine 64-Bit-Zielplattform.  
  
    > [!NOTE]
    >  Im Dialogfeld **Neue Projektmappenplattform** können Sie die Option **Einstellungen kopieren von** verwenden, um vorhandene Projekteinstellungen in die neue 64-Bit-Projektkonfiguration zu kopieren.  
  
6.  Klicken Sie auf die Schaltfläche **OK** . Die Plattform, die Sie im vorherigen Schritt ausgewählt haben, wird unter **Aktive Projektmappenplattform** im Dialogfeld **Konfigurations-Manager** angezeigt.  
  
7.  Wählen Sie die **schließen** Schaltfläche der **Configuration Manager** Dialogfeld Feld, und wählen Sie dann die **OK** Schaltfläche der  **\<Projektname > Eigenschaftenseiten** (Dialogfeld).  
  
### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>So kopieren Sie Win32-Projekteinstellungen in eine 64-Bit-Projektkonfiguration  
  
-   Wenn das Dialogfeld **Neue Projektmappenplattform** geöffnet ist, während Sie ein Projekt für eine 64-Bit-Zielplattform einrichten, wählen Sie in der Dropdownliste **Einstellungen kopieren von** den Wert **Win32**aus. Diese Projekteinstellungen werden auf der Projektebene automatisch aktualisiert:  
  
    -   Die Linkeroption [/MACHINE](../build/reference/machine-specify-target-platform.md) wird auf **/MACHINE:X64**festgelegt.  
  
    -   **Ausgabe registrieren** ist deaktiviert. Weitere Informationen finden Sie unter [Linker Property Pages](../ide/linker-property-pages.md).  
  
    -   **Zielumgebung** wird auf **/env x64**festgelegt. Weitere Informationen finden Sie unter [MIDL Property Pages: General](../ide/midl-property-pages-general.md).  
  
    -   **Parameter überprüfen** wird deaktiviert und auf den Standardwert zurückgesetzt. Weitere Informationen finden Sie unter [MIDL Property Pages: Advanced](../ide/midl-property-pages-advanced.md).  
  
    -   Wenn **Debuginformationsformat** in der Win32-Projektkonfiguration auf **/ZI** festgelegt war, wird der Wert in der 64-Bit-Projektkonfiguration auf **/Zi** festgelegt. Weitere Informationen finden Sie unter [/Z7, /Zi, /ZI (Debuginformationsformat)](../build/reference/z7-zi-zi-debug-information-format.md).  
  
    > [!NOTE]
    >  Keine dieser Projekteigenschaften wird geändert, wenn sie auf der Dateiebene überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch  

[.NET Framework-64-Bit-Anwendungen](/dotnet/framework/64-bit-apps)   
[Konfigurieren von Visual C++ für die 64-Bit-X64 Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[Debuggen von 64-Bit-Anwendungen](/visualstudio/debugger/debug-64-bit-applications)