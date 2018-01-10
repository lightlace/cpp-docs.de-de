---
title: CContainedWindow Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs: C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cf792fed2f7a5cac45826649224a565228f9d73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccontainedwindowt-class"></a>CContainedWindow-Klasse
Diese Klasse implementiert ein Fenster innerhalb eines anderen Objekts enthalten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Parameter  
 *TBase*  
 Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist `CWindow`.  
  
 `TWinTraits`  
 Eine trait-Klasse, die Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) ist eine Spezialisierung der `CContainedWindowT`. Wenn Sie die Basisklasse oder die Merkmale ändern möchten, verwenden Sie `CContainedWindowT` direkt.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Konstruktor. Initialisiert die Datenmember aus, um anzugeben, welche meldungszuordnung enthaltenen fenstermeldungen verarbeitet werden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindow:: Create auf](#create)|Erstellt ein Fenster.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Registriert die Fensterklasse des Fensters enthalten.|  
|[SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Ändert die meldungszuordnung verwendet wird, um die eigenständigen Windows-Meldungen zu verarbeiten.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Statisch) Verarbeitet die Nachrichten gesendet, um den im Fenster.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Gibt an, welche meldungszuordnung enthaltenen fenstermeldungen verarbeitet werden.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Gibt den Namen einer vorhandenen Fenster-Klasse, die auf dem eine neue Fensterklasse basieren soll.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Verweist auf des enthaltenden Objekts.|  
  
## <a name="remarks"></a>Hinweise  
 `CContainedWindowT`implementiert ein Fenster innerhalb eines anderen Objekts enthalten. `CContainedWindowT`der Fenster Beispielprozedur verwendet, die eine Nachricht im des enthaltenden Objekts direkte Nachrichten an die entsprechenden Handler zugeordnet werden. Beim Erstellen einer `CContainedWindowT` -Objekts können Sie angeben, welche meldungszuordnung verwendet werden soll.  
  
 `CContainedWindowT`ermöglicht Ihnen die Erstellung ein neues Fensters durch Erstellen von übergeordneten Klassen eine vorhandene Fensterklasse überordnen. Die **erstellen** Methode registriert zuerst eine Fensterklasse, die auf einer vorhandenen Klasse basiert, verwendet jedoch `CContainedWindowT::WindowProc`. **Erstellen Sie** erstellt dann ein Fenster, die basierend auf diesem neuen Fensterklasse. Jede Instanz des `CContainedWindowT` können Sie die übergeordnete Klasse eine unterschiedliche Fensterklasse.  
  
 `CContainedWindowT` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CContainedWindowT`-Objekt an und ändert die Fensterprozedur in `CContainedWindowT::WindowProc`. Jede Instanz von `CContainedWindowT` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Für jedes `CContainedWindowT` Objekt, rufen Sie entweder **erstellen** oder `SubclassWindow`. Sie sollten nicht beide Methoden für dasselbe Objekt aufrufen.  
  
 Bei Verwendung der **Hinzufügen des Steuerelements basierend auf** option im ATL-Projekt-Assistenten vom Assistenten werden automatisch hinzugefügt. eine `CContainedWindowT` Datenmember der Klasse, die das Steuerelement implementieren. Das folgende Beispiel zeigt, wie das eigenständige Fenster deklariert wird:  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------|---------|  
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) und nachfolgenden Themen im Windows SDK|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 Der Konstruktor initialisiert die Datenmember.  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 [in] Der Name einer vorhandenen Fenster-Klasse, die auf dem Fenster enthaltenen basieren soll.  
  
 `pObject`  
 [in] Ein Zeiger auf das enthaltende Objekt, das die meldungszuordnung deklariert. Klasse des Objekts abgeleitet muss [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Identifiziert die meldungszuordnung, die die eigenständigen Windows-Meldungen verarbeitet. Der Standardwert 0 (null) gibt an, die deklariert mit Standard-meldungszuordnung [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Verwenden Sie einen alternativen meldungszuordnung deklariert, mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie, beim Erstellen eines neuen Fensters über möchten [erstellen](#create), müssen Sie den Namen der eine vorhandene Fensterklasse überordnen für übergeben der `lpszClassName` Parameter. Ein Beispiel finden Sie die [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
 Es gibt drei Konstruktoren:  
  
-   Der Konstruktor mit drei Argumenten ist in der Regel aufgerufen.  
  
-   Der Konstruktor mit zwei Argumenten verwendet den Klassennamen aus **TBase::GetWndClassName**.  
  
-   Der Konstruktor ohne Argumente wird verwendet, wenn Sie später die Argumente angeben möchten. Sie müssen die Fenster-Klassennamen, die Nachricht Map-Objekt und die Nachricht Zuordnungs-ID angeben, wenn Sie später Aufrufen **erstellen**.  
  
 Wenn Sie ein vorhandenes Fenster Unterklasse über [SubclassWindow](#subclasswindow), die `lpszClassName` Wert wird nicht verwendet werden; Sie können daher übergeben **NULL** für diesen Parameter.  
  
##  <a name="create"></a>CContainedWindow:: Create auf  
 Aufrufe [RegisterWndSuperclass](#registerwndsuperclass) eine Fensterklasse registriert, die auf einer vorhandenen Klasse basiert, verwendet jedoch [CContainedWindowT::WindowProc](#windowproc).  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 [in] Der Name einer vorhandenen Fenster-Klasse, die auf dem Fenster enthaltenen basieren soll.  
  
 `pObject`  
 [in] Ein Zeiger auf das enthaltende Objekt, das die meldungszuordnung deklariert. Klasse des Objekts abgeleitet muss [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Identifiziert die meldungszuordnung, die die eigenständigen Windows-Meldungen verarbeitet. Der Standardwert 0 (null) gibt an, die deklariert mit Standard-meldungszuordnung [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Verwenden Sie einen alternativen meldungszuordnung deklariert, mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.  
  
 `hWndParent`  
 [in] Das Handle für das Fenster übergeordnete oder Besitzer.  
  
 `rect`  
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` als Zeiger oder Verweis übergeben werden kann.  
  
 `szWindowName`  
 [in] Gibt den Namen des Fensters. Der Standardwert ist **NULL**.  
  
 `dwStyle`  
 [in] Der Stil des Fensters. Der Standardwert ist **WS_CHILD &#124; WS_VISIBLE**. Eine Liste der möglichen Werte finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) im Windows SDK.  
  
 `dwExStyle`  
 [in] Der erweiterte Fensterstil. Der Standardwert ist 0, d. h. keine erweiterten Stil. Eine Liste der möglichen Werte finden Sie unter [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `MenuOrID`  
 [in] Für ein untergeordnetes Fenster, das Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menü-Handle für das Fenster. Der Standardwert ist **0 HE**.  
  
 `lpCreateParam`  
 [in] Ein Zeiger auf fenstererstellung Daten. Eine vollständige Beschreibung finden Sie in der Beschreibung für den letzten Parameter in [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle für das neu erstellte Fenster; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Der Name des vorhandenen Klasse wird gespeichert, [M_lpszClassName](#m_lpszclassname). **Erstellen Sie** erstellt dann ein Fenster, die basierend auf diese neue Klasse. Das neu erstellte Fenster wird automatisch angefügt, um die `CContainedWindowT` Objekt.  
  
> [!NOTE]
>  Rufen Sie nicht **erstellen** , wenn Sie bereits aufgerufen haben [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die `MenuOrID` Parameter, es muss angegeben werden, als 0 HE (Standardwert) um einen Compilerfehler zu vermeiden.  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Wird aufgerufen, indem [WindowProc](#windowproc) zum Verarbeiten von Nachrichten von der nachrichtenzuordnung nicht verarbeitet.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Nachrichtenverarbeitung.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `DefWindowProc` Aufrufe der [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) Win32-Funktion zum Senden der Nachrichteninformationen an die Fensterprozedur in angegebenen [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Gibt die aktuelle Nachricht zurück ( **M_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Nachricht, verpackt in die `MSG` Struktur.  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Enthält den Bezeichner der meldungszuordnung, die zurzeit für den im Fenster verwendet werden.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese nachrichtenzuordnung muss in dem Objekt deklariert werden.  
  
 Die Standard-meldungszuordnung deklariert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), immer von 0 (null) bezeichnet wird. Eine alternative meldungszuordnung deklariert mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), wird durch identifiziert `msgMapID`.  
  
 `m_dwMsgMapID`wird zuerst vom Konstruktor initialisiert und kann geändert werden, durch den Aufruf [SwitchMessageMap](#switchmessagemap). Ein Beispiel finden Sie die [CContainedWindow Übersicht](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Gibt den Namen einer vorhandenen Fenster-Klasse.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Erstellung eines Fensters [erstellen](#create) registriert eine neue Windows-Klasse, die auf diese vorhandene Klasse basiert, verwendet jedoch [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie die [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Wenn die enthaltenen Fenster als Unterklasse definiert ist, `m_pfnSuperWindowProc` verweist auf die ursprüngliche Fensterprozedur der Fensterklasse.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die enthaltenen Fenster Komponente ist, d. h. sie basiert auf eine Fensterklasse, die eine vorhandene Klasse ändert `m_pfnSuperWindowProc` verweist auf die vorhandenen des Fensterprozedur der Fensterklasse.  
  
 Die [DefWindowProc](#defwindowproc) Methode sendet die Nachrichteninformationen an die Fensterprozedur in gespeicherten `m_pfnSuperWindowProc`.  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 Verweist auf das Objekt mit dem `CContainedWindowT` Objekt.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Container, dessen Klasse ableiten muss [CMessageMap](../../atl/reference/cmessagemap-class.md), deklariert die meldungszuordnung, die von den im Fenster verwendet.  
  
 `m_pObject`wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie die [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Wird aufgerufen, indem [erstellen](#create) Fensterklasse des Fensters enthaltenen zu registrieren.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung eines Atom eindeutig identifiziert, die Fensterklasse registriert werden; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Fensterklasse verwendet jedoch basiert auf einer vorhandenen Klasse [CContainedWindowT::WindowProc](#windowproc). Vorhandene Fensterklasse überordnen Name und Fenster-Prozedur sind gespeichert [M_lpszClassName](#m_lpszclassname) und [M_pfnSuperWindowProc](#m_pfnsuperwindowproc)zugeordnet.  
  
##  <a name="subclasswindow"></a>SubclassWindow  
 Unterklassen des Fensters identifizierten `hWnd` und fügt es der `CContainedWindowT` Objekt.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Fenster wird als Unterklasse.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn das Fenster, erfolgreich untergeordnetes; andernfalls ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Untergeordnete Fenster jetzt unter Verwendung der [CContainedWindowT::WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Rufen Sie nicht `SubclassWindow` , wenn Sie bereits aufgerufen haben [erstellen](#create).  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Ändert die meldungszuordnung zum Verarbeiten von Nachrichten von den im Fenster verwendet wird.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMsgMapID`  
 [in] Der Meldungsbezeichner Zuordnung. Verwenden Sie die Standard-meldungszuordnung deklariert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), übergeben Sie 0 (null). Verwenden Sie einen alternativen meldungszuordnung deklariert, mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.  
  
### <a name="remarks"></a>Hinweise  
 Die meldungszuordnung muss in der enthaltenden Objekts definiert werden.  
  
 Legen Sie zu Beginn der Zuordnung Meldungsbezeichner im Konstruktor.  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Trennt die untergeordnete Fenster von der `CContainedWindowT` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bForce`  
 [in] Legen Sie auf **"true"** erzwingen Sie die ursprüngliche Fensterprozedur der wiederherzustellenden selbst wenn die Fensterprozedur für diesen `CContainedWindowT` Objekt ist nicht aktiv. Wenn `bForce` festgelegt ist, um **"false"** und die Fensterprozedur für diesen `CContainedWindowT` Objekt ist nicht aktiv, wird die ursprüngliche Fensterprozedur wird nicht wiederhergestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Fenster, das zuvor als Unterklasse. Wenn `bForce` festgelegt ist, um **"false"** und die Fensterprozedur für diesen `CContainedWindowT` Objekt ist nicht aktiv ist, wird **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur, wenn Sie möchten, um die ursprüngliche Fensterprozedur wiederherzustellen, bevor das Fenster zerstört wird. Andernfalls [WindowProc](#windowproc) wird automatisch dies geschieht, wenn das Fenster zerstört wird.  
  
##  <a name="windowproc"></a>CContainedWindowT::WindowProc  
 Diese statische Methode implementiert die Fensterprozedur.  
  
```
static LRESULT CALLBACK WindowProc(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle des Fensters.  
  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Nachrichtenverarbeitung.  
  
### <a name="remarks"></a>Hinweise  
 `WindowProc`leitet Nachrichten an die identifizierte meldungszuordnung [M_dwMsgMapID](#m_dwmsgmapid). Bei Bedarf `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für zusätzliche Nachrichtenverarbeitung.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindow-Klasse](../../atl/reference/cwindow-class.md)   
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap-Klasse](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
