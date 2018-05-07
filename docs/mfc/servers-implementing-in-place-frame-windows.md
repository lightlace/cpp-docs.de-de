---
title: 'Server: Implementieren eines In-Place-Frame-Fensters | Microsoft Docs'
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
ms.openlocfilehash: 1cc26e2874921d30ef233509ee46b776ec8e3e9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="servers-implementing-in-place-frame-windows"></a>Server: Implementieren eines In-Place-Frame-Fensters
In diesem Artikel wird erläutert, was Sie tun müssen, um direkte Rahmenfenster in die visuelle Bearbeitung Server-Anwendung zu implementieren, wenn Sie nicht den Assistenten zum Erstellen Sie die Server-Anwendung verwenden. Statt die Schritte in diesem Artikel beschrieben, können Sie eine vorhandenen direkte Rahmenfenster-Klasse von einer Anwendung vom Assistenten generierte Anwendung oder eines Beispiels mit Visual C++ verwenden.  
  
#### <a name="to-declare-an-in-place-frame-window-class"></a>Deklarieren Sie eine direkte Rahmenfenster-Klasse  
  
1.  Leiten Sie eine direkte Rahmenfenster Klasse von `COleIPFrameWnd`.  
  
    -   Verwenden der `DECLARE_DYNCREATE` Makro in der Headerdatei.  
  
    -   Verwenden der `IMPLEMENT_DYNCREATE` Makro in Ihrer Klassenimplementierungsdatei (.cpp). Dadurch können Objekte dieser Klasse durch das Framework erstellt werden.  
  
2.  Deklarieren Sie eine `COleResizeBar` Member in der Rahmenfenster Klasse. Dies ist erforderlich, wenn Sie direkte Ändern der Größe in Server-Anwendungen unterstützen möchten.  
  
     Deklarieren einer `OnCreate` Message-Handler (mithilfe der **Eigenschaften** Fenster), und rufen Sie **erstellen** für Ihre `COleResizeBar` Member auf, wenn Sie sie definiert haben.  
  
3.  Deklarieren Sie eine Symbolleiste ist eine `CToolBar` Member in der Rahmenfenster Klasse.  
  
     Überschreiben Sie die `OnCreateControlBars` Memberfunktion versucht, eine Symbolleiste zu erstellen, wenn der Server aktiv ist. Zum Beispiel:  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     Finden Sie in den Ausführungen dieses Codes nach Schritt 5.  
  
4.  Fügen Sie die Headerdatei für diese Klasse direkte Rahmenfenster in der wichtigsten cpp-Datei.  
  
5.  In `InitInstance` rufen Sie für Ihre Anwendungsklasse, die `SetServerInfo` Funktion des Vorlagenobjekts für das Dokument zum Angeben der Ressourcen und die in-Place-Frame-Fenster zu öffnen und die direkte Bearbeitung verwendet werden.  
  
 Die Reihe der Funktion aufruft, der **Wenn** Anweisung erstellt die Symbolleiste aus der Ressourcen der Server bereitgestellt. An diesem Punkt ist die Symbolleiste Teil des Containers Fensterhierarchie. Da diese Symbolleiste abgeleitet ist `CToolBar`, unverarbeitet parteinachrichten auf dem Besitzer, Rahmenfenster der Steuerelementcontainer-Anwendung, es sei denn, Sie der Besitzer geändert werden. Deshalb ist der Aufruf von `SetOwner` ist erforderlich. Dieser Aufruf ändert das Fenster, in denen Befehle gesendet werden, werden die Server in-Place-Frame-Fenster, verursacht die Nachrichten an den Server übergeben werden. Damit der Server, auf der Symbolleiste zu reagieren, die es bereitstellt.  
  
 Die ID für die Symbolleistenbitmap sollten mit den anderen in der Serveranwendung definierten direktes Ressourcen identisch sein. Finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md) Details.  
  
 Weitere Informationen finden Sie unter [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), und [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) in die *Klassenbibliotheksreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Server](../mfc/servers.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)

