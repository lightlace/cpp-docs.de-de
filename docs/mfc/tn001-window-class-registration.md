---
title: 'TN001: Fensterklassenregistrierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6818cb66f7ae9498ca13ac895a84e3b22c0c482
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426093"
---
# <a name="tn001-window-class-registration"></a>TN001: Fensterklassenregistrierung

In diesem Hinweis wird beschrieben, die MFC-Routinen, die die speziellen registrieren [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)es von Microsoft Windows benötigt werden. Bestimmte `WNDCLASS` Attribute, die von MFC und Windows verwendet werden beschrieben.

## <a name="the-problem"></a>Das Problem

Die Attribute des eine [CWnd](../mfc/reference/cwnd-class.md) Objekt, z. B. eine `HWND` in Windows verarbeitet, werden an zwei Orten gespeichert: das Window-Objekt und die `WNDCLASS`. Der Name des der `WNDCLASS` wird z. B. allgemeine-Fensterfunktionen für die Erstellung übergeben [CWnd:: Create](../mfc/reference/cwnd-class.md#create) und [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) in die *"lpszclassname"* Parameter.

Dies `WNDCLASS` muss über eine der vier Plattformen registriert werden:

- Implizit mithilfe einer bereitgestellten MFC `WNDCLASS`.

- Implizit durch das Erstellen von Unterklassen für ein Windows-Steuerelement (oder ein anderes Steuerelement verwenden).

- Explizit durch Aufrufen der MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) oder [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).

