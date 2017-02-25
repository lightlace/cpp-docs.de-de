---
title: "TN001: Fensterklassenregistrierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterClass-Funktion"
  - "TN001"
  - "WNDCLASS"
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# TN001: Fensterklassenregistrierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die MFC\-Routinen, die eine spezielle [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) registrieren es, das von Microsoft Windows erforderlich ist.  Bestimmte Attribute `WNDCLASS`, die von MFC verwendet werden und Windows werden erläutert.  
  
## Das Problem  
 Die Attribute von [CWnd](../mfc/reference/cwnd-class.md)\-Objekt, wie `HWND` ein Handle in Windows, werden gespeichert an zwei Stellen ein: dem Window\-Objekt und `WNDCLASS`.  Der Name `WNDCLASS` wird den allgemeinen Fenstererstellungsfunktionen wie [CWnd::Create](../Topic/CWnd::Create.md) und [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) im `lpszClassName`\-Parameter übergeben.  
  
 Dieser `WNDCLASS` muss durch eines von vier Mittel registriert werden:  
  
-   Implizit mit MFC bereitgestellten `WNDCLASS`.  
  
-   Implizit durch das Erstellen von Unterklassen von einem Windows\-Steuerelements \(oder eines beliebigen anderen Steuerelements\).  
  
-   Explizit durch Aufrufen des MFC\- [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) oder [AfxRegisterClass](../Topic/AfxRegisterClass.md).  
  
-   Explizit durch Aufrufen der Windows\-Routine [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586).  
  
## WNDCLASS\-Felder  
 Die `WNDCLASS`\-Struktur besteht aus verschiedenen Feldern, die eine Fensterklasse beschreiben.  In der folgenden Tabelle sind die Felder an und gibt an, wie sie in einer MFC\-Anwendung verwendet werden:  
  
|Feld|**Beschreibung**|  
|----------|----------------------|  
|`lpfnWndProc`|Fensterprozedur, muss `AfxWndProc` sein|  
|`cbClsExtra`|nicht verwendet werden sollte \(null\)|  
|`cbWndExtra`|nicht verwendet werden sollte \(null\)|  
|`hInstance`|automatisch ausgefüllt mit [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|  
|`hIcon`|Symbol für Rahmenfenster, siehe unten|  
|`hCursor`|Cursor für, wenn die Maus über Fenster ist, finden unten|  
|`hbrBackground`|Hintergrundfarbe, siehe unten|  
|`lpszMenuName`|nicht verwendet \(sollte NULL sein\)|  
|`lpszClassName`|Klassenname, siehe unten|  
  
## Bereitgestelltes WNDCLASSes  
 Frühere Versionen von MFC \(vor MFC 4.0\), vorausgesetzt einige vordefinierte Fensterklassen.  Diese Fensterklassen werden nicht mehr standardmäßig bereitgestellt.  Anwendungen sollten `AfxRegisterWndClass` mit den entsprechenden Parametern verwenden.  
  
 Wenn die Anwendung eine Ressource mit der angegebenen Ressourcen\-ID \(beispielsweise, AFX\_IDI\_STD\_FRAME\) bereitstellt, verwendet MFC diese Ressource.  Andernfalls verwendet sie die Standardressource.  Für das Symbol wird das Standardanwendungssymbol verwendet, und für den Cursor, wird der Standardpfeil\-Cursor verwendet.  
  
 Zwei Symbole unterstützen MDI\-Anwendungen mit einzelnen Dokumenttypen: ein Symbol für die Hauptanwendung, das anderen Symbol für ikonenhaftes Dokument\/MDIChild\-Fenster.  Bei mehrfachen Dokumenttypen mit unterschiedlichen Symbolen, müssen Sie zusätzliche `WNDCLASS` es registrieren oder die [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)\-Funktion verwenden.  
  
 `CFrameWnd::LoadFrame` registriert `WNDCLASS` mithilfe der ID Symbol, die Sie als ersten Parameter und die folgenden Standard\-Attribute angeben:  
  
-   Klassenformat: CS\_DBLCLKS &#124; CS\_HREDRAW &#124; CS\_VREDRAW;  
  
-   Symbol AFX\_IDI\_STD\_FRAME  
  
-   Pfeil\-Cursor  
  
-   COLOR\_WINDOW\-Hintergrundfarbe  
  
 Die Werte für Hintergrundfarbe und der Cursor für [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) werden nicht verwendet, da der Clientbereich `CMDIFrameWnd` vollständig vom Fenster **MDICLIENT** abgedeckt wird.  Microsoft bestärkt nicht das Erstellen von Unterklassen von des Fensters **MDICLIENT** an, erstellen Sie die Standardfarben und die Cursor\-Typen, sofern möglich.  
  
## Erstellen von Unterklassen und Superclassing\-Kontrollen  
 Wenn Sie als oder, übergeordnete Klasse ein Windows\-Steuerelement \(beispielsweise [CButton](../mfc/reference/cbutton-class.md)\), dann wird automatisch Ihre Klasse die Attribute `WNDCLASS` ab, die in der Windows\-Implementierung dieses Steuerelements bereitgestellt werden.  
  
## Die AfxRegisterWndClass\-Funktion  
 MFC bietet eine Hilfsfunktion zum Registrieren einer Fensterklasse bereit.  Erstellen eines Satzes Attribute \(Fensterklassenformat, Cursor, Hintergrundpinsel und Symbol angegeben\), wird ein synthetischer Namen generiert, und die resultierende Fensterklasse wird registriert.  Beispiel:  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle, HCURSOR hCursor, HBRUSH hbrBackground, HICON hIcon);  
