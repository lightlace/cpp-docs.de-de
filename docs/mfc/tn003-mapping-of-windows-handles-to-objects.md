---
title: 'TN003: Zuordnen von Windows-Fensterhandles zu Objekten | Microsoft-Dokumentation'
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
ms.openlocfilehash: b022c4c42a7373f9bfc23c1fff5be2c1317709de
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692447"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Zuordnen von Fensterhandles zu Objekten
In diesem Hinweis wird beschrieben, die MFC-Bibliothek Objekt Routinen, die Unterstützung für die Zuordnung von Windows-Handles für C++-Objekte.  
  
## <a name="the-problem"></a>Das Problem  
 Windows-Objekte werden in der Regel von verschiedenen dargestellt [BEHANDELN](/windows/desktop/WinProg/windows-data-types) Objekthandles für Windows mit C++-Objekte zum Umschließen von Objekten der MFC-Klassen. Das Handle Wrapperfunktionen der MFC-Klassenbibliothek können Sie das C++-Objekt zu suchen, das das Windows-Objekt umschlossen wird, das ein bestimmtes Handle ist. Allerdings manchmal ein Objekt kein C++-Wrapper-Objekt, und zu diesen Zeitpunkten erstellt das System ein temporäres Objekt, das als C++-Wrapper fungiert.  
  
 Die Windows-Objekte, die Handle-Karten zu verwenden sind wie folgt:  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md) und `CWnd`-abgeleiteten Klassen)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md) und `CDC`-abgeleiteten Klassen)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))  
  
-   SOCKET ([CSocket](../mfc/reference/csocket-class.md))  
  
 Ein Handle an eine der folgenden Objekte übergeben, finden Sie die MFC-Objekt, das das Handle durch Aufrufen der statischen Methode umschließt `FromHandle`. Angenommen, ein HWND namens *hWnd*, die folgende Zeile gibt einen Zeiger auf die `CWnd` , umschließt *hWnd*:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Wenn *hWnd* verfügt nicht über einen bestimmten Wrapperobjekt, ein temporäres `CWnd` wird erstellt, um umschließen *hWnd*. Dadurch wird es möglich, ein gültiges C++-Objekt aus beliebiges Handle zu erhalten.  
  
 Nachdem Sie ein Wrapperobjekt haben, können Sie das Handle von einer öffentlichen Membervariablen der Wrapperklasse abrufen. Im Fall von einem `CWnd`, *M_hWnd* das HWND für dieses Objekt enthält.  
  
## <a name="attaching-handles-to-mfc-objects"></a>Anfügen von Handles an MFC-Objekte  
 Wenn eine neu erstellte Handle-Wrapper-Objekt und einem Handle auf ein Windows-Objekt, können Sie die beiden durch Aufrufen von Zuordnen der `Attach` funktionieren, wie im folgenden Beispiel:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Dadurch wird einen Eintrag in das Zuordnen der permanenten Zuordnung *MyWnd* und *hWnd*. Aufrufen von `CWnd::FromHandle(hWnd)` gibt nun einen Zeiger auf *MyWnd*. Wenn *MyWnd* wird gelöscht, werden automatisch der Destruktor zerstört *hWnd* durch Aufrufen der Windows [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow) Funktion. Wenn dies nicht erwünscht ist, *hWnd* muss getrennt von *MyWnd* vor *MyWnd* zerstört wird (normalerweise beim Verlassen des Bereichs mit der *MyWnd*definiert wurde). Die `Detach` Methode hierfür.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Weitere Informationen zu temporären Objekte  
 Temporäre Objekte werden erstellt, wenn `FromHandle` erhält ein Handle, das nicht bereits über ein Wrapperobjekt verfügt. Diese temporären Objekte aus ihren Handle getrennt oder gelöscht, indem die `DeleteTempMap` Funktionen. Standardmäßig [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) ruft automatisch `DeleteTempMap` für jede Klasse, die temporäre Handlezuordnungen unterstützt. Dies bedeutet, dass Sie können nicht davon ausgehen, dass ein Zeiger auf ein temporäres Objekt ist am Punkt der Beendigung der Funktion gültig, in dem der Zeiger abgerufen wurde.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Wrapper-Objekte und mehreren Threads  
 Temporäre und permanente Objekte auf einer pro-Thread-Basis verwaltet werden. Ein Thread kann nicht, also einem anderen Thread C++-Wrapper-Objekte, unabhängig davon, ob es sich um temporär oder permanent ist zugreifen.  
  
 Um diese Objekte von einem Thread in einen anderen übergeben möchten, immer senden diese als ihre Native `HANDLE` Typ. Übergeben ein C++-Wrapper-Objekt von einem Thread in einen anderen wird oftmals zu unerwarteten Ergebnissen führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

