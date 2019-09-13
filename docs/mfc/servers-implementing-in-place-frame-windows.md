---
title: 'Server: Implementieren von direkten Rahmen Fenstern'
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: bc5439003b7c891ac3f4000c9b7820746aec4c8d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907545"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Server: Implementieren von direkten Rahmen Fenstern

In diesem Artikel wird erläutert, was Sie tun müssen, um direkte Rahmen Fenster in Ihrer Anwendung für die visuelle Bearbeitung zu implementieren, wenn Sie die Serveranwendung nicht mit dem Anwendungs-Assistenten erstellen. Anstelle des in diesem Artikel beschriebenen Verfahrens können Sie eine vorhandene direkte Frame Fenster Klasse entweder aus einer vom Anwendungs Assistenten generierten Anwendung oder aus einem mit Visual C++bereitgestellten Beispiel verwenden.

#### <a name="to-declare-an-in-place-frame-window-class"></a>So deklarieren Sie eine direkte Frame-Window-Klasse

1. Leiten Sie eine direkte Frame Fenster Klasse von ab `COleIPFrameWnd`.

   - Verwenden Sie das DECLARE_DYNCREATE-Makro in der Klassen Header Datei.

   - Verwenden Sie das IMPLEMENT_DYNCREATE-Makro in der Klassen Implementierungs Datei (. cpp). Dadurch können Objekte dieser Klasse vom Framework erstellt werden.

1. Deklarieren `COleResizeBar` Sie einen Member in der Frame-Window-Klasse. Dies ist erforderlich, wenn Sie die direkte Größe von Server Anwendungen unterstützen möchten.

   Deklarieren `OnCreate` Sie einen Nachrichten Handler (mit dem [Klassen-Assistenten](reference/mfc-class-wizard.md)) `Create` , und `COleResizeBar` rufen Sie für den Member auf, sofern Sie ihn definiert haben.

1. Wenn Sie über eine Symbolleiste verfügen, `CToolBar` deklarieren Sie einen Member in der Frame-Window-Klasse.

   Überschreiben `OnCreateControlBars` Sie die Member-Funktion, um eine Symbolleiste zu erstellen, wenn der Server aktiv ist. Beispiel:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   Weitere Informationen finden Sie in der Erörterung dieses Codes nach Schritt 5.

1. Fügen Sie die Header Datei für diese direkte Frame-Window-Klasse in die Datei "Main. cpp" ein.

1. Nennen `InitInstance` Sie in für die Anwendungsklasse die `SetServerInfo` -Funktion des Dokumentvorlagen Objekts, um die Ressourcen und das direkte Rahmen Fenster anzugeben, das bei der geöffneten und direkten Bearbeitung verwendet werden soll.

Die Reihe von Funktionsaufrufen in der **if** -Anweisung erstellt die Symbolleiste aus den Ressourcen, die der Server bereitgestellt hat. An diesem Punkt ist die Symbolleiste Teil der Fenster Hierarchie des Containers. Da diese Symbolleiste von `CToolBar`abgeleitet ist, übergibt Sie die Nachrichten an ihren Besitzer, das Rahmen Fenster der Containeranwendung, es sei denn, Sie ändern den Besitzer. Aus diesem Grund `SetOwner` ist der-Rückruf erforderlich. Mit diesem Befehl wird das Fenster geändert, in dem Befehle an das direkte Rahmen Fenster des Servers gesendet werden, sodass die Nachrichten an den Server übermittelt werden. Dies ermöglicht es dem Server, auf Vorgänge auf der Symbolleiste zu reagieren, die er bereitstellt.

Die ID für die Symbolleisten-Bitmap sollte mit den anderen direkten Ressourcen identisch sein, die in der Serveranwendung definiert sind. Siehe [Menüs und Ressourcen: Server Ergänzungen](../mfc/menus-and-resources-server-additions.md) für Details.

Weitere Informationen finden Sie unter [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md)und [CDocTemplate:: setserverinfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) in der *Klassen Bibliotheks Referenz*.

## <a name="see-also"></a>Siehe auch

[Server](../mfc/servers.md)<br/>
[Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)<br/>
[Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)<br/>
[Server: Serverelemente](../mfc/servers-server-items.md)