```  
  
 Diese Funktion gibt eine Zeichenfolge des temporären generierten registrierten Fensterklassennamens zurück.  Weitere Informationen über diese Funktion, finden Sie unter [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md).  
  
 Die zurückgegebene Zeichenfolge ist ein temporärer Zeiger mit einem statischen Zeichenfolgenpuffer.  Sie ist bis zum nächsten Aufruf von `AfxRegisterWndClass` gültig.  Wenn Sie diese Zeichenfolge zu speichern möchten, speichern Sie diese in einer [CString](../atl-mfc-shared/using-cstring.md)\-Variable, wie in diesem Beispiel:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);  
...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);  
...  
```  
  
 `AfxRegisterWndClass` löst [CResourceException](../mfc/reference/cresourceexception-class.md) aus, wenn die Fensterklasse registrieren konnte \(entweder aufgrund ungültiger Parameter oder aus Windows\-Arbeitsspeicher out\).  
  
## Die Funktionen RegisterClass und AfxRegisterClass  
 Wenn Sie alles ausführen, das als ausgereifter wird, das `AfxRegisterWndClass` bereitstellt, können Sie die Windows\-API `RegisterClass` oder die MFC\-Funktion `AfxRegisterClass` aufrufen.  `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create`\-Funktionen akzeptieren einen `lpszClassName` Zeichenfolgennamens der Fensterklasse als ersten Parameter.  Sie können einen registrierten Fensterklassennamen, unabhängig von der Methode, die Sie verwendet haben, um diese zu registrieren.  
  
 Es ist wichtig, `AfxRegisterClass` \(oder `AfxRegisterWndClass`\) in einer DLL auf Win32 zu verwenden.  Win32 jedoch nicht automatisch die Klassen, die eine DLL registrieren werden, müssen Sie die Registrierung explizit Klassen, wenn die DLL beendet wird.  Indem `AfxRegisterClass` statt `RegisterClass` verwendet, wird dieses automatisch für Sie behandelt.  `AfxRegisterClass` verwaltet eine Liste durch eindeutige Klassen, die von der DLL registriert werden und automatisch Registrierung sie, wenn die DLL beendet wird.  Wenn Sie `RegisterClass` in einer DLL verwenden, müssen Sie sicherstellen, dass alle Klassen nicht registriert sind, wenn die DLL beendet wird \(in der [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)\-Funktion\).  Nichtbeachten gehen möglicherweise `RegisterClass`, unerwartet fehlschlagen, wenn eine andere Clientanwendung versucht, die DLL zu verwenden.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)