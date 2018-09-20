---
title: 'Server: Implementieren von Windows für In-Place-Frame | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24c63c10feff624abe399952b682303a6e262d35
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425014"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Server: Implementieren eines In-Place-Frame-Fensters

In diesem Artikel wird erläutert, was Sie tun müssen, um in-Place-Frame-Fensters in die visuelle Bearbeitung Server-Anwendung zu implementieren, wenn Sie nicht der Anwendungs-Assistent zum Erstellen Ihrer Serveranwendung verwenden. Statt die Schritte in diesem Artikel beschriebenen, können Sie eine vorhandenen für ein direktes Rahmenfenster-Klasse von einer Anwendung vom Assistenten generierte Anwendung oder ein Beispiel mit Visual C++ verwenden.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Um ein direktes Rahmenfenster Klasse zu deklarieren.

1. Leiten Sie eine Klasse für ein direktes Rahmenfenster von `COleIPFrameWnd`.

   - Verwenden Sie das DECLARE_DYNCREATE-Makro in der Headerdatei.

   - Verwenden Sie das IMPLEMENT_DYNCREATE-Makro in der Klasse-Implementierungsdatei (.cpp). Dadurch können Objekte dieser Klasse durch das Framework erstellt werden.

1. Deklarieren Sie eine `COleResizeBar` Member in der Frame-Window-Klasse. Dies ist erforderlich, wenn Sie ein direktes Ändern der Größe in Server-Anwendungen zu unterstützen möchten.

     Deklarieren einer `OnCreate` Message-Handler (mit der **Eigenschaften** Fenster), und rufen Sie `Create` für Ihre `COleResizeBar` Member, wenn Sie von Ihnen definiert haben.

1. Wenn Sie über eine Symbolleiste verfügen, deklarieren Sie eine `CToolBar` Member in der Frame-Window-Klasse.

     Überschreiben der `OnCreateControlBars` Memberfunktion versucht, eine Symbolleiste erstellen, wenn der Server direkt aktiv ist. Zum Beispiel:

     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

     Finden Sie in den Ausführungen dieses Codes nach Schritt 5.

1. Einschließen der Headerdatei für diese Klasse für ein direktes Rahmenfenster in der wichtigsten cpp-Datei.

1. In `InitInstance` rufen Sie für Ihre Anwendungsklasse, die `SetServerInfo` Funktion des Dokumentobjekts-Vorlage zum Angeben der Ressourcen und ein direktes Rahmenfenster zu öffnen und die direkte Bearbeitung verwendet werden.

Die Reihe der Funktion aufgerufen wird, der **Wenn** Anweisung erstellt die Symbolleiste aus den Ressourcen der Server bereitgestellt. An diesem Punkt ist die Symbolleiste Teil des Containers Fensterhierarchie. Da diese Symbolleiste abgeleitet wird `CToolBar`, es werden die Nachrichten an dessen Besitzer, Rahmenfenster der containeranwendung, übergeben werden, wenn Sie den Besitzer ändern. Warum ist der Aufruf von `SetOwner` ist erforderlich. Dieser Aufruf ändert sich das Fenster, in denen Befehle gesendet werden soll, des Servers in-Place-Frame-Fenster, sodass die Nachrichten an den Server übergeben werden sollen. Dadurch kann der Server, auf die Vorgänge auf der Symbolleiste zu reagieren, die er bereitstellt.

Die ID für die Symbolleistenbitmap sollten andere direkte definierten Ressourcen in Ihrer Serveranwendung identisch sein. Finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md) Details.

Weitere Informationen finden Sie unter [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), und [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) in die *Klassenbibliotheksreferenz*.

## <a name="see-also"></a>Siehe auch

[Server](../mfc/servers.md)<br/>
[Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)<br/>
[Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)<br/>
[Server: Serverelemente](../mfc/servers-server-items.md)

