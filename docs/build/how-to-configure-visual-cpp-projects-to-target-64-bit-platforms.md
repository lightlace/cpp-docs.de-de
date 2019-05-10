---
title: 'Vorgehensweise: Konfigurieren von Visual Studio C++ Projekte auf Ziel-64-Bit, X64 Plattformen'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: a063c2f333a755ab86a4f91c9d14d0c65a6d1414
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446398"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>Vorgehensweise: Konfigurieren von Visual Studio C++ Projekte auf Ziel-64-Bit, X64 Plattformen

Sie können die Projektkonfigurationen in Visual Studio-IDE verwenden, C++-Anwendungen für 64-Bit-Ziel X64 Plattformen einrichten. Außerdem können Sie Win32-Projekteinstellungen zu einer 64-Bit-Projektkonfiguration migrieren.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>So richten Sie C++-Anwendungen für 64-Bit-Zielplattformen ein

1. Öffnen Sie das C++-Projekt, das Sie konfigurieren möchten.

1. Öffnen Sie die Eigenschaftenseiten für das betreffende Projekt. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](working-with-project-properties.md).

   > [!NOTE]
   > Für .NET-Projekte, stellen sicher, dass die **Konfigurationseigenschaften** Knotens oder einer seiner Unterknoten ausgewählt ist der  **\<Projectname > Property Pages** Dialogfeld ist, andernfalls die  **Konfigurations-Manager** Schaltfläche ist weiterhin nicht verfügbar.

1. Wählen Sie die Schaltfläche **Konfigurations-Manager** aus, um das Dialogfeld **Konfigurations-Manager** zu öffnen.

1. In der **Aktive Projektmappenplattform** Dropdown-Liste die  **\<neu... >** Option zum Öffnen der **neue Projektmappenplattform** Dialogfeld.

1. In der **eingeben oder Auswählen der neuen Plattform** Dropdown-Liste, wählen Sie eine 64-Bit-Zielplattform.

   > [!NOTE]
   > Im Dialogfeld **Neue Projektmappenplattform** können Sie die Option **Einstellungen kopieren von** verwenden, um vorhandene Projekteinstellungen in die neue 64-Bit-Projektkonfiguration zu kopieren.

1. Klicken Sie auf die Schaltfläche **OK** . Die Plattform, die Sie im vorherigen Schritt ausgewählt haben, wird unter **Aktive Projektmappenplattform** im Dialogfeld **Konfigurations-Manager** angezeigt.

1. Wählen Sie die **schließen** Schaltfläche der **Configuration Manager** Dialogfeld ein, und wählen Sie dann die **OK** Schaltfläche der  **\<Projektname > Eigenschaftenseiten** Dialogfeld.

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>So kopieren Sie Win32-Projekteinstellungen in eine 64-Bit-Projektkonfiguration

- Wenn das Dialogfeld **Neue Projektmappenplattform** geöffnet ist, während Sie ein Projekt für eine 64-Bit-Zielplattform einrichten, wählen Sie in der Dropdownliste **Einstellungen kopieren von** den Wert **Win32**aus. Diese Projekteinstellungen werden auf der Projektebene automatisch aktualisiert:

  - Die Linkeroption [/MACHINE](reference/machine-specify-target-platform.md) wird auf **/MACHINE:X64**festgelegt.

  - **Ausgabe registrieren** ist deaktiviert. Weitere Informationen finden Sie unter [Linker Property Pages](reference/linker-property-pages.md).

  - **Zielumgebung** wird auf **/env x64**festgelegt. Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": Allgemeine](reference/midl-property-pages-general.md).

  - **Parameter überprüfen** wird deaktiviert und auf den Standardwert zurückgesetzt. Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": Erweiterte](reference/midl-property-pages-advanced.md).

  - Wenn **Debuginformationsformat** in der Win32-Projektkonfiguration auf **/ZI** festgelegt war, wird der Wert in der 64-Bit-Projektkonfiguration auf **/Zi** festgelegt. Weitere Informationen finden Sie unter [/Z7, /Zi, /ZI (Debuginformationsformat)](reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Keine dieser Projekteigenschaften wird geändert, wenn sie auf der Dateiebene überschrieben werden.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von C++-Projekten für 64-Bit-X64 Ziele](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Debuggen von 64-Bit-Anwendungen](/visualstudio/debugger/debug-64-bit-applications)
