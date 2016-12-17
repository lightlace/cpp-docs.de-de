---
title: "Gewusst wie: Verwenden des Windows&#160;10-SDKs in einer Windows-Desktopanwendung"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden des Windows&#160;10-SDKs in einer Windows-Desktopanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] ein klassisches Windows\-Desktopprojekt erstellen, wird es standardmäßig zur Erstellung mit dem Windows 8.1\-SDK eingerichtet. Diese Version des Windows\-SDKs ist mit alle neueren Windows\-Versionen kompatibel, einschließlich Windows 10. Es enthält jedoch nicht die neuesten Windows 10\-APIs und \-CRT\-Funktionen, die im Windows 10\-SDK enthalten sind. Wenn Sie die neuen APIs verwenden möchten, können Sie das Projekt so neu ausrichten, dass es das Windows 10\-SDK referenziert.  
  
 Ab [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] und dem Windows 10\-SDK wurde die CRT\-Bibliothek in zwei Teile geteilt: eine Bibliothek \(ucrtbase\) mit Funktionen, die in universellen Windows\-Apps verwendet werden können, und eine Bibliothek, die alles andere enthält \(vcruntime140\). Da das Windows 10\-SDK neue Funktionen enthält, z. B. zahlreiche C99\-Funktionen, müssen Sie die folgenden Schritte ausführen, um diese Funktionen verwenden zu können. Siehe [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  
  
### Ausrichten auf das Windows 10\-SDK  
  
1.  Stellen Sie sicher, dass das Windows 10\-SDK installiert ist. Das Windows 10 SDK wird als Teil der [Tools für Windows 10](http://go.microsoft.com/fwlink/?LinkID=617631) installiert.  
  
2.  Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK\-Version neu zuweisen** aus.  
  
     ![SDK&#45;Version neu ausrichten](../windows/media/retargetingwindowssdk1.png "RetargetingWindowsSDK1")  
  
     Das Dialogfeld **Projektmappenaktionen überprüfen** wird angezeigt.  
  
     ![Lösungsaktionen prüfen](../windows/media/retargetingwindowssdk2.png "RetargetingWindowsSDK2")  
  
3.  Wählen Sie in der Dropdownliste **Version der Zielplattform** die Version des Windows 10\-SDKs, für das die Ausrichtung erfolgen soll, oder wählen Sie die Version 8.1, wenn Sie keine Änderungen vornehmen möchten. Klicken Sie auf „OK“, um die Änderung zu übernehmen.  
  
     Beachten Sie, dass „8.1“ sich in diesem Zusammenhang auf die Version des Windows\-SDKs bezieht, die ebenfalls abwärtskompatibel mit Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 und Windows Vista ist.  
  
     Wenn Sie diesen Schritt erfolgreich durchgeführt haben, wird der folgende Text im Ausgabefenster angezeigt:  
  
     `Ende wird neu zugewiesen: 1 abgeschlossen, 0 fehlgeschlagen, 0 übersprungen`  
  
4.  Öffnen Sie die Projekteigenschaften, und achten Sie im Abschnitt **Konfigurationseigenschaften, Allgemein** auf die Werte für **Version der Windows\-Zielplattform**. Wenn Sie den Wert hier ändern, hat dies die gleichen Auswirkungen wie dieses Verfahren. Siehe [Eigenschaftenseite "Allgemein" \(Projekt\)](../ide/general-property-page-project.md).  
  
     ![Version der Zielplattform](../windows/media/retargetingwindowssdk3.png "RetargetingWindowsSDK3")  
  
     Diese Aktion ändert die Werte der Projektmakros, die Pfade zu den Headerdateien und Bibliotheksdateien enthalten. Um die Änderungen zu überprüfen, wählen Sie im Abschnitt mit den Visual C\+\+\-Verzeichnissen des Projekteigenschaften\-Dialogfelds eine der Eigenschaften aus, wie z. B. „Includeverzeichnisse“, öffnen Sie die Dropdownliste, und wählen Sie „\<Bearbeiten\>“. Das Dialogfeld **Includeverzeichnisse** wird angezeigt.  
  
     ![Dialogfeld „Verzeichnisse einschließen“](../windows/media/retargetingwindowssdk4.png "RetargetingWindowsSDK4")  
  
     Klicken Sie auf die Schaltfläche **Makros \>\>**, und blättern Sie in der Liste mit den Makros zu den Windows\-SDK\-Makros, um alle neuen Werte anzuzeigen.  
  
     ![Windows SDK&#45;Makros](../windows/media/retargetingwindowssdk5.png "RetargetingWindowsSDK5")  
  
5.  Wiederholen Sie dies bei Bedarf für andere Projekte, und erstellen Sie die Projektmappe neu.  
  
### Ausrichten auf das Windows 8.1\-SDK  
  
1.  Öffnen Sie das Kontextmenü für den Projektknoten, und wählen Sie **SDK\-Version neu zuweisen** aus.  
  
2.  Wählen Sie in der Dropdown\-Liste „Version der Zielplattform“ den Eintrag „8.1“ aus.  
  
## Siehe auch  
 [Windows Desktop Applications \(Visual C\+\+\)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)