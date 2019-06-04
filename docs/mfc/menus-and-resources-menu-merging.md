---
title: 'Menüs und Ressourcen: Zusammenführen von Menüs'
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
ms.openlocfilehash: 1f7af7007e72cb8e01022c81a244fc70ba52a5cc
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504824"
---
# <a name="menus-and-resources-menu-merging"></a>Menüs und Ressourcen: Zusammenführen von Menüs

Dieser Artikel erläutert die erforderlichen Schritte für OLE-dokumentanwendungen zu behandeln, visuelle Bearbeitung und direkte Aktivierung ordnungsgemäß. Direkte Aktivierung ist eine Herausforderung für Container und Server-Anwendungen (Komponente). Der Benutzer bleibt in der gleichen Rahmenfenster (im Kontext des Containerdokuments), aber es ist tatsächlich eine andere Anwendung (dem Server) ausgeführt. Dies erfordert die Koordination zwischen den Ressourcen der Container und Server.

In diesem Artikel behandelten Themen umfassen:

- [Menülayouts](#_core_menu_layouts)

- [Symbolleisten und Statusleisten](#_core_toolbars_and_status_bars)

##  <a name="_core_menu_layouts"></a> Menülayouts

Der erste Schritt ist zum Koordinieren von Menülayouts. Containeranwendungen sollten, erstellen ein neues Menüs verwendet werden, nur, wenn eingebettete Elemente direkt aktiviert werden. Mindestens sollte in diesem Menü aus folgenden, in der aufgeführten Reihenfolge bestehen:

1. Menü "Datei" identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind. (In der Regel sind keine anderen Menüelementen vor dem nächsten Element platziert.)

1. Zwei aufeinander folgende Trennzeichen.

1. Menü "Fenster" identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind (nur, wenn der Container-Anwendung in einer MDI-Anwendung). Einige Anwendungen weisen andere Menüs, z. B. ein Menü "Optionen", die in dieser Gruppe gehören, die Sie im Menü bleibt, wenn ein eingebettetes Element direkt aktiviert ist.

    > [!NOTE]
    >  Es gibt möglicherweise andere Menüs, die die Ansicht des Containerdokuments, beispielsweise Zoom zu beeinflussen. Diese Containermenüs angezeigt werden, zwischen den zwei Trennzeichen in der Menüressource.

Serveranwendungen (Komponente) sollten auch ein neues Menü speziell für die direkte Aktivierung erstellen. Es sollte sich ebenso wie das Menü, das verwendet wird, wenn Dateien geöffnet sind, jedoch ohne Menüelemente, z. B. Datei- und Fenster, das das Serverdokument anstelle der Daten zu bearbeiten. In der Regel besteht aus diesem Menü den folgenden:

1. Bearbeiten Sie im Menü identisch mit dem Kennwort verwendet, wenn Dateien geöffnet sind.

1. Trennzeichen.

1. Bearbeiten von Menüs, z. B. die Pen-Menü in der beispielanwendung Scribble-Objekt.

1. Trennzeichen.

1. Menü "Hilfe".

Betrachten Sie beispielsweise das Layout der einige Beispiel für ein direktes Menüs für einen Container und einen Server aus. Die Details der einzelnen Menüelemente wurden zur Verdeutlichung des Beispiels entfernt. In-Place-Menü des Containers weist die folgenden Einträge:

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

Aufeinander folgende Trennzeichen geben an, in dem der erste Teil des Servers im Menü eingefügt werden sollen. Betrachten Sie nun das Serverzertifikat Menü:

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

Geben Sie hier die Trennzeichen an, in denen die zweite Gruppe von Menüelementen Container gespeichert werden sollen. Die resultierende Menüstruktur, wenn ein Objekt von diesem Server direkt innerhalb dieses Containers aktiviert ist, sieht folgendermaßen aus:

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

Wie Sie sehen können, wurden die Trennzeichen mit den verschiedenen Gruppen des Menüs für jede Anwendung ersetzt.

Zugriffstastentabellen, die mit dem in-Place-Menü verknüpft ist, sollte auch von der Serveranwendung angegeben werden. Der Container wird diese in eigenen Zugriffstastentabellen zu integrieren.

Wenn ein eingebettetes Element direkt aktiviert ist, lädt das Framework das Menü an. Anschließend fragt die Serveranwendung für Menüs für die direkte Aktivierung und fügt es der, in dem die Trennzeichen sind. Dies ist wie die Menüs zu kombinieren. Rufen Sie Menüs aus dem Container für Vorgänge für die Platzierung von Datei und das Fenster und Menüs wird vom Server abrufen, für den Betrieb für das Element.

##  <a name="_core_toolbars_and_status_bars"></a> Symbolleisten und Statusleisten

Server-Anwendungen eine neue Symbolleiste erstellen und speichern die Bitmap in einer separaten Datei. Die-Assistenten generierte Anwendungen speichern diese Bitmap in eine Datei namens ITOOLBAR. BMP. Die neue Symbolleiste ersetzt die Container-Anwendung-Symbolleiste aus, wenn Ihr Server Element ist vorhanden, aktiviert sollten die gleichen Elemente wie eine normale Symbolleiste enthalten verwendet werden kann, aber Entfernen von Symbolen, die Elemente in der Datei und Fenster-Menüs darstellt.

Diese Symbolleiste ist geladen, Ihre `COleIPFrameWnd`-abgeleitete Klasse, die vom Anwendungs-Assistenten für Sie erstellt. Die Statusleiste erfolgt über die Container-Anwendung. Weitere Informationen zur Implementierung von in-Place-Frame-Fensters finden Sie unter [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md).

## <a name="see-also"></a>Siehe auch

[Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Activation (Aktivierung)](../mfc/activation-cpp.md)<br/>
[Server](../mfc/servers.md)<br/>
[Container](../mfc/containers.md)
