---
title: 'TN003: Zuordnung von Windows-Handles zu Objekten'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: 45492963e1b686e03eb59c320fdc3d52d1534f7d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513536"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Zuordnung von Windows-Handles zu Objekten

Dieser Hinweis beschreibt die MFC-Routinen, die die Zuordnung von Windows C++ -Objekt Handles zu Objekten unterstützen.

## <a name="the-problem"></a>Das Problem

Windows-Objekte werden in der Regel durch verschiedene [handle](/windows/win32/WinProg/windows-data-types) -Objekte dargestellt. die MFC- C++ Klassen wrappen Windows-Objekt Handles mit Objekten. Mit den Handle Wrapping Funktionen der MFC-Klassenbibliothek können Sie das C++ Objekt suchen, das das Windows-Objekt mit einem bestimmten handle umwickelt. Manchmal verfügt ein Objekt jedoch nicht über ein C++ Wrapper Objekt, und zu diesem Zeitpunkt erstellt das System ein temporäres Objekt, das als C++ Wrapper fungiert.

Die Windows-Objekte, die Handle-Zuordnungen verwenden, lauten wie folgt:

- HWND ([CWnd](../mfc/reference/cwnd-class.md) und `CWnd`von abgeleitete Klassen)

- HDC ([CDC](../mfc/reference/cdc-class.md) - `CDC`und-abgeleitete Klassen)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH (`CGdiObject`)

- HFONT (`CGdiObject`)

- HBITMAP (`CGdiObject`)

- HPALETTE (`CGdiObject`)

- HRGN (`CGdiObject`)

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- Socket ([CSocket](../mfc/reference/csocket-class.md))

Wenn einem dieser Objekte ein Handle zugewiesen ist, können Sie das MFC-Objekt suchen, das das Handle umschließt, indem Sie `FromHandle`die statische-Methode aufrufen. Beispielsweise gibt die folgende Zeile einen Zeiger auf den zurück, der `CWnd` das *HWND*umschließt, wenn ein HWND namens " *HWND*" angegeben wird:

```
CWnd::FromHandle(hWnd)
```

Wenn für *HWND* kein bestimmtes Wrapper Objekt vorhanden ist, wird ein `CWnd` temporäres erstellt, um das *HWND*zu umschließen. Dadurch ist es möglich, ein gültiges C++ -Objekt von einem beliebigen Handle abzurufen.

Nachdem Sie über ein Wrapper Objekt verfügen, können Sie das zugehörige Handle aus einer öffentlichen Member-Variablen der Wrapper Klasse abrufen. Im Fall von `CWnd`enthält *m_hWnd* das HWND für dieses Objekt.

## <a name="attaching-handles-to-mfc-objects"></a>Anfügen von Handles an MFC-Objekte

Bei einem neu erstellten handle-Wrapper-Objekt und einem Handle für ein Windows-Objekt können Sie die beiden zuordnen, indem `Attach` Sie die-Funktion wie im folgenden Beispiel aufrufen:

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

Dies führt zu einem Eintrag in der permanenten Zuordnung, der *mywnd* und *HWND*zuordnet. Beim `CWnd::FromHandle(hWnd)` Aufrufen von wird jetzt ein Zeiger auf *mywnd*zurückgegeben. Wenn *mywnd* gelöscht wird, wird *HWND* vom debugtor automatisch durch Aufrufen der Windows-Funktion " [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow) " zerstört. Wenn dies nicht erwünscht ist, muss *HWND* von *mywnd* getrennt werden, bevor *mywnd* zerstört wird (normalerweise wenn der Bereich, in dem *mywnd* definiert wurde, verlassen wird). Dies `Detach` erfolgt durch die-Methode.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>Weitere Informationen zu temporären Objekten

Temporäre Objekte werden immer dann `FromHandle` erstellt, wenn ein Handle vorhanden ist, das nicht bereits über ein Wrapper Objekt verfügt. Diese temporären Objekte werden von Ihrem handle getrennt und durch die `DeleteTempMap` Funktionen gelöscht. Standardmäßig ruft `DeleteTempMap` [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) automatisch für jede Klasse auf, die temporäre Handle-Zuordnungen unterstützt. Dies bedeutet, dass Sie nicht annehmen können, dass ein Zeiger auf ein temporäres Objekt über den Punkt der Beendigung der Funktion hinaus gültig ist, in der der Zeiger abgerufen wurde.

## <a name="wrapper-objects-and-multiple-threads"></a>Wrapper Objekte und mehrere Threads

Temporäre und permanente Objekte werden Thread bezogen verwaltet. Das heißt, ein Thread kann nicht auf die C++ Wrapper Objekte eines anderen Threads zugreifen, unabhängig davon, ob er temporär oder permanent ist.

Wenn Sie diese Objekte von einem Thread an einen anderen übergeben möchten, senden Sie Sie `HANDLE` immer als systemeigenen Typ. Wenn Sie C++ ein Wrapper Objekt von einem Thread an einen anderen übergeben, werden häufig unerwartete Ergebnisse verursacht.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
