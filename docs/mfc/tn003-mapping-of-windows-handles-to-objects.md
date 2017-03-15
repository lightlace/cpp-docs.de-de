---
title: "TN003: Zuordnen von Fensterhandles zu Objekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mapping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Handlezuordnungen"
  - "Zuordnungen, Windows-Handles zu Objekten"
  - "TN003"
  - "Windows-Handles zu Objekten [C++]"
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# TN003: Zuordnen von Fensterhandles zu Objekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die MFC\-Routinen, die die Zuordnung von Windows\-Objekthandles C\+\+\-Objekten zu unterstützen.  
  
## Das Problem  
 Windows\-Objekte werden in der Regel von verschiedenen [HANDLE](http://msdn.microsoft.com/library/windows/desktop/aa383751)\-Objekte dargestellt, die die MFC\-Klassen\-Umbruch Windows\-Objekthandles mit C\+\+ Objekte.  Die Handleumbruchsfunktionen der MFC\-Klassen\-Bibliothek lassen Sie das C\+\+\-Objekt finden, das das Windows\-Objekt umschließt, das ein bestimmtes Handle hat.  Bisweilen hat kein Objekt Wrapperobjekt einer C\+\+\-Datei und zu diesen Fällen erstellt das System ein temporäres Objekt, das als C\+\+\-Wrapper fungiert.  
  
 Windows \- Objekt, dass Verwendungshandlezuordnungen sind, wie folgt:  
  
-   HWND \([CWnd](../mfc/reference/cwnd-class.md) und `CWnd` abgeleitete Klassen\)  
  
-   HDC \([CDC](../mfc/reference/cdc-class.md) und `CDC` abgeleitete Klassen\)  
  
-   HMENU \([CMenu](../mfc/reference/cmenu-class.md)\)  
  
-   HPEN \([CGdiObject](../mfc/reference/cgdiobject-class.md)\)  
  
-   HBRUSH \(`CGdiObject`\)  
  
-   HFONT \(`CGdiObject`\)  
  
-   HBITMAP \(`CGdiObject`\)  
  
-   HPALETTE \(`CGdiObject`\)  
  
-   HRGN \(`CGdiObject`\)  
  
-   HIMAGELIST \([CImageList](../mfc/reference/cimagelist-class.md)\)  
  
-   SOCKET \([CSocket](../mfc/reference/csocket-class.md)\)  
  
 Ein Handle bis eines dieser Objekte zugewiesen, können Sie das MFC\-Objekt finden, das das Handle umschließt, indem die statische Methode `FromHandle` aufruft.  Beispielsweise HWND angegeben dem Namen `hWnd`, die folgenden Zeilen zurückgibt einen Zeiger auf `CWnd` auf, der `hWnd` umschließt:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Wenn `hWnd` kein bestimmtes Wrapperobjekt hat, wird temporäres `CWnd`, um `hWnd` zu umschließen.  Dies ermöglicht es, ein gültiges C\+\+\-Objekt von jedem Handle zu erhalten.  
  
 Nachdem Sie ein Wrapperobjekt haben, können Sie das Handle einer Variable des öffentlichen Members der Wrapperklasse abrufen.  Bei `CWnd` enthält `m_hWnd` HWND für dieses Objekt.  
  
## Anfügen von Handles auf MFC\-Objekte  
 Ein neu erstelltes HandleWrapperobjekt und ein Handle für ein Windows\-Objekt gegeben, können Sie die beiden zuordnen, indem Sie die `Attach`\-Funktion entsprechend diesem Beispiel aufrufen:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);  
```  
  
 Dies macht einen Eintrag der permanenten Zuordnung, die `myWnd` und `hWnd` zuordnet.  `CWnd::FromHandle(hWnd)` aufrufen, gibt jetzt einen Zeiger auf `myWnd` zurück.  Wenn `myWnd` gelöscht wird, zerstört der Destruktor automatisch `hWnd`, indem er der Windows\-Funktion [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  Wenn dies nicht erforderlich ist, muss `hWnd` von `myWnd` getrennt werden, bevor `myWnd` zerstört wird \(normalerweise, wenn der Bereich verlassen wird, in dem `myWnd` definiert wurde\).  Die `Detach`\-Methode geschieht.  
  
```  
myWnd.Detach();  
```  
  
## Weitere zu temporären Objekte  
 Temporäre Objekte werden erstellt, wenn `FromHandle` ein Handle übergeben wird, das noch ein Wrapperobjekt hat.  Diese temporäre Objekte werden von ihrem Handle getrennt gelöscht und durch die `DeleteTempMap`\-Funktionen.  Standardmäßig ruft [CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md) automatisch `DeleteTempMap` für jede Klasse, die temporäre Handlezuordnungen unterstützt.  Dies bedeutet, dass Sie nicht davon ausgehen können, dass ein Zeiger auf einen temporären Objekt hinter dem Punkt der Beendigung der Funktion gültig ist, in der der Zeiger abgerufen wurde.  
  
## Wrapper\-Objekte und mehrere Threads  
 werden temporäre und permanente Objekte pro Thread beibehalten.  Das bedeutet, dass ein Thread auf C\+\+\-Wrapperobjekte eines anderen Threads nicht zugreifen, unabhängig davon, ob er temporär oder permanent ist.  
  
 Damit diese Objekte von einem Thread zu einem anderen zu übergeben, senden Sie sie immer als ihr systemeigener Typ `HANDLE`.  Durch Übergeben des Wrapperobjekts eine C\+\+\-Headerdatei von einem Thread zu anderen verursacht oftmals zu unerwarteten Ergebnissen.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)