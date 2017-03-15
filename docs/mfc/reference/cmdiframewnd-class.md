---
title: CMDIFrameWnd-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- MDI frame windows
- CMDIFrameWnd class
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0eae6c14038dd27a5779757d1807068fbe865b81
ms.lasthandoff: 02/24/2017

---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd-Klasse
Stellt die Funktionalität eines untergeordneten Windows-MDI-Rahmenfensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Erstellt ein Objekt vom Typ `CMDIFrameWnd`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Erstellt eine Windows **MDICLIENT** Fenster für dieses `CMDIFrameWnd`. Aufgerufen von der `OnCreate` Memberfunktion `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Erstellt ein neues untergeordnetes Fenster.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Gibt im Popup-Menü "Fenster" zurück.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Aktiviert einen anderen untergeordneten MDI-Fensters.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|Ordnet alle untergeordneten Fenster ein überlappend an.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Ruft den derzeit aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag gibt an, ab, unabhängig davon, ob das untergeordnete Element maximiert ist.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Ordnet alle minimierten Dokument untergeordnete Fenster.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Ein untergeordnetes MDI-Fenster wird maximiert.|  
|[CMDIFrameWnd::MDINext](#mdinext)|Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster, und fügt das derzeit aktiven untergeordneten Fenster hinter alle anderen untergeordneten Fenster.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Aktiviert das vorherige untergeordnete Fenster, und der derzeit aktiven untergeordneten Fenster unmittelbar hinter ihm platziert.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Ein untergeordnetes MDI-Fenster wiederhergestellt von maximierten oder minimierten Größe.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Ersetzt das Menü ein MDI-Rahmenfenster und/oder im Popup-Menü "Fenster".|  
|[CMDIFrameWnd::MDITile](#mditile)|Ordnet alle untergeordneten Fenster in einem gekachelten Format.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine nützliche MDI-Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIFrameWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Sie können ein MDI-Rahmenfenster erstellen, durch Aufrufen der [erstellen](../../mfc/reference/cframewnd-class.md#create) oder [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) Memberfunktion `CFrameWnd`.  
  
 Vor dem Aufruf von **erstellen** oder `LoadFrame`, müssen Sie die Frame-Window-Objekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf von **erstellen** können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um das Symbol und Stile für den Rahmen festzulegen.  
  
 Verwenden der **erstellen** Memberfunktion Erstellungsparameter des Frames als sofortige Argumente übergeben.  
  
 `LoadFrame`erfordert weniger Argumente als **erstellen**, und stattdessen entnimmt die Standardwerte von Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Für den Zugriff durch `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Obwohl **MDIFrameWnd** abgeleitet ist `CFrameWnd`, abgeleitet von eine Rahmenfenster (Klasse) `CMDIFrameWnd` müssen nicht deklariert werden, mit `DECLARE_DYNCREATE`.  
  
 Die `CMDIFrameWnd` Klasse erbt ein Großteil der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen finden Sie in der [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Klasse Beschreibung. Die `CMDIFrameWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   Ein MDI-Rahmenfenster verwaltet die **MDICLIENT** Fenster, in Verbindung mit Steuerleisten neu positionieren. Das MDI-Clientfenster ist das direkt übergeordnete Element der Rahmen des untergeordneten MDI-Fenster. Die **WS_HSCROLL** und **WS_VSCROLL** Fensterstile, die auf einem `CMDIFrameWnd` gelten für das MDI-Clientfenster anstatt das Hauptrahmenfenster, damit der Benutzer des MDI-Clientbereichs (wie in der Windows Program Manager, z. B.) einen Bildlauf durchführen kann.  
  
-   Ein MDI-Rahmenfenster besitzt ein Standardmenü, die als Menüleiste verwendet wird, wenn keine aktive untergeordnete MDI-Fenster vorhanden ist. Wird eine aktive untergeordnete MDI-Element, wird die Menüleiste des MDI-Rahmenfensters durch die untergeordneten MDI-Fenster-Menü automatisch ersetzt.  
  
-   Ein MDI-Rahmenfenster funktioniert in Verbindung mit der aktuellen, untergeordnetes MDI-Fenster, sofern vorhanden. Beispielsweise werden Command-Meldungen zu derzeit aktiven untergeordneten MDI-Fensters vor MDI-Rahmenfenster delegiert.  
  
-   Ein MDI-Rahmenfenster hat die Standardhandler für die folgenden standardmäßigen Fenster Befehle:  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   Ein MDI-Rahmenfenster verfügt auch über eine Implementierung von **ID_WINDOW_NEW**, erstellt einen neuen Frame und die Sicht auf das aktuelle Dokument. Eine Anwendung kann diese Standardeinstellung Befehl Implementierungen MDI-Fenster Behandlung anpassen überschrieben werden.  
  
 Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow` . Die `CFrameWnd` Implementierung von `PostNcDestroy` das C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster standardmäßig `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CMDIFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecmdiframewnda--cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd  
 Erstellt ein `CMDIFrameWnd`-Objekt.  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die **erstellen** oder `LoadFrame` Memberfunktion sichtbar MDI-Rahmenfenster erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#13;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="a-namecreateclienta--cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd::CreateClient  
 Erstellt das MDI-Client, der verwaltet die `CMDIChildWnd` Objekte.  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCreateStruct`  
 Ein long-Zeiger auf eine [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) Struktur.  
  
 `pWindowMenu`  
 Ein Zeiger auf die im Popup-Menü "Fenster".  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion aufgerufen werden, wenn Sie überschreiben die `OnCreate` Memberfunktion direkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&14;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="a-namecreatenewchilda--cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
 Erstellt ein neues untergeordnetes Fenster.  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pClass`  
 Die Laufzeit-Klasse des untergeordneten Fensters erstellt werden.  
  
 *nResource*  
 Die ID des freigegebenen Ressourcen, die das untergeordnete Fenster zugeordnet.  
  
 `hMenu`  
 Das untergeordnete Fenster im Menü.  
  
 `hAccel`  
 Das untergeordnete Fenster Zugriffstaste.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Erstellen von untergeordneten Fenstern von einem MDI-Rahmenfenster.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#15;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 In diesem Beispiel ist ein Auszug aus dem Knowledge Base-Artikel Q201045, "So wird's gemacht: eine nicht-Dokument/Ansicht-MDI-Anwendung mehrere Fenstertypen hinzugefügt." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namegetwindowmenupopupa--cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 Rufen Sie diese Memberfunktion zum Abrufen eines Handles für den aktuellen Popup-Menü mit dem Namen "Window" (dem Popup-Menü mit Menüelementen für MDI-Fenster-Management).  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>Parameter  
 *hMenuBar*  
 Die aktuelle Menüleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Fenster im Popupmenü eine vorhanden ist. andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht ein Popupmenü mit standardmäßigen Menübefehle, z. B. **ID_WINDOW_NEW** und **ID_WINDOW_TILE_HORZ**.  
  
 Überschreiben Sie diese Memberfunktion auf, haben Sie, indem Sie im Fenstermenü, die das Standardmenü-Befehls-IDs nicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&16;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="a-namemdiactivatea--cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 Aktiviert einen anderen untergeordneten MDI-Fensters.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndActivate*  
 Verweist auf das untergeordnete MDI-Fenster aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion sendet die [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) Nachricht an das untergeordnete Fenster aktiviert wird und das untergeordnete Fenster deaktiviert wird.  
  
 Dies ist die gleiche Nachricht, die gesendet wird, wenn der Benutzer den Fokus auf ein untergeordnetes MDI-Fenster festlegt, mit der Maus oder Tastatur.  
  
> [!NOTE]
>  Unabhängig von der MDI-Rahmenfenster ist ein untergeordnetes MDI-Fenster aktiviert. Das untergeordnete Fenster, die der letzten Aktivierung wird gesendet, wenn der Frame aktiv wird, eine [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) Nachricht an einen aktiven Fensterrahmen und Titelleiste jedoch zeichnen erhält keine anderen `WM_MDIACTIVATE` Nachricht.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).  
  
##  <a name="a-namemdicascadea--cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 Ordnet alle MDI-untergeordneten Fenster überlappend Format.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>Parameter  
 `nType`  
 Gibt ein Flag Cascade an. Nur die folgenden Flags können angegeben werden: `MDITILE_SKIPDISABLED`, wodurch verhindert wird, dass aktiven untergeordneten MDI-Fenstern kaskadiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version der `MDICascade`, ohne Parameter überlappend an alle untergeordneten MDI, einschließlich deaktiviert zu. Die zweite Version wird optional nicht überlappend deaktiviert untergeordnete MDI-Fenster, wenn Sie angeben `MDITILE_SKIPDISABLED` für die `nType` Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&17;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="a-namemdigetactivea--cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 Ruft den aktuellen aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag zur Angabe, ob das untergeordnete Fenster maximiert ist.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pbMaximized*  
 Ein Zeiger auf eine **BOOL** Wert zurückgeben. Legen Sie auf **TRUE** auf zurück, wenn das Fenster maximiert ist andernfalls **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktive untergeordnete MDI-Fenster.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="a-namemdiiconarrangea--cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange  
 Ordnet alle minimierten Dokument untergeordnete Fenster.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies beeinflusst nicht untergeordnete Fenster, die nicht minimiert werden.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIFrameWnd::MDICascade](#mdicascade).  
  
##  <a name="a-namemdimaximizea--cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 Maximiert die angegebenen untergeordneten MDI-Fensters.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster zu maximieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes Fenster maximiert wird, ändert sich Windows um seinen Clientbereich, geben Sie im Clientfenster zu machen. Windows fügt Systemmenü des untergeordneten Fensters in der Menüleiste des Frames, sodass der Benutzer das untergeordnete Fenster schließen oder wiederherstellen kann. Außerdem werden die Frame-Titel den Titel des untergeordneten Fensters hinzugefügt.  
  
 Wenn ein anderes untergeordnetes MDI-Fenster aktiviert wird, wenn das momentan aktive untergeordnete MDI-Fenster maximiert wird, wird Windows derzeit aktiven untergeordneten wiederhergestellt und wird der neu aktivierten untergeordneten Fenster maximiert.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="a-namemdinexta--cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd::MDINext  
 Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster, und fügt das derzeit aktiven untergeordneten Fenster hinter alle anderen untergeordneten Fenster.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das momentan aktive untergeordnete MDI-Fenster maximiert wird, wird die Memberfunktion stellt den untergeordneten und maximiert die neu aktivierte untergeordneten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&18;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="a-namemdipreva--cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 Aktiviert das vorherige untergeordnete Fenster, und der derzeit aktiven untergeordneten Fenster unmittelbar hinter ihm platziert.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das momentan aktive untergeordnete MDI-Fenster maximiert wird, wird die Memberfunktion stellt den untergeordneten und maximiert die neu aktivierte untergeordneten.  
  
##  <a name="a-namemdirestorea--cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 Ein untergeordnetes MDI-Fenster wiederhergestellt von maximierten oder minimierten Größe.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das wiederherzustellende Fenster.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).  
  
##  <a name="a-namemdisetmenua--cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 Ersetzt das Menü ein MDI-Rahmenfenster und/oder im Popup-Menü "Fenster".  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameMenu*  
 Gibt an, klicken Sie im Menü des neuen Fenster Menüs. Wenn **NULL**, klicken Sie im Menü wird nicht geändert.  
  
 `pWindowMenu`  
 Gibt an, klicken Sie im Menü des neuen Fensters Popupmenüs. Wenn **NULL**, klicken Sie im Menü wird nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Rahmenfenster-Menü, das durch diese Nachricht ersetzt. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `MDISetMenu`, muss eine Anwendung Aufrufen der [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) Memberfunktion `CWnd` die Menüleiste zu aktualisieren.  
  
 Wenn dieser Aufruf im Popup-Menü "Fenster" ersetzt, MDI-untergeordneten Fensters Menüelemente werden aus dem vorherigen Fenstermenü entfernt und das neue Fenster Popupmenü hinzugefügt.  
  
 Wenn ein untergeordnetes MDI-Fenster maximiert wird und dieser Aufruf dieses MDI-Rahmenfenster ersetzt, sind die Steuerelemente des Steuerelements im Menü und Wiederherstellung aus dem vorherigen Fenster Menü entfernt und das neue Menü hinzugefügt.  
  
 Rufen Sie diese Memberfunktion auf, wenn Sie das Framework verwenden, um die untergeordneten MDI-Fenster zu verwalten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&19;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&20;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="a-namemditilea--cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd::MDITile  
 Ordnet alle untergeordneten Fenster in einem gekachelten Format.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>Parameter  
 `nType`  
 Gibt ein Flag Tiling. Dieser Parameter kann eine der folgenden Werte sein:  
  
- `MDITILE_HORIZONTAL`Kacheln untergeordnete MDI-Fenster, über eine andere, ein Fenster angezeigt wird.  
  
- `MDITILE_SKIPDISABLED`Verhindert, dass deaktivierte untergeordnete MDI-Fenster nebeneinander angeordnet werden.  
  
- `MDITILE_VERTICAL`Kacheln untergeordnete MDI-Fenster damit, ein Fenster neben anderen angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version der `MDITile`, ohne Parameter werden die Fenster vertikal unter Windows-Versionen 3.1 und höher angeordnet. Die zweite Version Ordnet Fenster vertikal oder horizontal, abhängig vom Wert der `nType` Parameter.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIFrameWnd::MDICascade](#mdicascade).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)