- Explizit durch Aufrufen der Windows-Routine ["registerClass"](https://msdn.microsoft.com/library/windows/desktop/ms633586).

## <a name="wndclass-fields"></a>WNDCLASS-Felder

Die `WNDCLASS` Struktur besteht aus verschiedenen Feldern, die eine Fensterklasse zu beschreiben. Die folgende Tabelle zeigt die Felder und gibt an, wie sie in einer MFC-Anwendung verwendet werden:

|Feld|Beschreibung|
|-----------|-----------------|
|*lpfnWndProc*|die Fensterprozedur, muss ein `AfxWndProc`|
|*WNDCLAS*|nicht verwendet (sollte Null sein)|
|*cbWndExtra*|nicht verwendet (sollte Null sein)|
|*hInstance*|automatisch mit gefüllt [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|
|*hIcon*|Symbol für das Rahmenfenster, finden Sie weiter unten|
|*hCursor*|Cursor für Fenster, wenn Mauszeiger befindet, finden Sie weiter unten|
|*hbrBackground*|Farbe des Hintergrunds, finden Sie weiter unten|
|*lpszMenuName*|nicht verwendet (sollte NULL sein)|
|*"lpszclassname"*|Klassenname, finden Sie weiter unten|

## <a name="provided-wndclasses"></a>WNDCLASSes bereitgestellt

Früheren Versionen von Quickinfos (MFC 4.0), die mehrere vordefinierte Klassen bereitgestellt. Diese Klassen werden nicht mehr standardmäßig bereitgestellt. Anwendungen sollten verwenden `AfxRegisterWndClass` mit den entsprechenden Parametern.

Wenn die Anwendung auf eine Ressource mit der angegebenen Ressourcen-ID (z. B. AFX_IDI_STD_FRAME) bereitstellt, verwendet MFC diese Ressource. Andernfalls wird die Standardressource verwendet. Für das Symbol das Symbol "standardanwendung" wird verwendet, und für den Cursor, der Standardpfeilcursor verwendet wird.

Zwei Symbole unterstützt MDI-Anwendungen mit einzelnen Dokumenttypen: ein Symbol für die hauptanwendung, das andere Symbol für iconic-Dokument/MDIChild Windows. Für mehrere Dokumenttypen mit unterschiedlichen Symbolen, müssen Sie zusätzliche registrieren `WNDCLASS`es oder verwenden Sie die [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Funktion.

`CFrameWnd::LoadFrame` registriert eine `WNDCLASS` mithilfe der Symbol-ID, die Sie als ersten Parameter und die folgenden standard-Attribute angeben:

- -Klassenstil: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- Symbol "AFX_IDI_STD_FRAME"

- Cursor mit Pfeil

- COLOR_WINDOW Hintergrundfarbe

Die Werte für die Hintergrundfarbe und der Cursor für die [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) werden nicht verwendet werden, da das den Clientbereich des der `CMDIFrameWnd` vollständig berücksichtigt die **MDICLIENT** Fenster. Microsoft ist nicht empfiehlt, Unterklassen der **MDICLIENT** Fenster so verwenden Sie die Standardfarben und Cursortypen, sofern möglich.

## <a name="subclassing-and-superclassing-controls"></a>Erstellen von Unterklassen und Erstellung einer übergeordneten Klasse-Steuerelemente

Wenn Sie eine Unterklasse von oder der übergeordneten Klasse eine Windows-Steuerelement (z. B. [CButton](../mfc/reference/cbutton-class.md)) daraufhin die Klasse automatisch die `WNDCLASS` Attribute, die in der Windows-Implementierung des Steuerelements bereitgestellt.

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass-Funktion

MFC enthält eine Hilfsfunktion zum eine Fensterklasse registrieren. Wenn einen Satz von Attributen (Fensterklassenstil, Cursor, Hintergrundpinsel und Symbol "), wird ein synthetischer Name generiert, und die resultierende Fensterklasse registriert ist. Ein auf ein Objekt angewendeter

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Diese Funktion gibt eine temporäre Zeichenfolge der Name des generierten registrierten-Klasse. Weitere Informationen zu dieser Funktion finden Sie unter [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Die zurückgegebene Zeichenfolge ist ein temporärer Zeiger auf eine statische Zeichenfolge-Puffer. Es ist gültig, bis der nächste Aufruf von `AfxRegisterWndClass`. Wenn Sie diese Zeichenfolge zu behalten möchten, speichern Sie sie in einem [CString](../atl-mfc-shared/using-cstring.md) Variablen, wie im folgenden Beispiel:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` löst eine [CResourceException](../mfc/reference/cresourceexception-class.md) Wenn Window-Klasse, die Fehler aufgetreten ist (entweder aufgrund ungültiger Parameter oder nicht genügend Arbeitsspeicher für Windows) zu registrieren.

## <a name="the-registerclass-and-afxregisterclass-functions"></a>Die "registerClass" und die AfxRegisterClass-Funktionen

Wenn Sie möchten etwas komplexer als `AfxRegisterWndClass` bereitstellt, können Sie die Windows-API Aufrufen `RegisterClass` oder die MFC-Funktion `AfxRegisterClass`. Die `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` Funktionen akzeptieren eine *"lpszclassname"* Zeichenfolgennamen für Window-Klasse als ersten Parameter. Sie können alle registrierten Fensterklassenname, unabhängig von der Methode verwenden, die Sie verwendet, um ihn zu registrieren.

Es ist wichtig, verwenden Sie `AfxRegisterClass` (oder `AfxRegisterWndClass`) in einer DLL auf Win32. Win32 ist nicht automatisch abmelden Klassen, die durch eine DLL registriert werden, damit Sie Klassen explizit aufheben müssen, wenn die DLL beendet wird. Mithilfe von `AfxRegisterClass` anstelle von `RegisterClass` Dies wird automatisch für Sie erledigt. `AfxRegisterClass` verwaltet eine Liste von eindeutigen Klassen von der DLL registriert und wird automatisch deren Registrierung aufzuheben, wenn die DLL beendet wird. Bei Verwendung von `RegisterClass` in eine DLL dann, müssen Sie sicherstellen, dass alle Klassen nicht registriert sind, wenn die DLL beendet wird (in Ihrem [DllMain](/windows/desktop/Dlls/dllmain) Funktion). Bei unterlassen kann dazu führen, dass `RegisterClass` zu unerwarteten Systemfehlern, wenn eine andere Clientanwendung versucht, die DLL zu verwenden.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

