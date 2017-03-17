---
title: CCmdTarget-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b5b7617f6b3d89e454e31c9f95b5d4455569114
ms.lasthandoff: 02/24/2017

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
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Zeigt den Cursor als Sanduhr Cursor.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|Bewirkt, dass eine Aktion angegeben, die von einer OLE-Aktion ausgeführt werden.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE-Automatisierung für ermöglicht die `CCmdTarget` Objekt.|  
|[CCmdTarget::EnableConnections](#enableconnections)|Ermöglicht das Auslösen von Ereignissen über Verbindungspunkte.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Ermöglicht die Typbibliothek des Objekts.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Kehrt zum vorherigen Cursor zurück.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Listet die OLE-Verben für ein Objekt.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|Gibt einen Zeiger auf die `CCmdTarget` zugeordnete Objekt der `IDispatch` Zeiger.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Ruft die primäre Dispatch-Schnittstellen-ID.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|Gibt einen Zeiger auf die `IDispatch` zugeordnete Objekt der `CCmdTarget` Objekt.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Ruft die Beschreibung, die der angegebenen GUID entspricht.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|Ruft einen Zeiger auf eine Typbibliothek.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Ruft den Typ-Bibliothek-Cache ab.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Ermöglicht die Automatisierung-Methodenaufruf.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|Gibt einen Wert ungleich NULL, wenn eine Automatisierungsfunktion sollte einen Wert zurückgeben.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Leitet und Command-Meldungen sendet.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Löscht nach Ablauf der letzte OLE-Verweis freigegeben wird.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Sanduhrcursor wird wiederhergestellt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Nachricht-Karte wie Befehle oder Nachrichten, auf die Memberfunktionen, die Sie schreiben, um sie zu behandeln. (Ein Befehl ist eine Nachricht von einem Menüelement Befehlsschaltfläche oder Zugriffstaste.)  
  
 Abgeleitete Klassen-Framework für `CCmdTarget` gehören [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), und [CFrameWnd](../../mfc/reference/cframewnd-class.md). Wenn Sie beabsichtigen eine neue Klasse, die Nachrichten zu verarbeiten, leiten Sie die Klasse von diesen `CCmdTarget`-abgeleitete Klassen. Sie werden nur selten ableiten eine Klasse von `CCmdTarget` direkt.  
  
 Eine Übersicht über Befehlsziele und `OnCmdMsg` routing finden Sie unter [Befehlsziele](../../mfc/command-targets.md), [Befehlsrouting](../../mfc/command-routing.md), und [Zuordnen von Meldungen](../../mfc/mapping-messages.md).  
  
 `CCmdTarget`Memberfunktionen, die die Anzeige von ein Sanduhrcursor umfasst. Sanduhrcursor angezeigt, wenn Sie erwarten, dass einen Befehl eine merkliche Zeitintervall ausgeführt wird.  
  
 Dispatchzuordnungen, Meldungszuordnungstabellen ähnelt, werden verwendet, um OLE-Automatisierung verfügbar machen `IDispatch` Funktionen. Durch diese Schnittstelle verfügbar macht, können andere Anwendungen (z. B. Visual Basic) in Ihrer Anwendung aufrufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor  
 Rufen Sie diese Funktion, um den Cursor als Sanduhr angezeigt, wenn Sie erwarten, dass einen Befehl eine merkliche Zeitintervall ausgeführt wird.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um dem Benutzer zeigt an, dass sie beschäftigt sind, z. B. wenn ein **CDocument** Objekt lädt oder sich in einer Datei gespeichert.  
  
 Die Aktionen der `BeginWaitCursor` sind nicht immer effektiv außerhalb von einem einzelnen Meldungshandler als andere Aktionen wie z. B. `OnSetCursor` behandeln, konnte den Cursor geändert.  
  
 Rufen Sie `EndWaitCursor` zum Wiederherstellen des vorherigen Cursors.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="ccmdtarget"></a>CCmdTarget::CCmdTarget  
 Erstellt ein `CCmdTarget`-Objekt.  
  
```  
CCmdTarget();
```  
  
##  <a name="dooleverb"></a>CCmdTarget::DoOleVerb  
 Bewirkt, dass eine Aktion angegeben, die von einer OLE-Aktion ausgeführt werden.  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Numerische Bezeichner des Verbs.  
  
 `lpMsg`  
 Zeiger auf die [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) Struktur, die Beschreibung des Ereignisses (z. B. ein Doppelklicken), das das Verb aufgerufen hat.  
  
 `hWndParent`  
 Das Handle des Dokumentfensters, das das Objekt enthält.  
  
 `lpRect`  
 Zeiger auf die [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur mit den Koordinaten, in Pixel an, die Definieren eines Objekts umschließenden Rechtecks in *HwndParent*.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508). Die möglichen Aktionen werden von aufgelistet [CCmdTarget::EnumOleVerbs](#enumoleverbs).  
  
##  <a name="enableautomation"></a>CCmdTarget::EnableAutomation  
 Rufen Sie diese Funktion, um OLE-Automatisierung für ein Objekt zu aktivieren.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in der Regel aus dem Konstruktor des Objekts aufgerufen und sollte nur aufgerufen werden, wenn eine Dispatchzuordnung für die Klasse deklariert wurde. Weitere Informationen zur Automatisierung finden Sie in den Artikeln [Automatisierungsclients](../../mfc/automation-clients.md) und [Automatisierungsserver](../../mfc/automation-servers.md).  
  
##  <a name="enableconnections"></a>CCmdTarget::EnableConnections  
 Ermöglicht das Auslösen von Ereignissen über Verbindungspunkte.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>Hinweise  
 Um Verbindungspunkte zu aktivieren, rufen Sie diese Memberfunktion im Konstruktor der abgeleiteten Klasse.  
  
##  <a name="enabletypelib"></a>CCmdTarget::EnableTypeLib  
 Ermöglicht die Typbibliothek des Objekts.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion im Konstruktor Ihrer `CCmdTarget`-abgeleitetes Objekt, wenn sie Typinformationen bereitstellt. Weitere Informationen finden Sie im Knowledge Base-Artikel Q185720, "So wird's gemacht: Bereitstellen von Typinformationen aus MFC-Automatisierungsserver." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor  
 Nachdem Sie aufgerufen haben, rufen Sie diese Funktion die `BeginWaitCursor` Memberfunktion aus Sanduhrcursor auf den vorherigen Cursor zurückgegeben.  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Member-Funktion auch, nachdem Sanduhrcursor aufgerufen wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs  
 Listet die OLE-Verben für ein Objekt.  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `ppenumOleVerb`  
 Ein Zeiger auf einen Zeiger auf eine [IEnumOLEVERB](http://msdn.microsoft.com/library/windows/desktop/ms695084) Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Objekt mindestens ein OLE-Verb unterstützt (in diesem Fall \* `ppenumOleVerb` verweist auf eine **IEnumOLEVERB** Enumeratorschnittstelle), andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject:: EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781).  
  
##  <a name="fromidispatch"></a>CCmdTarget::FromIDispatch  
 Rufen Sie diese Funktion Zuordnen einer `IDispatch` -Zeiger ist, erhalten von Automation-Memberfunktionen einer Klasse, in der `CCmdTarget` -Objekt, das die Schnittstellen implementiert die `IDispatch` Objekt.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDispatch`  
 Ein Zeiger auf ein `IDispatch`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CCmdTarget` zugeordnete Objekt `lpDispatch`. Diese Funktion gibt **NULL** Wenn das `IDispatch` Objekt wird nicht als ein Microsoft Foundation Class erkannt `IDispatch` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Ergebnis dieser Funktion ist die Umkehrung von einem Aufruf der Memberfunktion `GetIDispatch`.  
  
##  <a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID  
 Ruft die primäre Dispatch-Schnittstellen-ID.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>Parameter  
 *pIID*  
 Ein Zeiger auf eine Schnittstellen-ID (eine [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE. Im Erfolgsfall \* *pIID* wird festgelegt, um die primären Dispatch-Schnittstellen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, `GetDispatchIID` gibt FALSE zurück). Finden Sie unter [COleControl](../../mfc/reference/colecontrol-class.md).  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q185720, "So wird's gemacht: Bereitstellen von Typinformationen aus MFC-Automatisierungsserver." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="getidispatch"></a>CCmdTarget::GetIDispatch  
 Rufen Sie diese Memberfunktion zum Abrufen der `IDispatch` Zeiger von einer Automatisierungsmethode gibt entweder ein `IDispatch` Zeiger oder übernimmt eine `IDispatch` Zeiger durch einen Verweis.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>Parameter  
 *bAddRef*  
 Gibt an, ob der Verweiszähler des Objekts inkrementiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IDispatch` Zeiger, die dem Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Um Objekte für diesen Aufruf `EnableAutomation` in ihren Konstruktoren, Automatisierung aktiviert wodurch, diese Funktion einen Zeiger auf die MFC-Implementierung von zurückgibt `IDispatch` , wird von Clients verwendet, die Kommunikation über die `IDispatch` Schnittstelle. Ein Verweis auf den Zeiger Aufrufen dieser Funktion automatisch hinzugefügt werden, daher es nicht notwendig ist, ein Aufruf an [IUnknown:: AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  
  
##  <a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount  
 Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Schnittstellen mit Typinformationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist im Grunde implementiert [IDispatch:: GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12).  
  
 Abgeleitete Klassen überschreiben, sollte diese Funktion, um die Anzahl der Schnittstellen mit Typinformationen bereitgestellt (0 oder 1) zurück. Wenn Sie nicht überschrieben, **Fall** gibt 0 zurück. Verwenden Sie zum Überschreiben der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeLib` und `GetTypeLibCache`.  
  
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
 Gebietsschema-ID ( `LCID`).  
  
 `guid`  
 Die [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931) der Beschreibung des Typs.  
  
 `ppTypeInfo`  
 Zeiger auf einen Zeiger auf die `ITypeInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein HRESULT, das den Erfolg oder Fehler des Aufrufs angibt. Im Erfolgsfall * `ppTypeInfo` verweist auf die Schnittstelle des Typs Informationen.  
  
##  <a name="gettypelib"></a>CCmdTarget::GetTypeLib  
 Ruft einen Zeiger auf eine Typbibliothek.  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>Parameter  
 `lcid`  
 Gebietsschema-ID ( `LCID`).  
  
 `ppTypeLib`  
 Ein Zeiger auf einen Zeiger auf die `ITypeLib` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein HRESULT, das den Erfolg oder Fehler des Aufrufs angibt. Im Erfolgsfall * `ppTypeLib` verweist auf die Schnittstelle der Bibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, `GetTypeLib` TYPE_E_CANTLOADLIBRARY gibt). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLibCache`.  
  
##  <a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache  
 Ruft den Typ-Bibliothek-Cache ab.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine **CTypeLibCache** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, **GetTypeLibCache** gibt NULL zurück). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) -Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLib`.  
  
##  <a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed  
 Diese Funktion wird aufgerufen, durch die Implementierung von MFC **IDispatch:: Invoke** bestimmen, ob eine angegebene Automatisierungsmethode (identifiziert durch `dispid`) aufgerufen werden kann.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Eine Dispatch-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Methode aufgerufen wurde, andernfalls "false" sein kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `IsInvokeAllowed` gibt TRUE zurück, **Invoke** fährt mit der Methodenaufruf; andernfalls `Invoke` fehl und gibt E_UNEXPECTED zurück.  
  
 Abgeleitete Klassen können überschreiben diese Funktion, um die entsprechenden Werte zurück (wenn nicht überschrieben, `IsInvokeAllowed` gibt TRUE zurück). Siehe insbesondere [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).  
  
##  <a name="isresultexpected"></a>CCmdTarget::IsResultExpected  
 Verwendung `IsResultExpected` zu ermitteln, ob ein Client einen Rückgabewert von seinem Aufruf an eine Automatisierungsfunktion erwartet.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Automatisierungsfunktion einen Wert zurückgeben sollte; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die OLE-Schnittstelle stellt Informationen zum MFC darüber, ob der Client verwenden oder das Ergebnis eines Funktionsaufrufs ignoriert und MFC verwendet diese Informationen wiederum bestimmt das Ergebnis eines Aufrufs von `IsResultExpected`. Wenn die Produktion eines Rückgabewerts oder Ressourcen-zeitaufwändig, können Sie die Effizienz durch Aufrufen dieser Funktion vor dem Berechnen des Rückgabewerts erhöhen.  
  
 Diese Funktion gibt 0 zurück, nur einmal so, dass Sie gültige Rückgabewerte von anderen Automatisierungsfunktionen erhalten, wenn Sie sie aus der Automatisierungsfunktion Aufrufen des Clients aufgerufen hat.  
  
 `IsResultExpected`Gibt einen Wert ungleich NULL zurück, wenn aufgerufen, wenn ein Funktionsaufruf Automatisierung nicht ausgeführt wird.  
  
##  <a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg  
 Vom Framework zum Weiterleiten und verteilen Befehl Nachrichten und zum Behandeln der Aktualisierung der Benutzeroberfläche Befehlsobjekte aufgerufen.  
  
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
 Identifiziert den Befehl Benachrichtigungscode. Finden Sie unter **Hinweise** Weitere Informationen zu den Werten für `nCode`.  
  
 `pExtra`  
 Entsprechend dem Wert der verwendeten `nCode`. Finden Sie unter **Hinweise** Weitere Informationen zu `pExtra`.  
  
 `pHandlerInfo`  
 Wenn nicht **NULL**, `OnCmdMsg` füllt die **pTarget** und **Pmf** Mitglieder der `pHandlerInfo` Struktur, anstatt den Befehl zu verteilen. Dieser Parameter sollte in der Regel **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist die Haupt-Implementierung-Routine, die Architektur der Framework-Befehl.  
  
 Zur Laufzeit `OnCmdMsg` sendet einen Befehl auf andere Objekte oder den Befehl selbst-handles durch Aufrufen der Stammklasse `CCmdTarget::OnCmdMsg`, welche die tatsächliche meldungszuordnung-Suche. Eine vollständige Beschreibung der Standard-Befehlsrouting, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
 In seltenen Fällen sollten Sie diese Memberfunktion zum Erweitern des Frameworks überschreiben standardbefehlsroutings. Finden Sie unter [Technische Hinweis 21](../../mfc/tn021-command-and-message-routing.md) für erweiterte Details der Befehlsrouting Architektur.  
  
 Wenn Sie außer Kraft setzen `OnCmdMsg`, müssen Sie den entsprechenden Wert für angeben `nCode`, den Benachrichtigungscode Befehl und `pExtra`, hängt der Wert des `nCode`. In der folgenden Tabelle werden die entsprechenden Werte aufgeführt:  
  
|`nCode`-Wert|`pExtra`-Wert|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|AUFGERUFEN|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#44;](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#45;](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease  
 Wird vom Framework aufgerufen, wenn die letzte OLE-Verweis zum oder vom Objekt freigegeben wird.  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um eine besondere Behandlung für diese Situation bereitstellen. Die standardmäßige Implementierung wird das Objekt gelöscht.  
  
##  <a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor  
 Rufen Sie diese Funktion, um die entsprechenden Sanduhrcursor wiederherzustellen, nachdem der Systemcursor geändert wurde (z. B. nachdem ein Meldungsfeld geöffnet und dann mitten in einem langwierigen Vorgang geschlossen wurden).  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ACDUAL-Beispiel](../../visual-cpp-samples.md)   
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

