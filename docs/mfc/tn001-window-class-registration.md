---
title: 'TN001: Fenster Klassen Registrierung'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: 95e35ddd6f55c955bc2adb7b4db2460ae84a6dc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513549"
---
# <a name="tn001-window-class-registration"></a>TN001: Fenster Klassen Registrierung

In diesem Hinweis werden die MFC-Routinen beschrieben, die die für Microsoft Windows benötigten speziellen [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)-es registrieren. Bestimmte `WNDCLASS` von MFC und Windows verwendete Attribute werden erörtert.

## <a name="the-problem"></a>Das Problem

Die Attribute eines [CWnd](../mfc/reference/cwnd-class.md) -Objekts, wie ein `HWND` -Handle in Windows, werden an zwei Stellen gespeichert: dem Window-Objekt `WNDCLASS`und dem. `WNDCLASS` Der Name des wird an allgemeine Fenster Erstellungs Funktionen wie [CWnd:: Create](../mfc/reference/cwnd-class.md#create) und [CFrameWnd:: Create](../mfc/reference/cframewnd-class.md#create) im *lpszClassName* -Parameter übergeben.

Dies `WNDCLASS` muss mit einer von vier Methoden registriert werden:

- Implizit mithilfe eines bereitgestellten `WNDCLASS`MFC.

- Implizit durch die Unterklassen eines Windows-Steuer Elements (oder eines anderen Steuer Elements).

- Explizites Aufrufen von MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) oder [afxregisterclass](../mfc/reference/application-information-and-management.md#afxregisterclass).

- Explizit durch Aufrufen der Windows-Routine " [registerClass](/windows/win32/api/winuser/nf-winuser-registerclassw)".

## <a name="wndclass-fields"></a>WNDCLASS-Felder

Die `WNDCLASS` Struktur besteht aus verschiedenen Feldern, die eine Fenster Klasse beschreiben. In der folgenden Tabelle sind die Felder aufgeführt, und es wird angegeben, wie Sie in einer MFC-Anwendung verwendet werden:

|Feld|Beschreibung|
|-----------|-----------------|
|*lpfnWndProc*|Fenster proc, muss ein`AfxWndProc`|
|*cbClsExtra*|nicht verwendet (sollte NULL sein)|
|*cbWndExtra*|nicht verwendet (sollte NULL sein)|
|*hInstance*|automatisch mit [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle) gefüllt|
|*hIcon*|Symbol für Rahmen Fenster, siehe unten|
|*hcursor*|Cursor, wenn sich die Maus über dem Fenster befindet, siehe unten|
|*hbrBackground*|Hintergrundfarbe, siehe unten|
|*lpszMenuName*|nicht verwendet (sollte NULL sein)|
|*lpszClassName*|Klassenname, siehe unten|

## <a name="provided-wndclasses"></a>Bereitgestellte wndclasses

In früheren Versionen von MFC (vor MFC 4,0) wurden mehrere vordefinierte Fenster Klassen bereitgestellt. Diese Fenster Klassen werden nicht mehr standardmäßig bereitgestellt. Anwendungen sollten mit `AfxRegisterWndClass` den entsprechenden Parametern verwenden.

Wenn die Anwendung eine Ressource mit der angegebenen Ressourcen-ID (z. b. AFX_IDI_STD_FRAME) bereitstellt, verwendet MFC diese Ressource. Andernfalls wird die Standardressource verwendet. Für das Symbol wird das Symbol Standardanwendung verwendet, und für den Cursor wird der Standardpfeil Cursor verwendet.

Zwei Symbole unterstützen MDI-Anwendungen mit einzelnen Dokumenttypen: ein Symbol für die Hauptanwendung, das andere Symbol für das Symbol "Icon Document/MDIChild". Bei mehreren Dokumenttypen mit unterschiedlichen Symbolen müssen Sie zusätzliche `WNDCLASS`es registrieren oder die [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) -Funktion verwenden.

`CFrameWnd::LoadFrame`registriert eine `WNDCLASS` mit der Symbol-ID, die Sie als ersten Parameter und die folgenden Standard Attribute angeben:

- Klassen Stil: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- Symbol AFX_IDI_STD_FRAME

- Pfeilcursor

- COLOR_WINDOW Hintergrundfarbe

Die Werte für Hintergrundfarbe und Cursor für [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) werden nicht verwendet, da der Client Bereich von `CMDIFrameWnd` vollständig durch das **MdiClient** -Fenster abgedeckt wird. Microsoft ermutigt nicht, das **MdiClient** -Fenster zu Unterklassen zu verwenden, daher sollten Sie möglichst die Standardfarben und-Cursor Typen verwenden.

## <a name="subclassing-and-superclassing-controls"></a>Unterklassen-und superclassingsteuerelemente

Wenn Sie ein Windows-Steuerelement (z. b. [CButton](../mfc/reference/cbutton-class.md)) Unterklasse oder eine übergeordnete Klasse verwenden `WNDCLASS` , ruft die Klasse automatisch die Attribute ab, die in der Windows-Implementierung dieses Steuer Elements bereitgestellt werden

## <a name="the-afxregisterwndclass-function"></a>Die AfxRegisterWndClass-Funktion

MFC stellt eine Hilfsfunktion zum Registrieren einer Fenster Klasse bereit. Wenn ein Satz von Attributen (Fenster Klassen Stil, Cursor, Hintergrund Pinsel und Symbol) angegeben wird, wird ein synthetischer Name generiert, und die resultierende Fenster Klasse wird registriert. Ein auf ein Objekt angewendeter

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Diese Funktion gibt eine temporäre Zeichenfolge des generierten registrierten Fenster Klassen namens zurück. Weitere Informationen zu dieser Funktion finden Sie unter [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Die zurückgegebene Zeichenfolge ist ein temporärer Zeiger auf einen statischen Zeichen folgen Puffer. Sie ist bis zum nächsten `AfxRegisterWndClass`-Vorgang gültig. Wenn Sie diese Zeichenfolge beibehalten möchten, speichern Sie Sie in einer [CString](../atl-mfc-shared/using-cstring.md) -Variablen, wie in diesem Beispiel:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass`löst eine " [kresourceexception](../mfc/reference/cresourceexception-class.md) " aus, wenn die Fenster Klasse nicht registriert werden konnte (entweder aufgrund fehlerhafter Parameter oder aus Windows-Speicher).

## <a name="the-registerclass-and-afxregisterclass-functions"></a>Die Funktionen "registerClass" und "afxregisterclass"

Wenn Sie etwas anspruchsvoller als `AfxRegisterWndClass` das bereitstellen möchten, können Sie die Windows-API `RegisterClass` oder die MFC-Funktion `AfxRegisterClass`verwenden. Die `CWnd` [CFrameWnd](../mfc/reference/cframewnd-class.md) -und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` -Funktionen akzeptieren einen *lpszClassName* -Zeichen folgen Namen für die Fenster Klasse als ersten Parameter. Sie können einen beliebigen registrierten Fenster Klassennamen verwenden, unabhängig von der Methode, die Sie zur Registrierung verwendet haben.

Es ist wichtig, ( `AfxRegisterClass` oder `AfxRegisterWndClass`) in einer DLL auf Win32 zu verwenden. Win32 führt keine automatische Aufhebung der Registrierung von Klassen aus, die von einer DLL registriert wurden, sodass Sie die Registrierung von Klassen explizit aufheben müssen, wenn die dll beendet wird. Wenn Sie `AfxRegisterClass` anstelle von `RegisterClass` verwenden, wird dies automatisch für Sie erledigt. `AfxRegisterClass`verwaltet eine Liste eindeutiger Klassen, die von der dll registriert wurden, und gibt die Registrierung automatisch aus, wenn die dll beendet wird. Wenn Sie in `RegisterClass` einer DLL verwenden, müssen Sie sicherstellen, dass beim Beenden der dll (in der [DllMain](/windows/win32/Dlls/dllmain) -Funktion) die Registrierung aller Klassen aufgehoben wird. Wenn dies nicht möglich ist, `RegisterClass` kann dies zu einem unerwarteten Fehler führen, wenn eine andere Client Anwendung versucht, die dll zu verwenden.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
