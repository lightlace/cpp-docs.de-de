---
title: 'TN001: Fensterklassenregistrierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4560905660ea80524c3e26bf14a803a2bc74344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn001-window-class-registration"></a>TN001: Fensterklassenregistrierung
In diesem Hinweis werden die MFC-Routinen, die die speziellen registrieren [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es von Microsoft Windows benötigt werden. Bestimmte `WNDCLASS` von MFC und Windows verwendeten Attribute werden erläutert.  
  
## <a name="the-problem"></a>Das Problem  
 Die Attribute einer [CWnd](../mfc/reference/cwnd-class.md) Objekt, z. B. ein `HWND` in Windows behandelt werden, werden an zwei Orten gespeichert: jedoch stattdessen das Fenster und die `WNDCLASS`. Der Name des der `WNDCLASS` wie z. B. allgemeine Erstellung Fensterfunktionen übergeben wird [CWnd:: Create](../mfc/reference/cwnd-class.md#create) und [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) in der `lpszClassName` Parameter.  
  
 Dies `WNDCLASS` muss über eines der vier Mittel registriert werden:  
  
-   Implizit mithilfe einer bereitgestellten MFC `WNDCLASS`.  
  
-   Implizit durch das Erstellen von Unterklassen eines Windows-Steuerelements (oder ein anderes Steuerelement).  
  
-   Explizit durch Aufrufen der MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) oder [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
-   Explizit durch Aufrufen der Windows-Routine [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586).  
  
## <a name="wndclass-fields"></a>Z. B. WNDCLASS Felder  
 Die `WNDCLASS` Struktur besteht aus verschiedenen Feldern, die eine Fensterklasse beschreiben. In der folgenden Tabelle werden die Felder und gibt an, wie sie in einer MFC_Anwendung verwendet werden:  
  
|Feld|Beschreibung|  
|-----------|-----------------|  
|`lpfnWndProc`|Fensterprozedur, muss ein`AfxWndProc`|  
|`cbClsExtra`|nicht verwendet (sollte Null sein)|  
|`cbWndExtra`|nicht verwendet (sollte Null sein)|  
|`hInstance`|gefüllt mit [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|  
|`hIcon`|Symbol für Rahmenfenster, finden Sie weiter unten|  
|`hCursor`|Cursor, wenn die Maus über Fenster ist, finden Sie weiter unten|  
|`hbrBackground`|die Hintergrundfarbe (siehe unten)|  
|`lpszMenuName`|nicht verwendet (sollte NULL sein)|  
|`lpszClassName`|Klassenname, finden Sie weiter unten|  
  
## <a name="provided-wndclasses"></a>WNDCLASSes bereitgestellt  
 Frühere Versionen von MFC (vor MFC 4.0) verfügten über mehrere vordefinierte Fensterklassen. Diese Klassen werden nicht mehr standardmäßig bereitgestellt. Anwendungen sollten verwenden `AfxRegisterWndClass` mit den entsprechenden Parametern.  
  
 Wenn die Anwendung auf eine Ressource mit der angegebenen Ressourcen-ID (z. B. AFX_IDI_STD_FRAME) bereitstellt, verwendet MFC diese Ressource. Andernfalls wird die Standardressource verwendet. Für das Symbol das Anwendungssymbol für standard wird verwendet, und für den Cursor der Standardpfeilcursor verwendet wird.  
  
 Zwei Symbole unterstützt MDI-Anwendungen mit einzelnen Dokumenttypen: ein Symbol für die Hauptassembly der Anwendung, die andere Symbol für Elementsymbol Dokument/MDIChild Windows. Für mehrfache Dokumentvorlagen mit unterschiedlichen Symbolen, müssen Sie zusätzliche registrieren `WNDCLASS`es, oder verwenden Sie die [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Funktion.  
  
 `CFrameWnd::LoadFrame`registriert eine `WNDCLASS` mithilfe der Symbol-ID, die Sie als ersten Parameter und die folgenden standard-Attribute angeben:  
  
-   -Klassenstil: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;  
  
-   Symbol "AFX_IDI_STD_FRAME"  
  
-   -Pfeilcursor  
  
-   COLOR_WINDOW Hintergrundfarbe  
  
 Die Werte für die Hintergrundfarbe und der Cursor für die [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) werden nicht verwendet, seit der Clientbereich der `CMDIFrameWnd` vollständig berücksichtigt die **MDICLIENT** Fenster. Microsoft ist nicht empfehlen Unterklassen der **MDICLIENT** Fenster so verwenden Sie die Standardfarben und Cursortypen, sofern möglich.  
  
## <a name="subclassing-and-superclassing-controls"></a>Erstellung von Unterklassen von und Erstellen von übergeordneten Klassen-Steuerelemente  
 Wenn Sie eine Unterklasse von oder die übergeordnete Klasse eine Windows-Steuerelement (z. B. [CButton](../mfc/reference/cbutton-class.md)) und dann automatisch eine Klasse ruft der `WNDCLASS` Attribute, die in der Windows-Implementierung dieses Steuerelements bereitgestellt.  
  
## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass-Funktion  
 MFC enthält eine Hilfsfunktion für eine Fensterklasse registriert. Bei einem gegebenen Satz von Attributen (Fensterklassenstil, Cursor, Hintergrundpinsel und Symbol "), wird ein synthetischer Name generiert, und die resultierende Fensterklasse registriert ist. Ein auf ein Objekt angewendeter  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```  
  
 Diese Funktion gibt eine temporäre Zeichenfolge des Klassennamens generierten registrierten Fenster zurück. Weitere Informationen zu dieser Funktion finden Sie unter [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).  
  
 Die zurückgegebene Zeichenfolge ist ein temporärer Zeiger auf eine statische Zeichenfolgenpuffer. Es ist zulässig, bis zum nächsten Aufruf von `AfxRegisterWndClass`. Wenn Sie diese Zeichenfolge um beibehalten möchten, speichern Sie es in einem [CString](../atl-mfc-shared/using-cstring.md) Variablen, wie in diesem Beispiel:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);

...  
```  
  
 `AfxRegisterWndClass`Löst ein [CResourceException](../mfc/reference/cresourceexception-class.md) Wenn Fensterklasse fehlgeschlagen ist (entweder aufgrund ungültiger Parameter oder nicht genügend Arbeitsspeicher für Windows) zu registrieren.  
  
## <a name="the-registerclass-and-afxregisterclass-functions"></a>Die RegisterClass und AfxRegisterClass-Funktionen  
 Wenn Sie möchten nichts ausgefeilter als `AfxRegisterWndClass` bereitstellt, können Sie die Windows-API Aufrufen `RegisterClass` oder die MFC-Funktion `AfxRegisterClass`. Die `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` Funktionen nehmen eine `lpszClassName` Zeichenfolgennamen für die Fensterklasse als erster Parameter. Sie können alle registrierten Klasse Fenstername, unabhängig von der Methode, die Sie verwendet, um ihn zu registrieren.  
  
 Es ist wichtig, verwenden Sie `AfxRegisterClass` (oder `AfxRegisterWndClass`) in einer Win32-DLL. Win32 wird nicht automatisch aufgehoben Klassen, die von einer DLL registriert werden, damit Sie Klassen explizit Registrierung müssen, wenn die DLL beendet wird. Mithilfe von `AfxRegisterClass` anstelle von `RegisterClass` Dies erfolgt automatisch für Sie. `AfxRegisterClass`verwaltet eine Liste der eindeutigen Klassen registriert, indem Sie die DLL und wird automatisch deren Registrierung aufzuheben, wenn die DLL beendet wird. Bei Verwendung von `RegisterClass` in eine DLL dann, müssen Sie sicherstellen, dass alle Klassen aufgehoben werden, wenn die DLL beendet wird (in Ihrem [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) Funktion). Bei unterlassen kann dazu führen, dass `RegisterClass` zu unerwarteten Systemfehlern, wenn eine andere Clientanwendung versucht, die DLL zu verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

