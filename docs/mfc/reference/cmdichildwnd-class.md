---
title: CMDIChildWnd-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- MDI [C++], child windows
- windows [C++], MDI
- CMDIChildWnd class
- child windows, CMDIChildWnd class
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 240af1fe5f3afa4cdb7d4d585dc74cc4836799cc
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd-Klasse
Stellt die Funktionalität eines untergeordneten Windows-MDI-Fensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Erstellt ein `CMDIChildWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|Erstellt das zugeordnete Windows-MDI-untergeordneten Fenster der `CMDIChildWnd` Objekt.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Gibt das übergeordnete MDI-Frame des MDI-Clientfenster zurück.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Aktiviert dieses untergeordneten MDI-Fensters.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Löscht diese untergeordneten MDI-Fensters.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Diese untergeordneten MDI-Fenster wird maximiert.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Diese untergeordneten MDI-Fenster wiederhergestellt von maximierten oder minimierten Größe.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Legt die Handles für Menüs und Accelerator Ressourcen fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein untergeordnetes MDI-Fenster sieht ähnlich wie eine normale Rahmenfenster, außer dass die untergeordneten MDI-Fensters in einem MDI-Rahmenfenster und nicht auf dem Desktop angezeigt wird. Ein untergeordnetes MDI-Fenster besitzt keine eigene Menüleiste, aber stattdessen teilt das Menü des MDI-Rahmenfenster. Das Framework ändert automatisch den Frame MDI-Menü, das momentan aktive untergeordnete MDI-Fenster darstellt.  
  
 Um eine nützliche untergeordnete MDI-Fenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIChildWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Es gibt drei Möglichkeiten, ein untergeordnetes MDI-Fenster zu erstellen:  
  
-   Erstellen Sie direkt mit **erstellen**.  
  
-   Erstellen Sie direkt mit `LoadFrame`.  
  
-   Erstellen Sie sie indirekt über eine Dokumentvorlage.  
  
 Vor dem Aufruf von **erstellen** oder `LoadFrame`, müssen Sie das Rahmenfenster Objekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf von **erstellen** können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um das Symbol und Stile für den Rahmen festzulegen.  
  
 Verwenden der **erstellen** Memberfunktion Erstellungsparameter des Frames als sofortige Argumente übergeben.  
  
 `LoadFrame`erfordert weniger Argumente als **erstellen**, und stattdessen entnimmt die Standardwerte von Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Zugänglich sein `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Wenn ein `CMDIChildWnd` Objekt enthält, Ansichten und Dokumente, die indirekt vom Framework nicht direkt durch den Programmierer erstellt werden. Das `CDocTemplate` Objekt orchestriert die Erstellung des Frames, die Erstellung der enthaltenden Ansichten und die Verbindung der Ansichten auf das entsprechende Dokument. Die Parameter von der `CDocTemplate` Konstruktor Festlegen der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird vom Framework verwendet, dynamisch neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe der neuen Datei Befehl oder MDI-Fenster neue) erstellen.  
  
 Eine Klasse abgeleitet `CMDIChildWnd` muss deklariert werden, mit `DECLARE_DYNCREATE` in der Reihenfolge für die oben genannten `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 Die `CMDIChildWnd` Klasse erbt ein Großteil der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen finden Sie unter der [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Klasse Beschreibung. Die `CMDIChildWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   In Verbindung mit der `CMultiDocTemplate` -Klasse, die mehrere `CMDIChildWnd` Objekte aus derselben Dokumentvorlage im gleiche Menü Einsparung von Windows-Systemressourcen freizugeben.  
  
