---
title: "Men&#252;s und Ressourcen: Men&#252;s schachteln"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Koordinieren von Menülayouts"
  - "Menüs [C++], OLE-Dokumentanwendungen"
  - "Zusammenführen von Symbolleiste und Statusleiste"
  - "OLE-Container, Menüs und Ressourcen"
  - "Statusleisten, OLE-Dokumentanwendungen"
  - "Symbolleisten [C++], OLE-Dokumentanwendungen"
  - "Visuelle Bearbeitung, Anwendungsmenüs und Ressourcen"
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
caps.latest.revision: 9
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Men&#252;s und Ressourcen: Men&#252;s schachteln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel sind die Schritte aufgeführt, die für OLE\-Dokument\-Anwendungen visuelle Bearbeiten und direkte Aktivierung ordnungsgemäß erforderlich sind, behandeln.  Direkte Aktivierung stellt eine Herausforderung für Container\- und Server\(Komponente\) Anwendungen dar.  Der Benutzer bleibt im gleichen Rahmenfenster \(im Zusammenhang mit dem Containerdokument\) führt jedoch eigentlich eine andere Anwendung aus \(den Server\).  Dies erfordert Koordination zwischen den Ressourcen des Containers und Serveranwendungen.  
  
 Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Menü\-Layouts](#_core_menu_layouts)  
  
-   [Symbolleisten und Statusleisten](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> Menü\-Layouts  
 Der erste Schritt ist, Menülayouts zu koordinieren.  Weitere Informationen finden Sie im Abschnitt **Menüerstellung** in [Menü\-Programmier Überlegungen](https://msdn.microsoft.com/en-us/library/ms647557.aspx) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Containeranwendungen sollten ein neues Menü verwendet werden, erstellen, nur, wenn eingebettete Elemente direkt aktiv sind.  Am Mindest\- sollte diesem Menü aus Folgendem bestehen, in der angegebenen Reihenfolge:  
  
1.  Menü identisch bis die verwendet wird, wenn Dateien geöffnet sind. \(Normalerweise werden keine anderen Menüelemente vor der nächste Punkt platziert\).  
  
2.  Zwei aufeinander folgende Kommas.  
  
3.  Fenstermenü identisch bis das verwendet wird, wenn Dateien geöffnet sind \(nur wenn die Containeranwendung in einer MDI\-Anwendung.\)  Einige Anwendungen haben möglicherweise andere Menüs, wie ein Optionsmenü, die in dieser Gruppe angehören, die im Menü bleibt, wenn ein eingebettetes Element an der Stelle aktiviert ist.  
  
    > [!NOTE]
    >  Es gibt andere Menüs, die die Ansicht des Containerdokuments auswirken, z Zoom.  Diese Containermenüs werden zwischen den zwei Trennzeichen in dieser Menüressource.  
  
 Anwendungen des Servers \(Komponente\) sollten ein neues Menü für direkte Aktivierung auch ausdrücklich erstellen.  Sie sollte sein wie das Menü, das verwendet wird, wenn Dateien geöffnet sind, aber ohne Menüelemente, wie Datei und Fenstern, die das Serverdokument anstelle der Daten bearbeiten.  In der Regel besteht dieses Menü aus Folgendem:  
  
1.  Bearbeiten Sie das Menü, das dem identisch ist, das verwendet wird, wenn Dateien geöffnet sind.  
  
2.  Trennzeichen.  
  
3.  Planen Sie Bearbeitungsmenüs, wie das Stiftsmenü in der Scribblebeispielanwendung ein.  
  
4.  Trennzeichen.  
  
5.  Menü Hilfe.  
  
 Ein Beispiel Blick auf das Layout einiger Beispieldirekter Menüs für einen Container und Server ein.  Die Details jedes Menüelements wurden entfernt, um den Beispielsreiniger zu machen.  Das direkte Menü des Containers hat die folgenden Einträge:  
  
```  
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&File C1"  
    MENUITEM SEPARATOR  
    POPUP "&Zoom C2"  
    MENUITEM SEPARATOR  
    POPUP "&Options C3"  
    POPUP "&Window C3"  
END  
```  
  
 Die nachfolgenden Trennzeichen wird angegeben, wo der erste Teil des Servers wechseln soll.  Betrachten Sie nun das direktes Menü des Servers:  
  
```  
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&Edit S1"  
    MENUITEM SEPARATOR  
    POPUP "&Format S2"  
    MENUITEM SEPARATOR  
    POPUP "&Help S3"  
END  
```  
  
 Die hier Trennzeichen wird angegeben, wo die zweite Gruppe von Containermenüelementen wechseln soll.  Die resultierende Menüstruktur, wenn ein Objekt aus diesem Server in der dieses Containers aussehen wie folgt aktiviert gesorgt ist:  
  
```  
BEGIN  
    POPUP "&File C1"  
    POPUP "&Edit S1"  
    POPUP "&Zoom C2"  
    POPUP "&Format S2"  
    POPUP "&Options C3  
    POPUP "&Window C3"  
    POPUP "&Help S3"  
END  
```  
  
 Wie Sie sehen können, sind die durch Trennzeichen die verschiedenen Gruppen des Menüs jeder Anwendung ersetzt.  
  
 Die Zugriffstastentabellen, die dem direkten Menü zugeordnet sind, sollten durch die Serveranwendung ebenfalls angegeben werden.  Der Container enthält sie in seine eigenen Zugriffstastentabellen.  
  
 Wenn ein eingebettetes Element an der Stelle aktiviert ist, lädt das Framework das direktes Menü.  Anschließend fordert die Serveranwendung für das Menü um direkte Aktivierung und fügt sie ein, wo die Trennzeichen sind.  Dies ist, wie Menüs kombinieren.  Rufen Sie Menüs vom Container für das Funktionieren der Fensteranordnung auf Datei\- und ab, und rufen Sie Menüs vom Server für das Funktionieren auf das Element ab.  
  
##  <a name="_core_toolbars_and_status_bars"></a> Symbolleisten und Statusleisten  
 Serveranwendungen sollten eine neue Symbolleiste erstellen und die Bitmap in einer separaten Datei speichern.  Die vom Assistenten generierten Anwendungen der Anwendung speichern diese Bitmap in einer Datei mit dem Namen ITOOLBAR.BMP.  Die neue Symbolleiste ersetzt die Symbolleiste der Containeranwendung, wenn das Element des Servers an der Stelle aktiviert ist, und die gleichen Elemente wie die normale Symbolleiste enthalten, aber entfernt die Symbole, die Elemente der Datei\- und Fenstermenüs darstellen.  
  
 Diese Symbolleiste ist im `COleIPFrameWnd` abgeleitete Klasse geladen, wird für Sie im Anwendungs\-Assistenten.  Die Statusleiste wird über die Containeranwendung behandelt.  Weitere Informationen über die Implementierung von Rahmenfenstern direkten, finden Sie unter [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md).  
  
## Siehe auch  
 [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Aktivierung](../mfc/activation-cpp.md)   
 [Server](../mfc/servers.md)   
 [Container](../mfc/containers.md)