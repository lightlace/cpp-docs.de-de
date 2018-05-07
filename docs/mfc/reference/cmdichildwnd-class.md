---
title: CMDIChildWnd-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e27551c04be5d6e985c6e7829f11f94d0aafeba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd-Klasse
Stellt die Funktionalität eines untergeordneten Windows-MDI-Fensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Erstellt ein `CMDIChildWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|Erstellt die zugeordneten untergeordnetes Windows-MDI-Fenster die `CMDIChildWnd` Objekt.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Gibt das übergeordnete MDI-Frame des MDI-Client-Fenster zurück.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Aktiviert diese untergeordneten MDI-Fensters.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Zerstört dieser untergeordneten MDI-Fensters.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Diese untergeordneten MDI-Fenster wird maximiert.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Wird diese untergeordnete MDI-Fenster aus maximierten oder minimierten Größe wiederhergestellt.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Legt die Handles für Menüs und Zugriffstasten Ressourcen fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein untergeordnetes MDI-Fenster sieht ähnlich wie einem typischen Rahmenfenster, mit dem Unterschied, dass die untergeordneten MDI-Fensters in ein MDI-Rahmenfenster und nicht auf dem Desktop angezeigt wird. Ein untergeordnetes MDI-Fenster verfügt nicht über eine eigene Menüleiste, aber stattdessen im Menü des MDI-Rahmenfensters freigibt. Das Framework ändert automatisch den Frame MDI-Menü zur Darstellung der derzeit aktiven untergeordneten MDI-Fensters.  
  
 Um eine nützliche untergeordnetes MDI-Fenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIChildWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Es gibt drei Möglichkeiten, ein untergeordnetes MDI-Fenster zu erstellen:  
  
-   Erstellen Sie direkt mit **erstellen**.  
  
-   Erstellen Sie direkt mit `LoadFrame`.  
  
-   Erstellen Sie sie indirekt über eine Dokumentvorlage.  
  
 Vor dem Aufruf **erstellen** oder `LoadFrame`, müssen Sie das Rahmenfenster Objekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf **erstellen** können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion die Stile-Symbol und die Klasse für den Frame festgelegt.  
  
 Verwenden der **erstellen** Memberfunktion, die Frame-Erstellungsparameter als sofortige Argumente zu übergeben.  
  
 `LoadFrame` erfordert weniger Argumente als **erstellen**, und ruft stattdessen die meisten die Standardwerte aus Ressourcen, einschließlich der Frame Beschriftung, Symbol Zugriffstastentabelle und im Menü ab. Um zugänglich `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Wenn ein `CMDIChildWnd` Objekt enthält, Ansichten und Dokumente, die indirekt durch das Framework statt direkt vom Programmierer erstellt werden. Die `CDocTemplate` Objekt organisiert, die Erstellung des Frames, die Erstellung der enthaltenden Ansichten und die Verbindung der Ansichten dem entsprechenden Dokument. Die Parameter von der `CDocTemplate` Konstruktor angeben der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird vom Framework verwendet, um neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe der neuen Datei Befehl oder MDI-Fenster neue) dynamisch zu erstellen.  
  
 Eine Rahmenfenster abgeleitete Klasse `CMDIChildWnd` muss deklariert werden, mit `DECLARE_DYNCREATE` in der Reihenfolge für die oben genannten `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 Die `CMDIChildWnd` Klasse erbt ein Großteil der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen, verweisen Sie auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Klasse Beschreibung. Die `CMDIChildWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   In Verbindung mit der `CMultiDocTemplate` -Klasse, die mehrere `CMDIChildWnd` Objekte aus der gleichen Dokumentvorlage gemeinsam das gleiche Menü, und speichern die Windows-Systemressourcen.  
  