-   Der derzeit aktive untergeordneten MDI-Fenstermenü vollständig ersetzt die MDI-Rahmenfenster und die Beschriftung der derzeit aktiven untergeordneten MDI-Fensters des MDI-Rahmenfensters Beschriftung hinzugefügt wird. Weitere Beispiele für MDI-untergeordneten Funktionen, die in Verbindung mit einem MDI-Rahmenfenster implementiert werden, finden Sie unter der `CMDIFrameWnd` -Klasse Beschreibung.  
  
 Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow` . Die `CFrameWnd` Implementierung von `PostNcDestroy` das C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster standardmäßig `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CMDIChildWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd  
 Aufruf zum Erstellen einer `CMDIChildWnd` Objekt.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** zum Erstellen des Fensters sichtbar.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIChildWnd::Create](#create).  
  
##  <a name="create"></a>CMDIChildWnd::Create  
 Rufen Sie diese Memberfunktion zum untergeordneten Windows-MDI-Fenster erstellen, und fügen Sie es auf die `CMDIChildWnd` Objekt.  
  
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
 Verweist auf eine Null-terminierte Zeichenfolge, die die Windows-Klassennamen (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur). Der Name der Klasse kann einen beliebigen Namen registriert die [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) globale Funktion. Sollte **NULL** für einen Standard `CMDIChildWnd`.  
  
 `lpszWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters darstellt. Als Text verwendet für die Titelleiste.  
  
 `dwStyle`  
 Gibt das Zeitfenster [Stil](../../mfc/reference/window-styles.md) Attribute. Die **WS_CHILD** Stil ist erforderlich.  
  
 `rect`  
 Enthält die Größe und Position des Fensters. Die `rectDefault` Wert kann Windows die Größe und Position des neuen `CMDIChildWnd`.  
  
 `pParentWnd`  
 Gibt das Fenster übergeordnete an. Wenn **NULL**, Hauptfenster der Anwendung verwendet wird.  
  
 `pContext`  
 Gibt eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das derzeit aktive Fenster kann die Beschriftung des übergeordneten Rahmenfensters bestimmen. Diese Funktion ist deaktiviert, durch das Deaktivieren der **FWS_ADDTOTITLE** Formatbit untergeordneten Rahmenfenster.  
  
 Das Framework ruft diese Member-Funktion als Antwort auf eine Benutzerbefehl, um ein untergeordnetes Fenster zu erstellen, und das Framework verwendet die `pContext` Parameter ordnungsgemäß das untergeordnete Fenster für die Anwendung eine Verbindung herstellen. Beim Aufruf von **erstellen**, `pContext` kann **NULL**.  
  
### <a name="example"></a>Beispiel  
 Beispiel 1:  
  
 [!code-cpp[NVC_MFCWindowing&#7;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Beispiel  
 Beispiel 2:  
  
 [!code-cpp[NVC_MFCWindowing&#8;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#9;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame  
 Rufen Sie diese Funktion, um den übergeordneten MDI-Frame zurück.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf MDI-Rahmenfenster übergeordneten.  
  
### <a name="remarks"></a>Hinweise  
 Der Frame, der zurückgegeben wird zwei übergeordneten aus entfernt die `CMDIChildWnd` und ist das übergeordnete Element des Fensters des Typs **MDICLIENT** , verwaltet die `CMDIChildWnd` Objekt. Rufen Sie die [GetParent](../../mfc/reference/cwnd-class.md#getparent) Member-Funktion zurückgeben der `CMDIChildWnd` des Objekts sofort **MDICLIENT** übergeordneten eine temporäre `CWnd` Zeiger.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="mdiactivate"></a>CMDIChildWnd::MDIActivate  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster unabhängig von der MDI-Rahmenfenster zu aktivieren.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Frame aktiv ist, wird das untergeordnete Fenster, das zuletzt aktiviert wurde ebenfalls aktiviert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster zu zerstören.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Funktion den Titel des untergeordneten Fensters vom Rahmenfenster entfernt und das untergeordnete Fenster deaktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#10;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster zu maximieren.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes Fenster maximiert wird, ändert sich Windows um seinen Clientbereich der Innenbereich des Rahmenfensters zu machen. Windows speichert Systemmenü des untergeordneten Fensters in der Menüleiste des Frames, so, dass der Benutzer wiederherstellen kann, oder schließen das untergeordnete Fenster und dem Fenster Titel den Titel des untergeordneten Fensters hinzugefügt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#11;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>CMDIChildWnd::MDIRestore  
 Rufen Sie diese Memberfunktion, um ein untergeordnetes MDI-Fenster von maximierten oder minimierten Größe wiederherzustellen.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#12;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>CMDIChildWnd::SetHandles  
 Legt die Handles für Menüs und Accelerator Ressourcen fest.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Das Handle für eine Ressource.  
  
 `hAccel`  
 Das Handle einer Zugriffstaste-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion verwendeten vom Window-Objekt des untergeordneten MDI-Menü und Zugriffstaste Ressourcen festlegen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)

