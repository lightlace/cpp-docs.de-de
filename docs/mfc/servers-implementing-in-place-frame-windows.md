---
title: "Server: Implementieren eines In-Place-Frame-Fensters"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Rahmenfenster, Implementieren"
  - "Rahmenfenster, Direkt"
  - "platzierte Rahmenfenster"
  - "OLE-Serveranwendungen, Rahmenfenster"
  - "Server, platzierte Rahmenfenster"
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Server: Implementieren eines In-Place-Frame-Fensters
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, was Sie tun müssen, um die direkte Rahmenfenster in der Serveranwendung für visuelle Bearbeitung zu implementieren, wenn der Anwendungs\-Assistenten verwenden, um die Anwendung zu erstellen.  Anstatt den Einhaltens der Prozedur, die in diesem Artikel beschrieben wurde, können Sie eine bestehende Klasse des direkten Rahmenfensters entweder einer vom Assistenten generierten Anwendung der Anwendung oder einem Beispiel verwenden, die mit Visual C\+\+ bereitgestellt wurden.  
  
#### Um eine Klasse des direkten Rahmenfensters deklarieren  
  
1.  Leiten Sie eine Klasse des direkten Rahmenfensters von `COleIPFrameWnd`.  
  
    -   Verwenden Sie das `DECLARE_DYNCREATE` in der Makro Klassenheaderdatei.  
  
    -   Verwenden Sie das `IMPLEMENT_DYNCREATE`\-Makro in der Datei der Klassenimplementierung \(.cpp\).  Dadurch können Objekte dieser vom Framework erstellt werden, Klasse.  
  
2.  Deklarieren Sie einen Member `COleResizeBar` in der Rahmenfensterklasse.  Dies ist erforderlich, wenn Sie direkte Größenanpassung in Serveranwendungen unterstützen möchten.  
  
     Deklarieren Sie einen Meldungshandler `OnCreate` \(mithilfe des Fensters **Eigenschaften** \), und rufen Sie **Erstellen** für den Member `COleResizeBar` auf, wenn Sie sie definiert haben.  
  
3.  Wenn Sie eine Symbolleiste vorhanden ist, deklarieren einen Member `CToolBar` in der Rahmenfensterklasse.  
  
     Überschreiben Sie die `OnCreateControlBars`\-Memberfunktion, um eine Symbolleiste zu erstellen, wenn der Server aktives gesorgt ist.  Beispiel:  
  
     [!CODE [NVC_MFCOleServer#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleServer#1)]  
  
     Siehe die Erörterung dieser Code nach Schritt 5.  
  
4.  Schließen Sie die Headerdatei für diese Klasse des direkten Rahmenfensters in der Haupt\-CPP\-Datei ein.  
  
5.  In `InitInstance` für die Anwendungsklasse verfügen, rufen Sie die `SetServerInfo`\-Funktion des Dokumentvorlagenobjekts auf, um den in geöffnetem und der direkten Bearbeitung verwendet werden Ressourcen und dem direkten Rahmenfenster, anzugeben.  
  
 Die Reihe von Funktionsaufrufen in der **if**\-Anweisung stellt die Symbolleiste von Ressourcen erstellt, die der Server bereitgestellt hat.  Damit ist die Symbolleiste ein Teil der Fensterhierarchie des Containers.  Da diese Symbolleiste von `CToolBar` abgeleitet ist, geht diese ihre Nachrichten an den Besitzer, das Rahmenfenster der Containeranwendung weiter, es sei denn, Sie den Besitzer ändern.  Deshalb ist der Aufruf von `SetOwner` erforderlich.  Dieser Aufruf wird das Fenster, in dem Befehle, das direktes Rahmenfenster des Servers sein gesendet werden und bewirkt die Meldungen, die an den Server übergeben werden.  Dies ermöglicht dem Server, die Operationen auf einer Symbolleiste zu reagieren, die er bereitstellt.  
  
 Die ID der Symbolleistenbitmap sollte mit der direkten anderen Ressourcen sein, die in der Serveranwendung definiert werden.  Ausführliche Informationen finden Sie unter [Menüs und Ressourcen: Server\-Hinzufügungen](../mfc/menus-and-resources-server-additions.md).  
  
 Weitere Informationen finden Sie unter [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md) und [CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md) in der Class Library Reference.  
  
## Siehe auch  
 [Server](../mfc/servers.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)