---
title: 'Gewusst wie: Verwenden des Windows 10 SDK in einer Windows-Desktop Anwendung'
description: Legen Sie fest, wie die SDK-Zielversion in einem Windows-Desktop Anwendungsprojekt für die Verwendung des Windows 10 SDK festgelegt wird.
ms.custom: get-started-article
ms.date: 01/22/2020
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: c1d71b591398453f7cee02aa22cd2e377991588f
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725733"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Gewusst wie: Verwenden des Windows 10 SDK in einer Windows-Desktop Anwendung

Wenn Sie in Visual Studio ein neues klassisches Windows-Desktop Projekt erstellen, ist es standardmäßig auf das Windows 10 SDK ausgerichtet. Visual Studio installiert eine Version dieses SDK, wenn Sie die Arbeits C++ Auslastung des Desktops installieren. Das Windows 10 SDK unterstützt das Schreiben von Code für Windows 7 SP1 und höher. Weitere Informationen zur Ausrichtung auf bestimmte Versionen von Windows finden [Sie unter Verwenden der Windows-Header](/windows/win32/WinProg/using-the-windows-headers) und Aktualisieren von [winver und _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).

Wenn Sie ein vorhandenes Projekt aktualisieren, haben Sie folgende Möglichkeiten: Sie können die in Ihrem Projekt angegebene Ziel Windows SDK weiterhin verwenden. Oder Sie können Ihr Projekt neu zuweisen, um das Windows 10 SDK zu verwenden. Mit dem Windows 10 SDK erhalten Sie die Vorteile der Unterstützung für die neuesten Betriebssysteme und Sprachstandards.

## <a name="use-the-right-windows-sdk-for-your-project"></a>Verwenden Sie die richtige Windows SDK für Ihr Projekt.

Ab Visual Studio 2015 wurde die c-Lauf Zeit Bibliothek (CRT) in zwei Teile unterteilt: ein Teil, ucrtbase, enthält die Standard mäßigen C-und Microsoft-spezifischen CRT-Funktionen, die Sie in universellen Windows-Apps verwenden können. Diese Bibliothek wird jetzt als universelle CRT oder ucrt bezeichnet und ist in das Windows 10 SDK verschoben worden. Die ucrt enthält zahlreiche neue Funktionen, wie z. b. C99-Funktionen, C++ die zur Unterstützung der neuesten Sprachstandards benötigt werden. Der andere Teil der ursprünglichen CRT ist vcruntime. Sie enthält die C-Laufzeitunterstützung, den Start-und Beendigungs Code und alles andere, was nicht in die ucrt wechselt. Die vcruntime-Bibliothek wird zusammen mit dem C++ Compiler und Toolset in Visual Studio installiert. Weitere Informationen finden Sie unter [Funktionen der CRT-Bibliothek](../c-runtime-library/crt-library-features.md).

Die ucrt ist nun eine Systemkomponente, die auf jeder Version von Windows 10 installiert ist. Sie steht auch als installierbare Komponente für alle früheren unterstützten Windows-Versionen zur Verfügung. Mit dem Windows 10 SDK können Sie alle unterstützten Versionen von Windows als Ziel verwenden. Eine umfassende Liste der unterstützten Betriebssysteme finden Sie unter [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

Führen Sie die folgenden Schritte aus, um Ihre Projekte für die Verwendung des Windows 10 SDK zu verwenden, wenn Sie ein Upgrade von einer Projekt Version vor Visual Studio 2015 durchführen:

### <a name="to-target-the-windows-10-sdk"></a>Ausrichten auf das Windows 10-SDK

1. Stellen Sie sicher, dass das Windows 10-SDK installiert ist. Das Windows 10 SDK wird als Teil der **Desktop Entwicklung mit C++**  Arbeitsauslastung installiert. Eine eigenständige Version ist unter [Downloads und Tools für Windows 10](https://developer.microsoft.com/windows/downloads)verfügbar.

1. Öffnen Sie das Kontextmenü für den Projekt Knoten, und wählen Sie **Projekte neu**zuweisen aus. (Wählen Sie in früheren Versionen von Visual Studio die Option **SDK-Version neu**zuweisen aus.) Das Dialogfeld **projektmappenaktionen überprüfen** wird angezeigt.

   ![Lösungs Aktionen überprüfen](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

1. Wählen Sie in der Dropdown Liste **Ziel Platt Form Version** die Version des Windows 10 SDK aus, auf das Sie abzielen möchten. Im Allgemeinen wird empfohlen, die neueste installierte Version auszuwählen. Wählen Sie die Schaltfläche **OK** , um die Änderung zu übernehmen.

   8,1 in diesem Kontext bezieht sich auf das Windows 8.1 SDK.

   Wenn Sie diesen Schritt erfolgreich durchgeführt haben, wird der folgende Text im Ausgabefenster angezeigt:

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

1. Öffnen Sie das Dialogfeld Projekteigenschaften. Beachten Sie im Abschnitt **Konfigurations Eigenschaften** > **Allgemein** die Werte der **Version der Windows-Zielplattform**. Wenn Sie den Wert hier ändern, hat dies die gleichen Auswirkungen wie dieses Verfahren. Weitere Informationen finden Sie unter [General Property Page (Project) (Eigenschaftenseite „Allgemein“ (Projekt))](../build/reference/general-property-page-project.md).

   ![Version der Zielplattform](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   Diese Aktion ändert die Werte der Projektmakros, die Pfade zu den Headerdateien und Bibliotheksdateien enthalten. Um zu sehen, was sich geändert hat, öffnen Sie den Abschnitt **visuelle C++ Verzeichnisse** des Dialog Felds **Projekteigenschaften** . Wählen Sie eine der Eigenschaften aus, z. b. **Verzeichnisse einschließen**. Öffnen Sie dann die Dropdown Liste der Eigenschaftswerte, und wählen Sie **\<> Bearbeiten**. Das Dialogfeld **Includeverzeichnisse** wird angezeigt.

   ![Dialogfeld ' Verzeichnisse einschließen '](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   Wählen Sie die Schaltfläche **Makros > >** aus, und Scrollen Sie in der Liste der Makros nach unten, Windows SDK um alle neuen Werte anzuzeigen.

   ![Windows SDK Makros](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

1. Wiederholen Sie das Neuzuweisungs Verfahren bei Bedarf für andere Projektmappenprojekte, und erstellen Sie die Lösung neu.

### <a name="to-target-the-windows-81-sdk"></a>Ausrichten auf das Windows 8.1-SDK

1. Öffnen Sie das Kontextmenü für den Projekt Knoten in Projektmappen-Explorer, und wählen Sie **Projekte neu**zuweisen aus. (Wählen Sie in früheren Versionen von Visual Studio die Option **SDK-Version neu**zuweisen aus.)

2. Wählen Sie in der Dropdown Liste **Ziel Platt Form Version** die Option **8,1**aus.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Erstellen einer herkömmlichen Windows-C++Desktop Anwendung ()](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)
