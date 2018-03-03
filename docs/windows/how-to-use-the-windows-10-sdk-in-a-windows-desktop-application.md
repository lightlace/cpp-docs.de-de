---
title: 'Vorgehensweise: Verwenden des Windows 10 SDK in einer Windows-Desktopanwendung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f5e6f09b371c4d295b4bcdff469396a2671d22a
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Gewusst wie: Verwenden des Windows 10-SDKs in einer Windows-Desktopanwendung
Beim Erstellen einer klassischen Windows-Desktopprojekt in Visual Studio 2017 ist es sich standardmäßig einrichten, erstellen Sie mit der Version des Windows 10-SDKS, die installiert wurde, wenn die C++-Desktop-arbeitsauslastung installiert oder zuletzt aktualisiert wurde. Diese Version des Windows SDK ist mit alle neueren Windows-Versionen kompatibel. Wenn Sie eine frühere Version des SDK abzielen möchten, können Sie Projekt öffnen | Eigenschaften, und wählen Sie die anderen SDK-Versionen in der Dropdownliste für das Windows SDK-Version verfügbar.  
  
 Beginnend mit Visual Studio 2015 und Windows 10-SDK, wurde die CRT-Bibliothek getrennt, in zwei Teile: eine (Bibliothek Ucrtbase), die Funktionen enthält, die in universellen Windows-Apps verwendet werden, und eine, die alles andere (vcruntime140) enthält. Da das Windows 10-SDK neue Funktionen enthält, z. B. zahlreiche C99-Funktionen, müssen Sie die folgenden Schritte ausführen, um diese Funktionen verwenden zu können. Siehe [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  
  
### <a name="to-target-the-windows-10-sdk"></a>Ausrichten auf das Windows 10-SDK  
  
1.  Stellen Sie sicher, dass das Windows 10-SDK installiert ist. Das Windows 10-SDK installiert ist, als Teil der [Tools für Windows 10](http://go.microsoft.com/fwlink/p/?linkid=617631).  
  
2.  Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK-Version neu zuweisen**aus.  
  
     ![Ändern Sie die SDK-Version Zielversion](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")  
  
     Das Dialogfeld **Projektmappenaktionen überprüfen** wird angezeigt.  
  
     ![Überprüfen Sie die Projektmappe Aktionen](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")  
  
3.  In der **Version der Zielplattform** Dropdown Liste, wählen Sie die Version des Windows-10-SDKS, die verwendet werden soll. Klicken Sie auf „OK“, um die Änderung zu übernehmen.  
  
     Beachten Sie, dass „8.1“ sich in diesem Zusammenhang auf die Version des Windows-SDKs bezieht, die ebenfalls abwärtskompatibel mit Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 und Windows Vista ist.  
  
     Wenn Sie diesen Schritt erfolgreich durchgeführt haben, wird der folgende Text im Ausgabefenster angezeigt:  
  
     `Retargeting End: 1 completed, 0 failed, 0 skipped`  
  
4.  Öffnen Sie die Projekteigenschaften, und achten Sie im Abschnitt **Konfigurationseigenschaften, Allgemein** auf die Werte für **Version der Windows-Zielplattform**. Wenn Sie den Wert hier ändern, hat dies die gleichen Auswirkungen wie dieses Verfahren. Siehe [General Property Page (Project)](../ide/general-property-page-project.md).  
  
     ![Plattformversion als Ziel](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")  
  
     Diese Aktion ändert die Werte der Projektmakros, die Pfade zu den Headerdateien und Bibliotheksdateien enthalten. Um festzustellen, was sich geändert, im Abschnitt Visual C++-Verzeichnissen des Projekteigenschaften-Dialogfelds eine der Eigenschaften wie z. B. den Includeverzeichnissen, wählen Sie, öffnen Sie die Dropdownliste, und wählen \<Bearbeiten >. Das Dialogfeld **Includeverzeichnisse** wird angezeigt.  
  
     ![Dialogfeld für die Verzeichnisse enthalten](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")  
  
     Wählen Sie die **Makros >>** Schaltfläche, und blättern Sie in der Liste mit den Makros zu den Windows SDK-Makros, um die neuen Werte anzuzeigen.  
  
     ![Windows SDK-Makros](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")  
  
5.  Wiederholen Sie dies bei Bedarf für andere Projekte, und erstellen Sie die Projektmappe neu.  
  
### <a name="to-target-the-windows-81-sdk"></a>Ausrichten auf das Windows 8.1-SDK  
  
1.  Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK-Version neu zuweisen**aus.  
  
2.  Wählen Sie in der Dropdown-Liste „Version der Zielplattform“ den Eintrag „8.1“ aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Desktopanwendungen (Visual C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