-   Der derzeit aktive untergeordneten MDI-Fenster-Menü vollständig ersetzt der MDI-Rahmenfenster Menü und die Beschriftung der derzeit aktiven untergeordneten MDI-Fensters der MDI-Rahmenfenster Beschriftung hinzugefügt wird. Weitere Beispiele für MDI-untergeordneten Fensterfunktionen, die in Verbindung mit einem MDI-Rahmenfenster implementiert werden, finden Sie unter der `CMDIFrameWnd` -Klasse Beschreibung.  
  
 Verwenden Sie nicht den C++ **löschen** Operator, um ein Framefenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung der `PostNcDestroy` der C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Wenn der Benutzer das Rahmenfenster der Standardeinstellung schließt `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CMDIChildWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd  
 Der Aufruf zum Erstellen einer `CMDIChildWnd` Objekt.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** zum Erstellen des Fensters sichtbar.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIChildWnd::Create](#create).  
  
##  <a name="create"></a>  CMDIChildWnd::Create  
 Rufen Sie diese Memberfunktion zum Erstellen von ein untergeordnetes Windows-MDI-Fenster, und fügen Sie es auf die `CMDIChildWnd` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Namen die Windows-Klasse (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur). Der Klassenname kann einen beliebigen Namen registriert die [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion. Sollte **NULL** für einen Standard `CMDIChildWnd`.  
  
 `lpszWindowName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen darstellt. Als Text verwendet der Titelleiste.  
  
 `dwStyle`  
 Gibt das Zeitfenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute. Die **WS_CHILD** Stil ist erforderlich.  
  
 `rect`  
 Enthält die Größe und Position des Fensters. Die `rectDefault` Wert zulässt, geben Sie die Größe und Position des neuen Windows `CMDIChildWnd`.  
  
 `pParentWnd`  
 Gibt das Fenster übergeordnete an. Wenn **NULL**, Hauptfenster der Anwendung verwendet wird.  
  
 `pContext`  
 Gibt eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der derzeit aktive untergeordneten-MDI-Rahmenfenster kann die Beschriftung des übergeordneten Rahmenfensters bestimmen. Diese Funktion ist deaktiviert, durch das Deaktivieren der **FWS_ADDTOTITLE** Formatbit für die untergeordneten Rahmenfenster.  
  
 Das Framework ruft diese Memberfunktion als Antwort auf eine Benutzerbefehl aus, um ein untergeordnetes Fenster erstellt, und das Framework verwendet die `pContext` Parameter ordnungsgemäß das untergeordnete Fenster an die Anwendung eine Verbindung herstellen. Beim Aufruf **erstellen**, `pContext` kann **NULL**.  
  
### <a name="example"></a>Beispiel  
 Beispiel 1:  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Beispiel  
 Beispiel 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame  
 Rufen Sie diese Funktion, um den übergeordneten MDI-Frame zurück.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die MDI-Rahmenfenster übergeordneten.  
  
### <a name="remarks"></a>Hinweise  
 Der Frame, der zurückgegeben wird zwei übergeordneten daraus die `CMDIChildWnd` und ist das übergeordnete Element des Fensters des Typs **MDICLIENT** , verwaltet die `CMDIChildWnd` Objekt. Rufen Sie die [GetParent](../../mfc/reference/cwnd-class.md#getparent) Memberfunktion zurückzugebenden der `CMDIChildWnd` des Objekts sofort **MDICLIENT** übergeordneten als vorübergehende `CWnd` Zeiger.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster, unabhängig von der MDI-Rahmenfenster zu aktivieren.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Frame aktiv ist, wird das untergeordnete Fenster, das zuletzt aktiviert war ebenfalls aktiviert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster zu zerstören.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt den Titel des untergeordneten Fensters aus dem Rahmenfenster und das untergeordnete Fenster deaktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster zu maximieren.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes Fenster maximiert ist, ändert sich Windows um seinen Clientbereich, das den Clientbereich des Rahmenfensters ausfüllen zu machen. Windows platziert Steuerelementmenü für das untergeordnete Fenster in der Menüleiste des Frames, damit der Benutzer wiederherstellen kann, oder schließen Sie das untergeordnete Fenster und fügt den Titel des untergeordneten Fensters für den Titel der Frame-Fensters.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster aus maximierten oder minimierten Größe wiederherzustellen.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles  
 Legt die Handles für Menüs und Zugriffstasten Ressourcen fest.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Das Handle des eine Menüressource.  
  
 `hAccel`  
 Das Handle einer Zugriffstaste-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion wird vom Objekt Fenster untergeordnete MDI-Menü und Zugriffstaste Ressourcen festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)
