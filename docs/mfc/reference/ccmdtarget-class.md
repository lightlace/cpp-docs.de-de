---
title: CCmdTarget-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
dev_langs:
- C++
helpviewer_keywords:
- message maps, CCmdTarget base class
- command targets
- CCmdTarget class
- command routing, command targets
- targets, command
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: d58ee8e02c57c48c58f13c7e826fd01a1c0d9f57
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="ccmdtarget-class"></a>CCmdTarget-Klasse
Die Basisklasse für die meldungszuordnungsarchitektur der Microsoft Foundation Class-Bibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Erstellt ein `CCmdTarget`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Zeigt den Cursor als eine Sanduhrcursor an.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|Bewirkt, dass eine Aktion angegeben, die von einem OLE-Verb ausgeführt werden.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE-Automatisierung für ermöglicht die `CCmdTarget` Objekt.|  
|[CCmdTarget::EnableConnections](#enableconnections)|Auslösen von Ereignissen ermöglicht für Verbindungspunkte.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Ermöglicht die Typbibliothek des Objekts.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Kehrt zur vorherigen Cursor zurück.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Listet die OLE-Verben für ein Objekt.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|Gibt einen Zeiger auf die `CCmdTarget` zugeordnete Objekt der `IDispatch` Zeiger.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Ruft die primäre Dispatch-Schnittstellen-ID.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|Gibt einen Zeiger auf die `IDispatch` zugeordnete Objekt der `CCmdTarget` Objekt.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Ruft die Beschreibung, die der angegebenen GUID entspricht.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|Ruft einen Zeiger auf eine Typbibliothek.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Ruft den Typ-Bibliothek-Cache ab.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Ermöglicht die Automatisierung der Methodenaufruf.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|Gibt, die ungleich NULL, wenn eine Automatisierungsfunktion sollte einen Wert zurückgeben.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Befehlsmeldungen Routen und sendet.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Bereinigt die letzte OLE-Verweis nicht freigegeben ist.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Sanduhrcursor wird wiederhergestellt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine meldungszuordnung leitet Befehle oder Nachrichten für die Memberfunktionen, die Sie schreiben, zu deren Behandlung. (Ein Befehl ist eine Nachricht von einem Menüelement Befehlsschaltfläche oder Zugriffstaste.)  
  
 Key-Framework-Klassen abgeleitet `CCmdTarget` enthalten [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), und [CFrameWnd](../../mfc/reference/cframewnd-class.md). Wenn Sie beabsichtigen eine neue Klasse, um Meldungen zu verarbeiten, leiten Sie Klasse aus einer der folgenden `CCmdTarget`-abgeleitete Klassen. Sie werden nur selten leiten eine Klasse von `CCmdTarget` direkt.  
  
 Eine Übersicht über Befehlsziele und `OnCmdMsg` routing finden Sie unter [Befehlsziele](../../mfc/command-targets.md), [Befehlsrouting](../../mfc/command-routing.md), und [Zuordnen von Meldungen](../../mfc/mapping-messages.md).  
  
 `CCmdTarget`enthält die Memberfunktionen, die die Anzeige von einer Sanduhrcursor behandeln. Sanduhrcursor angezeigt, wenn Sie erwarten, dass einen Befehl ein bemerkbar Zeitintervalls ausgeführt wird.  
  
 Dispatchzuordnungen, meldungszuordnungen ähnelt, werden verwendet, um OLE-Automatisierung verfügbar zu machen `IDispatch` Funktionalität. Von dieser Schnittstelle verfügbar macht, können andere Anwendungen (z. B. Visual Basic) in Ihrer Anwendung aufrufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor  
 Rufen Sie diese Funktion, um den Cursor als Sanduhr angezeigt, wenn Sie erwarten, dass einen Befehl ein bemerkbar Zeitintervalls ausgeführt wird.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um dem Benutzer anzuzeigen, dass darauf ausgelastet ist, z. B. wenn ein **CDocument** Objekt lädt oder speichert selbst in einer Datei.  
  
 Die Aktionen der `BeginWaitCursor` sind nicht immer effektiv außerhalb eines einzelnen meldungshandlers als andere Aktionen wie z. B. `OnSetCursor` Behandlung die, den Cursor ändern kann.  
  
 Rufen Sie `EndWaitCursor` zum Wiederherstellen des vorherigen Cursors.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="ccmdtarget"></a>CCmdTarget::CCmdTarget  
 Erstellt ein `CCmdTarget`-Objekt.  
  
```  
CCmdTarget();
```  
  
##  <a name="dooleverb"></a>CCmdTarget::DoOleVerb  
 Bewirkt, dass eine Aktion angegeben, die von einem OLE-Verb ausgeführt werden.  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Numerischen Bezeichner des Verbs an.  
  
 `lpMsg`  
 Zeiger auf die [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) Struktur, die Beschreibung des Ereignisses (z. B. einem Doppelklick), die das Verb aufgerufen hat.  
  
 `hWndParent`  
 Das Handle des Dokumentfensters, das das Objekt enthält.  
  
 `lpRect`  
 Zeiger auf die [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur mit den Koordinaten, in Pixel, die ein Objekt definieren umschließenden Rechtecks in *HwndParent*.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508). Die möglichen Aktionen werden von aufgelistet [CCmdTarget::EnumOleVerbs](#enumoleverbs).  
  
##  <a name="enableautomation"></a>CCmdTarget::EnableAutomation  
 Mit dieser Funktion können Sie OLE-Automatisierung für ein Objekt zu aktivieren.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aus dem Konstruktor des Objekts aufgerufen und sollte nur aufgerufen werden, wenn eine Dispatchzuordnung für die Klasse deklariert wurde. Weitere Informationen zur Automatisierung finden Sie in den Artikeln [Automatisierungsclients](../../mfc/automation-clients.md) und [Automatisierungsserver](../../mfc/automation-servers.md).  
  
##  <a name="enableconnections"></a>CCmdTarget::EnableConnections  
 Auslösen von Ereignissen ermöglicht für Verbindungspunkte.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>Hinweise  
 Um Verbindungspunkte zu aktivieren, rufen Sie diese Memberfunktion im Konstruktor der abgeleiteten Klasse ein.  
  
##  <a name="enabletypelib"></a>CCmdTarget::EnableTypeLib  
 Ermöglicht die Typbibliothek des Objekts.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion im Konstruktor der Ihre `CCmdTarget`-abgeleitetes Objekt aus, wenn sie die Typinformationen bereitstellt. Weitere Informationen finden Sie im Knowledge Base-Artikel Q185720, "So wird's gemacht: Bereitstellen von Typinformationen aus einer MFC-Automatisierungsservers." Knowledge Base-Artikeln finden Sie unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor  
 Mit dieser Funktion werden, nachdem Sie aufgerufen haben die `BeginWaitCursor` Memberfunktion versucht, die von der Sanduhrcursor an den vorherigen Cursor zurückgegeben.  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Memberfunktion auch, nachdem die Sanduhrcursor aufgerufen wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs  
 Listet die OLE-Verben für ein Objekt.  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `ppenumOleVerb`  
 Ein Zeiger auf einen Zeiger auf eine [IEnumOLEVERB](http://msdn.microsoft.com/library/windows/desktop/ms695084) Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn das Objekt mindestens ein OLE-Verb unterstützt (in diesem Fall \* `ppenumOleVerb` verweist auf eine **IEnumOLEVERB** Enumeratorschnittstelle), andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject:: EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781).  
  
##  <a name="fromidispatch"></a>CCmdTarget::FromIDispatch  
 Mit dieser Funktion wird zum Zuordnen einer `IDispatch` -Zeiger ist, Empfangen von Automation-Memberfunktionen einer Klasse in der `CCmdTarget` Objekt, das die Schnittstellen implementiert die `IDispatch` Objekt.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDispatch`  
 Ein Zeiger auf ein `IDispatch`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CCmdTarget` Objekt zugeordneten `lpDispatch`. Diese Funktion gibt **NULL** Wenn die `IDispatch` Objekt wird nicht als ein Microsoft Foundation Class erkannt `IDispatch` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Ergebnis dieser Funktion ist das Gegenteil eines Aufrufs an die Memberfunktion `GetIDispatch`.  
  
##  <a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID  
 Ruft die primäre Dispatch-Schnittstellen-ID.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>Parameter  
 *pIID*  
 Ein Zeiger auf eine Schnittstellen-ID (eine [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls "false". Im Erfolgsfall \* *pIID* festgelegt ist, um die primären Dispatch-Schnittstellen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht außer Kraft gesetzt, `GetDispatchIID` gibt "false"). Finden Sie unter [COleControl](../../mfc/reference/colecontrol-class.md).  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q185720, "So wird's gemacht: Bereitstellen von Typinformationen aus einer MFC-Automatisierungsservers." Knowledge Base-Artikeln finden Sie unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="getidispatch"></a>CCmdTarget::GetIDispatch  
 Rufen Sie diese Memberfunktion zum Abrufen der `IDispatch` Zeiger von einer Automatisierungsmethode, einer gibt eine `IDispatch` Zeiger oder nimmt eine `IDispatch` Zeiger als Verweis.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>Parameter  
 *bAddRef*  
 Gibt an, ob die für das Objekt den Verweiszähler erhöht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IDispatch` Zeiger, die dem Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Für Objekte dieser Aufruf `EnableAutomation` in ihren Konstruktoren, Automatisierung aktiviert sodass, diese Funktion einen Zeiger auf die MFC-Implementierung von zurückgibt `IDispatch` wird, von Clients, die Kommunikation über die `IDispatch` Schnittstelle. Ein Verweis auf den Zeiger durch das Aufrufen dieser Funktion wird automatisch hinzugefügt werden, daher ist es nicht notwendig, einen Aufruf [IUnknown:: AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  
  
##  <a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount  
 Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Schnittstellen mit Typinformationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion im Grunde implementiert [IDispatch:: GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12).  
  
 Abgeleitete Klassen überschreiben, sollte dieser Funktion können Sie die Anzahl der Schnittstellen mit Typinformationen bereitgestellt (0 oder 1) zurück. Wenn Sie nicht überschrieben, **Fall** gibt 0 zurück. Um zu überschreiben, verwenden die [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeLib` und `GetTypeLibCache`.  
  
##  <a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid  
 Ruft die Beschreibung, die der angegebenen GUID entspricht.  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lcid`  
 Ein Gebietsschemabezeichner ( `LCID`).  
  
 `guid`  
 Die [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931) die typbeschreibung.  
  
 `ppTypeInfo`  
 Zeiger auf einen Zeiger auf die `ITypeInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein HRESULT, das den Erfolg oder Fehler des Aufrufs angibt. Im Erfolgsfall * `ppTypeInfo` verweist auf die Schnittstelle der Type-Informationen.  
  
##  <a name="gettypelib"></a>CCmdTarget::GetTypeLib  
 Ruft einen Zeiger auf eine Typbibliothek.  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>Parameter  
 `lcid`  
 Ein Gebietsschemabezeichner ( `LCID`).  
  
 `ppTypeLib`  
 Ein Zeiger auf einen Zeiger auf die `ITypeLib` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein HRESULT, das den Erfolg oder Fehler des Aufrufs angibt. Im Erfolgsfall * `ppTypeLib` verweist auf die Typ-Library-Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht außer Kraft gesetzt, `GetTypeLib` TYPE_E_CANTLOADLIBRARY zurückgibt). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLibCache`.  
  
##  <a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache  
 Ruft den Typ-Bibliothek-Cache ab.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine **CTypeLibCache** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht außer Kraft gesetzt, **GetTypeLibCache** gibt NULL zurück). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLib`.  
  
##  <a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed  
 Diese Funktion wird aufgerufen, durch die Implementierung von MFC **IDispatch:: Invoke** bestimmen, ob eine angegebene Automatisierungsmethode (identifiziert durch `dispid`) aufgerufen werden kann.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Eine Dispatch-ID  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn die Methode aufgerufenen, andernfalls "false" werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `IsInvokeAllowed` gibt "true", **Invoke** geht zum Aufrufen der Methode; andernfalls `Invoke` schlägt fehl, E_UNEXPECTED zurückgegeben.  
  
 Abgeleitete Klassen können Überschreiben dieser Funktion können Sie die entsprechenden Werte zurück (wenn nicht außer Kraft gesetzt, `IsInvokeAllowed` gibt "true"). Finden Sie unter insbesondere [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).  
  
##  <a name="isresultexpected"></a>CCmdTarget::IsResultExpected  
 Verwendung `IsResultExpected` zu ermitteln, ob ein Client einen Rückgabewert von seinem Aufruf von Automatisierungsfunktion erwartet.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Automatisierungsfunktion einen Wert zurückgeben soll; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die OLE-Schnittstelle stellt Informationen zum MFC gibt an, ob der Client verwenden oder ignorieren das Ergebnis eines Funktionsaufrufs und MFC verwendet im Gegenzug diese Informationen, um zu bestimmen, das Ergebnis eines Aufrufs von `IsResultExpected`. Wenn Produktion eines Rückgabewerts Zeit - oder ressourcenintensiv ist können Sie die Effizienz erhöhen, durch den Aufruf dieser Funktion vor dem Berechnen des Rückgabewerts.  
  
 Diese Funktion gibt 0 zurück, nur einmal, damit Sie gültige Rückgabewerte von anderen Automatisierungsfunktionen erhalten werden, wenn Sie sie aus der Automatisierungsfunktion Aufrufen des Clients aufgerufen hat.  
  
 `IsResultExpected`Gibt einen Wert ungleich NULL zurück, wenn wird aufgerufen, wenn ein Automation-Funktionsaufruf nicht ausgeführt wird.  
  
##  <a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg  
 Wird aufgerufen, durch das Framework zum Weiterleiten und Befehl Nachrichten verschicken und die Aktualisierung der Benutzeroberfläche Befehlsobjekte zu behandeln.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Enthält die Befehls-ID.  
  
 `nCode`  
 Identifiziert den Befehl Benachrichtigungscode. Finden Sie unter **"Hinweise"** für Weitere Informationen zu den Werten für `nCode`.  
  
 `pExtra`  
 Nach dem Wert des verwendet `nCode`. Finden Sie unter **"Hinweise"** Weitere Informationen zu `pExtra`.  
  
 `pHandlerInfo`  
 Wenn dies nicht der **NULL**, `OnCmdMsg` füllt die **pTarget** und **Pmf** Mitglied der `pHandlerInfo` Struktur anstatt den Befehl zu verteilen. Dieser Parameter muss in der Regel **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist die Haupt-Implementierung-Routine, die Architektur der Framework-Befehl.  
  
 Zur Laufzeit `OnCmdMsg` sendet einen Befehl auf andere Objekte oder den Befehl selbst-handles durch Aufrufen der Stammklasse `CCmdTarget::OnCmdMsg`, welche die tatsächliche meldungszuordnung Suche. Eine vollständige Beschreibung der Standardeinstellung Befehlsrouting, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
 In seltenen Fällen möchten Sie möglicherweise überschreiben Sie diese Memberfunktion, um das Framework erweitert wird, standardbefehlsroutings. Verweisen auf [technischen Hinweis 21](../../mfc/tn021-command-and-message-routing.md) für erweiterte Details der Befehlsrouting Architektur.  
  
 Wenn Sie außer Kraft setzen `OnCmdMsg`, geben Sie an den richtigen Wert für `nCode`, den Befehl Benachrichtigungscode und `pExtra`, dem hängt vom Wert des `nCode`. In der folgenden Tabelle sind die entsprechenden Werte aufgeführt:  
  
|`nCode`-Wert|`pExtra`-Wert|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|AUFGERUFEN|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease  
 Vom Framework aufgerufen, wenn der letzte OLE-Verweis, oder das Objekt freigegeben wird.  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um eine besondere Behandlung für diese Situation zu gewährleisten. Die standardmäßige Implementierung löscht das Objekt.  
  
##  <a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor  
 Mit dieser Funktion wird zum entsprechenden Sanduhrcursor wiederherstellen, nachdem der Systemcursor geändert wurde (z. B. nachdem ein Meldungsfeld geöffnet und anschließend geschlossen wird, während in der Mitte eines längeren Vorgangs).  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel ACDUAL](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver-Klasse](../../mfc/reference/coledispatchdriver-class.md)

