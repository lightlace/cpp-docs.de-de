---
title: 'Menüs und Ressourcen: Menüs schachteln | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 252619872fc53e06629a4cbded7e3640131dc94a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351965"
---
# <a name="menus-and-resources-menu-merging"></a>Menüs und Ressourcen: Menüs schachteln
In diesem Artikel erläutert die erforderlichen Schritte für OLE-dokumentanwendungen zu behandeln, die visuelle Bearbeitung und direkte Aktivierung ordnungsgemäß. Direkte Aktivierung stellt eine Herausforderung für Container und Server-Anwendungen (Komponente). Der Benutzer in der gleichen Rahmenfenster (im Kontext des Containerdokuments) bleibt jedoch tatsächlich einer anderen Anwendung (Server) ausgeführt wird. Dies erfordert die Koordination zwischen dem Container und Server-Anwendung.  
  
 In diesem Artikel behandelten Themen werden behandelt:  
  
- [Menülayouts](#_core_menu_layouts)  
  
- [Symbolleisten und Statusleisten](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> Menülayouts  
 Der erste Schritt ist zum Koordinieren von Menülayouts. Weitere Informationen finden Sie unter der **Erstellung** im Abschnitt [Menü Programmierung Überlegungen](https://msdn.microsoft.com/library/ms647557.aspx) im Windows SDK.  
  
 Containeranwendungen zu erstellende ein neues Menüs verwendet werden, nur bei eingebettete Elementen direkt aktiviert werden. Dieses Menü sollte mindestens die folgenden, in der aufgeführten Reihenfolge umfassen:  
  
1.  Das Menü "Datei" identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind. (In der Regel sind keine anderen Menüelementen vor dem nächsten Element platziert.)  
  
2.  Zwei aufeinander folgenden Trennzeichen.  
  
3.  Menü "Fenster" identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind (nur, wenn der Container-Anwendung in einer MDI-Anwendung). Einige Anwendungen weisen andere Menüs, z. B. ein Menü "Optionen", die in dieser Gruppe gehören, die Sie im Menü bleibt, wenn ein eingebettetes Element direkt aktiviert ist.  
  
    > [!NOTE]
    >  Es gibt möglicherweise andere Menüs, die die Ansicht des Containerdokuments ein, z. B. Zoom beeinflusst. Diese Containermenüs zwischen den zwei Trennzeichen in der Menüressource angezeigt werden.  
  
 Serveranwendungen (Komponente) sollte auch ein neues Menü speziell für die direkte Aktivierung erstellen. Es sollte sich ebenso wie das Menü, das verwendet wird, wenn Dateien geöffnet sind, jedoch ohne Menüelemente, z. B. Datei- und Fenster, das Dokument nicht die Daten zu bearbeiten. In der Regel besteht aus diesem Menü Folgendes ein:  
  
1.  Bearbeiten Sie im Menü identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind.  
  
2.  Als Trennzeichen.  
  
3.  Bearbeiten von Menüs, z. B. der Stift im Menü in der Scribble-beispielanwendung-Objekt.  
  
4.  Als Trennzeichen.  
  
5.  Menü "Hilfe".  
  
 Betrachten Sie beispielsweise das Layout der einige Beispiel direktes Menüs für einen Container und einen Server aus. Die Details der einzelnen Menüelemente wurden entfernt, um das Beispiel deutlicher zu machen. Die direkte Menü des Containers hat die folgenden Einträge:  
  
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
  
 Die aufeinander folgenden Trennzeichen geben an, wo der erste Teil des Menüs des Servers. Betrachten Sie nun die direkte Menü aus:  
  
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
  
 Die Trennzeichen Hier geben an, wo die zweite Gruppe von Menüelementen Container. Die resultierende Menüstruktur, wenn innerhalb dieses Containers ein Objekt auf diesem Server aktiviert ist, sieht wie folgt:  
  
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
  
 Wie Sie sehen können, wurden die Trennzeichen mit verschiedenen Gruppen des Menüs für jede Anwendung ersetzt.  
  
 Zugriffstastentabellen direkte Menü zugeordnet sollte auch die Server-Anwendung angegeben werden. Der Container wird diese in eine eigene Zugriffstastentabellen integrieren.  
  
 Wenn ein eingebettetes Element direkt aktiviert ist, lädt das Framework das direkte Menü. Anschließend fragt die Server-Anwendung für Menüs für die direkte Aktivierung und fügt es der, in dem die Trennzeichen sind. Dies ist wie die Menüs zu kombinieren. Rufen Sie Menüs aus dem Container für Vorgänge für die Platzierung von Datei und Fenster und Menüs wird vom Server abrufen, die für den Betrieb auf das Element.  
  
##  <a name="_core_toolbars_and_status_bars"></a> Symbolleisten und Statusleisten  
 Serveranwendungen erstellen eine neue Symbolleiste, und seine Bitmap in einer separaten Datei zu speichern. Die Anwendung vom Assistenten generierten Anwendungen speichern diese Bitmap in einer Datei namens ITOOLBAR. BMP. Die neue Symbolleiste ersetzt die containeranwendung-Symbolleiste aus, wenn Ihres Servers Element aktiviert ist, eingerichtet ist, sollten die gleichen Elemente wie die normale Symbolleiste enthalten verwendet werden kann, jedoch Symbole für Elemente in den Menüs Datei und Fenster entfernen.  
  
 Diese Symbolleiste ist geladen, Ihrem `COleIPFrameWnd`-abgeleitete Klasse, die vom Anwendungs-Assistenten erstellt. Die Statusleiste wird von der Steuerelementcontainer-Anwendung behandelt. Weitere Informationen zur Implementierung von Windows für in-Place-Frame, finden Sie unter [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)   
 [Aktivierung](../mfc/activation-cpp.md)   
 [Server](../mfc/servers.md)   
 [Container](../mfc/containers.md)

