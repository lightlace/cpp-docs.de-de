---
title: CMDIFrameWnd-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
dev_langs: C++
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc40ac38d4f74848448b26284ad225faad04864e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd-Klasse
Stellt die Funktionalität eines untergeordneten Windows-MDI-Rahmenfensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Erstellt ein Objekt vom Typ `CMDIFrameWnd`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Erstellt eine Windows- **MDICLIENT** Fenster dafür `CMDIFrameWnd`. Wird aufgerufen, indem Sie die `OnCreate` Memberfunktion von `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Erstellt ein neues untergeordnetes Fenster.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Gibt im Fenster Popupmenü zurück.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Aktiviert einen anderen untergeordneten MDI-Fensters.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|Ordnet alle untergeordneten Fenster in einem kaskadierenden Format an.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Ruft die derzeit aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag, der angibt, ab, unabhängig davon, ob das untergeordnete Element maximiert ist.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Ordnet alle minimierten untergeordneten Dokumentfenster an.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Ein untergeordnetes MDI-Fenster wird maximiert.|  
|[CMDIFrameWnd::MDINext](#mdinext)|Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster durch und platziert das derzeit aktives untergeordnetes Fenster hinter alle anderen untergeordneten Fenster.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Aktiviert das vorherige untergeordnete Fenster, und schaltet das Fenster derzeit aktives untergeordnetes unmittelbar hinter.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Wird ein untergeordnetes MDI-Fenster aus maximierten oder minimierten Größe wiederhergestellt.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Ersetzt das Menü ein MDI-Rahmenfenster, im Fenster Popupmenü oder beides.|  
|[CMDIFrameWnd::MDITile](#mditile)|Ordnet alle untergeordneten Fenster in einem gekachelten Format an.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine nützliche MDI-Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIFrameWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Sie können ein MDI-Rahmenfenster erstellen, durch Aufrufen der [erstellen](../../mfc/reference/cframewnd-class.md#create) oder [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) Memberfunktion von `CFrameWnd`.  
  
 Vor dem Aufruf **erstellen** oder `LoadFrame`, müssen Sie die Frame-Fensterobjekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf **erstellen** können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion die Stile-Symbol und die Klasse für den Frame festgelegt.  
  
 Verwenden der **erstellen** Memberfunktion, die Frame-Erstellungsparameter als sofortige Argumente zu übergeben.  
  
 `LoadFrame`erfordert weniger Argumente als **erstellen**, und ruft stattdessen die meisten die Standardwerte aus Ressourcen, einschließlich der Frame Beschriftung, Symbol Zugriffstastentabelle und im Menü ab. Zugriff durch `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Obwohl **MDIFrameWnd** stammt aus `CFrameWnd`, einem Rahmenfenster (Klasse) abgeleitet `CMDIFrameWnd` müssen nicht deklariert werden, mit `DECLARE_DYNCREATE`.  
  
 Die `CMDIFrameWnd` Klasse erbt ein Großteil der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen finden Sie in der [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Klasse Beschreibung. Die `CMDIFrameWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   Ein MDI-Rahmenfenster verwaltet die **MDICLIENT** Fenster zusammen mit Schiebeleisten-Steuerelemente neu positionieren. MDI-Client-Fenster ist das direkte übergeordnete Element des untergeordneten MDI-Fenster Frame. Die **WS_HSCROLL** und **WS_VSCROLL** Fensterstile, die auf einem `CMDIFrameWnd` gelten für das Hauptrahmenfenster, anstatt der MDI-Client-Fenster, damit der Benutzer den MDI-Client-Bereich (wie in der Windows gescrollt werden kann Programm-Manager, z. B.).  
  
-   Ein MDI-Rahmenfenster besitzt ein Standardmenü, die als Menüleiste verwendet wird, wenn keine aktives untergeordnete MDI-Fenster vorhanden ist. Wird eine aktive untergeordnete MDI-Element, wird die Menüleiste des MDI-Rahmenfensters von untergeordneten MDI-Fenster-Menü automatisch ersetzt.  
  
-   Ein MDI-Rahmenfenster funktioniert in Verbindung mit der aktuellen untergeordnetes MDI-Fenster, sofern vorhanden. Befehlsmeldungen werden z. B. zu derzeit aktiven untergeordneten MDI-Fensters vor der MDI-Rahmenfenster delegiert.  
  
-   Ein MDI-Rahmenfenster hat die Standardhandler für die folgenden Fenster im Menü Standardbefehle:  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   Ein MDI-Rahmenfenster ist auch eine Implementierung von **ID_WINDOW_NEW**, wodurch erstellt einen neuen Rahmen und die Sicht auf das aktuelle Dokument. Eine Anwendung kann diesen Befehl standardimplementierungen zum Anpassen der MDI-Fenster Behandlung überschrieben werden.  
  
 Verwenden Sie nicht den C++ **löschen** Operator, um ein Framefenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung der `PostNcDestroy` der C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Wenn der Benutzer das Rahmenfenster der Standardeinstellung schließt `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CMDIFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd  
 Erstellt ein `CMDIFrameWnd`-Objekt.  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die **erstellen** oder `LoadFrame` Memberfunktion versucht, das sichtbar MDI-Rahmenfenster erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>CMDIFrameWnd::CreateClient  
 Erstellt die MDI-Client-Fenster, das verwaltet die `CMDIChildWnd` Objekte.  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCreateStruct`  
 Eine long-Zeiger auf eine [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) Struktur.  
  
 `pWindowMenu`  
 Ein Zeiger auf das Menü das Popupmenü Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion aufgerufen werden, wenn Sie überschreiben die `OnCreate` Memberfunktion direkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
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
 Die Laufzeitklasse für das untergeordnete Fenster erstellt werden soll.  
  
 *nResource*  
 Die ID des freigegebenen Ressourcen, die das untergeordnete Fenster zugeordnet.  
  
 `hMenu`  
 Das untergeordnete Fenster im Menü.  
  
 `hAccel`  
 Das untergeordnete Fenster Zugriffstaste.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion so erstellen Sie untergeordnete Fenster eine MDI-Rahmenfenster.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 In diesem Beispiel ist ein Auszug aus Knowledge Base-Artikel Q201045, "So wird's gemacht: eine nicht-Dokument-/Ansichtarchitektur MDI-Anwendung mehrere Fenstertypen hinzugefügt." Knowledge Base-Artikeln finden Sie unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 Rufen Sie diese Memberfunktion zum Abrufen eines Handles für die aktuelle Popupmenü mit dem Namen "Fenster" (im Popupmenü mit Menüelementen für MDI-Fenster-Management).  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>Parameter  
 *hMenuBar*  
 Der aktuelle Menüleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Fenster im Popupmenü sofern vorhanden ist. andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht ein Popupmenü, enthalten standard Menübefehle wie **ID_WINDOW_NEW** und **ID_WINDOW_TILE_HORZ**.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn Sie ein Fenstermenü verfügen, die nicht standardmäßige Menü-Befehls-IDs verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 Aktiviert einen anderen untergeordneten MDI-Fensters.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndActivate*  
 Verweist auf die untergeordneten MDI-Fensters aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion sendet die [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) Nachricht an das untergeordnete Fenster aktiviert wird und das untergeordnete Fenster wird deaktiviert.  
  
 Hierbei handelt es sich um dieselbe Meldung, die gesendet wird, wenn der Benutzer den Fokus auf ein untergeordnetes MDI-Fenster festlegt, mit der Maus oder Tastatur.  
  
> [!NOTE]
>  Unabhängig von der MDI-Rahmenfenster ist ein untergeordnetes MDI-Fenster aktiviert. Das untergeordnete Fenster, die zuletzt aktiviert war wird gesendet, wenn der Frame aktiv wird, eine [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) Nachricht zum Zeichnen einer aktiven Fensterrahmen sowie Titelleiste, aber keine erhält eine andere `WM_MDIACTIVATE` Nachricht.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).  
  
##  <a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 Ordnet alle untergeordnete MDI-Fenster in einem Format Cascade an.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>Parameter  
 `nType`  
 Gibt ein Flag Cascade an. Nur die folgenden Flags können angegeben werden: `MDITILE_SKIPDISABLED`, wodurch verhindert wird, dass deaktivierte untergeordnete MDI-Fenster kaskadiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version des `MDICascade`, überlappend an ohne Parameter alle untergeordnete MDI-Fenster, einschließlich deaktiviert Sitzungen. Die zweite Version ist nicht deaktiviert Cascade untergeordnete MDI-Fenster optional bei Angabe von `MDITILE_SKIPDISABLED` für die `nType` Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 Ruft ab den aktuellen aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag gibt an, ob das untergeordnete Fenster maximiert ist.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pbMaximized*  
 Ein Zeiger auf eine **BOOL** Rückgabewert. Legen Sie auf **"true"** bei der Rückgabe aus, wenn das Fenster maximiert ist andernfalls **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktive untergeordnete MDI-Fenster.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange  
 Ordnet alle minimierten untergeordneten Dokumentfenster an.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>Hinweise  
 Es hat keine Auswirkungen auf untergeordnete Fenster, die nicht minimiert werden.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIFrameWnd::MDICascade](#mdicascade).  
  
##  <a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 Die angegebene untergeordnete MDI-Fenster wird maximiert.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster zu maximieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes Fenster maximiert ist, ändert sich Windows um seinen Clientbereich, füllen Sie die Client-Fenster zu machen. Windows platziert Steuerelementmenü für das untergeordnete Fenster in der Menüleiste des Frames, sodass der Benutzer wiederherstellen kann, oder schließen Sie das untergeordnete Fenster. Darüber hinaus wird den Titel des untergeordneten Fensters hinzugefügt, auf den Titel der Frame-Fensters.  
  
 Wenn ein anderes untergeordnetes MDI-Fenster aktiviert ist, wenn der aktuell aktiven untergeordneten MDI-Fensters maximiert ist, wird Windows derzeit aktive untergeordnetes wiederhergestellt und der neu aktivierten untergeordnetes Fenster maximiert.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdinext"></a>CMDIFrameWnd::MDINext  
 Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster durch und platziert das derzeit aktives untergeordnetes Fenster hinter alle anderen untergeordneten Fenster.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aktuell aktiven untergeordneten MDI-Fensters maximiert ist, wird die Memberfunktion derzeit aktive untergeordnetes wiederhergestellt und der neu aktivierte untergeordneten maximiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 Aktiviert das vorherige untergeordnete Fenster, und schaltet das Fenster derzeit aktives untergeordnetes unmittelbar hinter.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aktuell aktiven untergeordneten MDI-Fensters maximiert ist, wird die Memberfunktion derzeit aktive untergeordnetes wiederhergestellt und der neu aktivierte untergeordneten maximiert.  
  
##  <a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 Wird ein untergeordnetes MDI-Fenster aus maximierten oder minimierten Größe wiederhergestellt.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster wiederherzustellen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).  
  
##  <a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 Ersetzt das Menü ein MDI-Rahmenfenster, im Fenster Popupmenü oder beides.  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameMenu*  
 Gibt an, klicken Sie im Menü des neuen Menüs Rahmenfenster. Wenn **NULL**, klicken Sie im Menü wird nicht geändert.  
  
 `pWindowMenu`  
 Gibt an, das Menü des neuen Fenster im Popupmenü. Wenn **NULL**, klicken Sie im Menü wird nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Frame-Fensters im Menü durch diese Meldung ersetzt. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `MDISetMenu`, muss eine Anwendung aufrufen, die [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) Memberfunktion von `CWnd` auf die Menüleiste zu aktualisieren.  
  
 Wenn dieser Aufruf im Fenster Popupmenü ersetzt, werden MDI-Fenster untergeordnete Menüelemente aus dem vorherigen Fenstermenü entfernt und das neue Fenster Popupmenü hinzugefügt.  
  
 Wenn ein untergeordnetes MDI-Fenster maximiert wird und dieser Aufruf ersetzt, die im MDI-Rahmenfenster Menü, werden die Steuerelemente des Steuerelements Menü- und Wiederherstellung aus der vorherigen Frame-Fensters im Menü entfernt und das neue Menü hinzugefügt.  
  
 Rufen Sie diese Memberfunktion nicht, wenn Sie das Framework verwenden, um Ihre untergeordneten MDI-Fenster zu verwalten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>CMDIFrameWnd::MDITile  
 Ordnet alle untergeordneten Fenster in einem gekachelten Format an.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>Parameter  
 `nType`  
 Gibt ein Flag Tiling. Dieser Parameter kann eine der folgenden Flags sein:  
  
- `MDITILE_HORIZONTAL`Kacheln untergeordnete MDI-Fenster damit, ein Fenster über anderen angezeigt wird.  
  
- `MDITILE_SKIPDISABLED`Verhindert, dass deaktivierte untergeordnete MDI-Fenster nebeneinander angeordnet werden.  
  
- `MDITILE_VERTICAL`Kacheln untergeordnete MDI-Fenster neben anderen Kanton, ein Fenster festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version des `MDITile`, ohne Angabe von Parametern werden die Fenster unter Windows-Versionen 3.1 und höher vertikal angeordnet. Die zweite Version Kacheln Windows vertikal oder horizontal, abhängig vom Wert der `nType` Parameter.  
  
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
