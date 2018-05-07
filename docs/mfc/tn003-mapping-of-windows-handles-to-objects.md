---
title: 'TN003: Zuordnen von Fensterhandles zu Objekten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mapping
dev_langs:
- C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc8658868c36008c5ed6b9db9747eb63ae37e4d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Zuordnen von Fensterhandles zu Objekten
In diesem Hinweis werden die MFC-Bibliothek Routinen, die Unterstützung für die Zuordnung von Windows-Objekt-Handles zu C++-Objekte.  
  
## <a name="the-problem"></a>Das Problem  
 Windows-Objekte werden in der Regel von verschiedenen dargestellt [BEHANDELN](http://msdn.microsoft.com/library/windows/desktop/aa383751) Windows Objekthandles mit C++-Objekte zum Umschließen von Objekten der MFC-Klassen. Das Handle wrapping Funktionen der MFC-Klassenbibliothek können Sie das C++-Objekt zu suchen, das das Windows-Objekt umschließt, das ein bestimmtes Handle verfügt. Allerdings manchmal ein Objekt kein C++-Wrapperobjekt und zu diesen Zeitpunkten erstellt das System ein temporäres Objekt, das als C++-Wrapper fungiert.  
  
 Die Windows-Objekte, die Handlezuordnungen verwenden, sind wie folgt:  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md) und `CWnd`-abgeleitete Klassen)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md) und `CDC`-abgeleitete Klassen)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))  
  
-   SOCKET ([CSocket](../mfc/reference/csocket-class.md))  
  
 Wenn ein Handle für jede dieser Objekte, finden Sie die MFC-Objekt, das das Handle durch Aufrufen der statischen Methode umschließt `FromHandle`. Angenommen, einen HWND bezeichnet `hWnd`, die folgende Zeile zurück, einen Zeiger auf die `CWnd` , umschließt `hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Wenn `hWnd` verfügt nicht über einen bestimmten Wrapperobjekt, ein temporäres `CWnd` erstellt, um umschließen `hWnd`. Dadurch möglich, ein gültiges C++-Objekt aus beliebiges Handle zu erhalten.  
  
 Nachdem Sie ein Wrapperobjekt haben, können Sie dessen Handle aus einer Variablen öffentlichen Member von der Wrapperklasse abrufen. Im Fall von einem `CWnd`, `m_hWnd` das HWND für dieses Objekt enthält.  
  
## <a name="attaching-handles-to-mfc-objects"></a>Anfügen von Handles zu MFC-Objekten  
 Eine neu erstellte Handle-Wrapperobjekt und ein Handle, ein Windows-Objekt zugewiesen, können Sie die beiden durch Aufrufen von Zuordnen der `Attach` wie in diesem Beispiel funktionieren:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Dadurch wird einen Eintrag in der permanenten Zuordnung zuordnen `myWnd` und `hWnd`. Aufrufen von `CWnd::FromHandle(hWnd)` wird nun einen Zeiger auf zurückgeben `myWnd`. Wenn `myWnd` wird gelöscht, der Destruktor automatisch zerstört `hWnd` durch Aufruf der Windows [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) Funktion. Wenn dies nicht erwünscht ist, `hWnd` muss getrennt von `myWnd` vor `myWnd` zerstört wird (normalerweise beim Verlassen des Bereichs an dem `myWnd` definiert wurde). Die `Detach` Methode geschieht.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Weitere Informationen zu temporären Objekte  
 Temporäre Objekte werden erstellt, wenn `FromHandle` erhält ein Handle, das nicht bereits ein Wrapperobjekt verfügt. Diese temporären Objekte aus ihren Handle getrennt oder gelöscht, indem die `DeleteTempMap` Funktionen. Standardmäßig [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) ruft automatisch `DeleteTempMap` für jede Klasse, die temporäre Handlezuordnungen unterstützt. Dies bedeutet, dass Sie nicht davon ausgehen können, dass ein Zeiger auf ein temporäres Objekt ist am Punkt des Beenden von der Funktion gültig, in dem der Zeiger abgerufen wurde.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Wrapper-Objekte und mehrere Threads  
 Temporäre und permanente Objekte werden in Abständen threadspezifisches beibehalten. Ein Thread kann nicht, also ein anderer Thread C++ Wrapper-Objekte, unabhängig davon, ob es temporär oder dauerhaft zugreifen.  
  
 Um diese Objekte von einem Thread zu einem anderen zu übergeben, immer senden als ihre systemeigenen `HANDLE` Typ. Übergeben ein C++-Wrapper-Objekt von einem Thread zu einem anderen wird häufig zu unerwarteten Ergebnissen führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

