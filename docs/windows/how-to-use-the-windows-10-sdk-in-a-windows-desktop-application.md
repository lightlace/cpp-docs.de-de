---
title: 'Vorgehensweise: Verwenden des Windows 10 SDK in einer Windows-Desktop Anwendung'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: 8dbf18d24c0369507743c3c1da624838f9ab4703
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69513819"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Vorgehensweise: Verwenden des Windows 10 SDK in einer Windows-Desktop Anwendung

Wenn Sie in Visual Studio 2017 ein klassisches Windows-Desktop Projekt erstellen, wird es standardmäßig so eingerichtet, dass es mit der Version des Windows 10 SDK erstellt wird, das C++ beim Installieren oder letzten Aktualisieren der Desktop Arbeitsauslastung installiert wurde. Diese Version des Windows SDK ist kompatibel mit Windows 7 und höher. Weitere Informationen zu bestimmten Versionen von Windows finden [Sie unter Verwenden der Windows-Header](/windows/win32/WinProg/using-the-windows-headers) .

Wenn Sie auf eine frühere Version des SDK abzielen möchten, können Sie das Projekt öffnen.  **Eigenschaften** und wählen Sie aus den anderen SDK-Versionen aus, die in der Dropdown Liste Windows SDK Version verfügbar sind.

Beginnend mit Visual Studio 2015 und dem Windows 10-SDK wurde die CRT-Bibliothek in zwei Teile unterteilt: eine (ucrtbase), die die Funktionen enthält, die für die Verwendung in universellen Windows-apps zulässig sind, und eine, die alles andere enthält (vcruntime140). Da das Windows 10-SDK neue Funktionen enthält, z. B. zahlreiche C99-Funktionen, müssen Sie die folgenden Schritte ausführen, um diese Funktionen verwenden zu können. Siehe [CRT Library Features](../c-runtime-library/crt-library-features.md).

### <a name="to-target-the-windows-10-sdk"></a>Ausrichten auf das Windows 10-SDK

1. Stellen Sie sicher, dass das Windows 10-SDK installiert ist. Das Windows 10 SDK wird als Teil der **Desktop Entwicklung mit C++**  Arbeitsauslastung installiert. Eine eigenständige Version ist unter [Downloads und Tools für Windows 10](https://developer.microsoft.com/windows/downloads)verfügbar.

2. Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK-Version neu zuweisen**aus.

   ![SDK-Version neu ausrichten](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")

   Das Dialogfeld **Projektmappenaktionen überprüfen** wird angezeigt.

   ![Lösungs Aktionen überprüfen](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

3. Wählen Sie in der Dropdown Liste **Ziel Platt Form Version** die Version des Windows 10 SDK aus, auf das Sie abzielen möchten. Klicken Sie auf „OK“, um die Änderung zu übernehmen.

   Beachten Sie, dass „8.1“ sich in diesem Zusammenhang auf die Version des Windows-SDKs bezieht, die ebenfalls abwärtskompatibel mit Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 und Windows Vista ist.

   Wenn Sie diesen Schritt erfolgreich durchgeführt haben, wird der folgende Text im Ausgabefenster angezeigt:

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

4. Öffnen Sie die Projekteigenschaften, und achten Sie im Abschnitt **Konfigurationseigenschaften, Allgemein** auf die Werte für **Version der Windows-Zielplattform**. Wenn Sie den Wert hier ändern, hat dies die gleichen Auswirkungen wie dieses Verfahren. Siehe [General Property Page (Project)](../build/reference/general-property-page-project.md).

   ![Version der Zielplattform](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   Diese Aktion ändert die Werte der Projektmakros, die Pfade zu den Headerdateien und Bibliotheksdateien enthalten. Um zu sehen, was sich geändert hat, wählen Sie im Abschnitt "  **C++ visuelle Verzeichnisse** " des Dialog Felds " **Projekteigenschaften** " eine der Eigenschaften aus, z. b. Includeverzeichnisse, \<öffnen Sie die Dropdown Liste, und wählen Sie > Bearbeiten aus. Das Dialogfeld **Includeverzeichnisse** wird angezeigt.

   ![Dialogfeld ' Verzeichnisse einschließen] ' (../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   Wählen Sie die Schaltfläche **Makros > >** aus, und Scrollen Sie in der Liste der Makros nach unten, Windows SDK um alle neuen Werte anzuzeigen.

   ![Windows SDK Makros](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

5. Wiederholen Sie dies bei Bedarf für andere Projekte, und erstellen Sie die Projektmappe neu.

### <a name="to-target-the-windows-81-sdk"></a>Ausrichten auf das Windows 8.1-SDK

1. Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK-Version neu zuweisen**aus.

2. Wählen Sie in der Dropdown Liste **Ziel Platt Form Version** die Option **8,1**aus.

## <a name="see-also"></a>Siehe auch

[Windows-Desktop Anwendungen ( C++Visual)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)