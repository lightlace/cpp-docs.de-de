---
title: 'Vorgehensweise: Konfigurieren von Visual C++ Studio-Projekten für 64-Bit-, x64-Plattformen'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: 762fd5d6ddbb55713cf2fc5e34cb33fb91b08eb9
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492240"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>Vorgehensweise: Konfigurieren von Visual C++ Studio-Projekten für 64-Bit-, x64-Plattformen

Sie können die Projekt Konfigurationen in der Visual Studio-IDE verwenden, um C++ Anwendungen für 64-Bit-x64-Plattformen einzurichten. Außerdem können Sie Win32-Projekteinstellungen zu einer 64-Bit-Projektkonfiguration migrieren.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>So richten Sie C++-Anwendungen für 64-Bit-Zielplattformen ein

1. Öffnen Sie das C++-Projekt, das Sie konfigurieren möchten.

1. Öffnen Sie die Eigenschaftenseiten für das betreffende Projekt. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](working-with-project-properties.md).

   > [!NOTE]
   > Stellen Sie für .net-Projekte sicher, dass der Knoten **Konfigurations Eigenschaften** oder einer der untergeordneten Knoten im  **\<Dialogfeld Projektname > Eigenschaften Seiten** ausgewählt ist. andernfalls bleibt die Schaltfläche **Configuration Manager** erhalten. vorübergehend.

1. Wählen Sie die Schaltfläche **Konfigurations-Manager** aus, um das Dialogfeld **Konfigurations-Manager** zu öffnen.

1. Wählen Sie in der Dropdown Liste **aktive** Projektmappenplattform die  **\<Option neu... >** Option zum Öffnen des Dialog Felds **neue** Projektmappenplattform.

1. Wählen Sie in der Dropdown Liste **neue Plattform eingeben oder auswählen** eine 64-Bit-Zielplattform aus.

   > [!NOTE]
   > Im Dialogfeld **Neue Projektmappenplattform** können Sie die Option **Einstellungen kopieren von** verwenden, um vorhandene Projekteinstellungen in die neue 64-Bit-Projektkonfiguration zu kopieren.

1. Klicken Sie auf die Schaltfläche **OK** . Die Plattform, die Sie im vorherigen Schritt ausgewählt haben, wird unter **Aktive Projektmappenplattform** im Dialogfeld **Konfigurations-Manager** angezeigt.

1. Wählen Sie im Dialogfeld **Configuration Manager** die Schaltfläche **Schließen** aus, und wählen Sie dann im Dialogfeld  **\<Projektname > Eigenschaften Seiten** die Schaltfläche **OK** aus.

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>So kopieren Sie Win32-Projekteinstellungen in eine 64-Bit-Projektkonfiguration

- Wenn das Dialogfeld **Neue Projektmappenplattform** geöffnet ist, während Sie ein Projekt für eine 64-Bit-Zielplattform einrichten, wählen Sie in der Dropdownliste **Einstellungen kopieren von** den Wert **Win32**aus. Diese Projekteinstellungen werden auf der Projektebene automatisch aktualisiert:

  - Die Linkeroption [/MACHINE](reference/machine-specify-target-platform.md) wird auf **/MACHINE:X64**festgelegt.

  - **Ausgabe registrieren** ist deaktiviert. Weitere Informationen finden Sie unter [Linker Property Pages](reference/linker-property-pages.md).

  - **Zielumgebung** wird auf **/env x64**festgelegt. Weitere Informationen finden Sie unter [Eigenschaften Seiten](reference/midl-property-pages.md)für die Mitte.

  - **Parameter überprüfen** wird deaktiviert und auf den Standardwert zurückgesetzt. Weitere Informationen finden Sie unter [Eigenschaften Seiten](reference/midl-property-pages.md)für die Mitte.

  - Wenn **Debuginformationsformat** in der Win32-Projektkonfiguration auf **/ZI** festgelegt war, wird der Wert in der 64-Bit-Projektkonfiguration auf **/Zi** festgelegt. Weitere Informationen finden Sie unter [/Z7, /Zi, /ZI (Debuginformationsformat)](reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Keine dieser Projekteigenschaften wird geändert, wenn sie auf der Dateiebene überschrieben werden.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von C++-Projekten für 64-Bit-x64-Ziele](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Debuggen von 64-Bit-Anwendungen](/visualstudio/debugger/debug-64-bit-applications)
