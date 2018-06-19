---
title: CWindowImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4884bbacd03675d00cb1a49b937265ab5faa2835
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366155"
---
# <a name="cwindowimpl-class"></a>CWindowImpl-Klasse
Stellt Methoden für das Erstellen eines Fensters oder von Unterklassen eines Fensters bereit  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die neue Klasse, die von `CWindowImpl` abgeleitet ist.  
  
 *TBase*  
 Die Basisklasse der Klasse. Standardmäßig ist die Basisklasse [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 Ein [Merkmalklasse](../../atl/understanding-window-traits.md) , Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWindowImpl:: Create](#create)|Erstellt ein Fenster.|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT-Methoden  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|  
|[GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|  
|[GetWindowProc](#getwindowproc)|Gibt die aktuelle Fensterprozedur zurück.|  
|[OnFinalMessage](#onfinalmessage)|Wird nach dem Empfang der letzten Nachricht aufgerufen (in der Regel `WM_NCDESTROY`).|  
|[SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|  
|[UnsubclassWindow auf](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|  
  
### <a name="static-methods"></a>Statische Methoden  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|Gibt eine statische Instanz [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), der die fensterklasseninformationen verwaltet.|  
|[WindowProc](#windowproc)|Verarbeitet die Nachrichten, die an das Fenster gesendet werden.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können `CWindowImpl` ein Fenster oder Unterklassen ein vorhandenes Fenster erstellen. die `CWindowImpl` Fensterprozedur eine meldungszuordnung zur Weiterleitung von Nachrichten an die entsprechenden Handler verwendet.  
  
 `CWindowImpl::Create` erstellt ein Fenster, die Grundlage der fensterklasseninformationen, die von verwalteten [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` enthält die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) -Makro, das bedeutet, dass `CWndClassInfo` eine neue Fensterklasse registriert. Wenn Sie eine vorhandene Fensterklasse überordnen Informationen möchten, leiten Sie eine Klasse von `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro. In diesem Fall wird mit `CWndClassInfo` eine Fensterklasse registriert, die auf einer vorhandenen Klasse basiert, aber `CWindowImpl::WindowProc` verwendet. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Da `CWndClassInfo` nur die Informationen für eine Fensterklasse verwaltet, basiert jedes Fenster, das durch eine Instanz von `CWindowImpl` erstellt wird, auf der gleichen Fensterklasse.  
  
 `CWindowImpl` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CWindowImpl`-Objekt an und ändert die Fensterprozedur in `CWindowImpl::WindowProc`. Jede Instanz von `CWindowImpl` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Für jedes `CWindowImpl` Objekt, rufen Sie entweder **erstellen** oder `SubclassWindow`. Rufen Sie nicht beide Methoden für dasselbe Objekt auf.  
  
 Zusätzlich zu `CWindowImpl`, ATL stellt [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) So erstellen in einem anderen Objekt ein Fenster, das enthalten ist.  
  
 Basisklassendestruktor (~ **CWindowImplRoot**) wird sichergestellt, dass das Fenster verfügbar wird, bevor das Objekt zerstört wird.  
  
 `CWindowImpl` leitet sich von **CWindowImplBaseT**, die sich daraus ableitet **CWindowImplRoot**, die sich daraus ableitet **TBase** und [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------|---------|  
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="create"></a>  CWindowImpl:: Create  
 Erstellt ein Fenster, die basierend auf einem neuen Fensterklasse.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle für das Fenster übergeordnete oder Besitzer.  
  
 `rect`  
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` als Zeiger oder Verweis übergeben werden kann.  
  
 `szWindowName`  
 [in] Gibt den Namen des Fensters. Der Standardwert ist **NULL**.  
  
 `dwStyle`  
 [in] Der Stil des Fensters. Dieser Wert wird in dem Format, das von der Klasse "traits" bereitgestellt wird, für das Fenster kombiniert. Der Standardwert gibt die Merkmale Klasse volle Kontrolle über das Format. Eine Liste der möglichen Werte finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) im Windows SDK.  
  
 `dwExStyle`  
 [in] Der erweiterte Fensterstil. Dieser Wert wird in dem Format, das von der Klasse "traits" bereitgestellt wird, für das Fenster kombiniert. Der Standardwert gibt die Merkmale Klasse volle Kontrolle über das Format. Eine Liste der möglichen Werte finden Sie unter [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `MenuOrID`  
 [in] Für ein untergeordnetes Fenster, das Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menü-Handle für das Fenster. Der Standardwert ist **0 HE**.  
  
 `lpCreateParam`  
 [in] Ein Zeiger auf fenstererstellung Daten. Eine vollständige Beschreibung finden Sie in der Beschreibung für den letzten Parameter in [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle für das neu erstellte Fenster. Andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** zuerst die Fensterklasse registriert, wenn er noch nicht registriert wurde. Das neu erstellte Fenster wird automatisch angefügt, um die `CWindowImpl` Objekt.  
  
> [!NOTE]
>  Rufen Sie nicht **erstellen** , wenn Sie bereits aufgerufen haben [SubclassWindow](#subclasswindow).  
  
 Um eine Fensterklasse zu verwenden, die auf eine vorhandene Fensterklasse überordnen basieren, leiten Sie eine Klasse von `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro. Die vorhandene Fensterklasse überordnen Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc). Weitere Informationen finden Sie unter der [CWindowImpl](../../atl/reference/cwindowimpl-class.md) (Übersicht).  
  
> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die `MenuOrID` Parameter, es muss angegeben werden, als 0 HE (Standardwert) um einen Compilerfehler zu vermeiden.  
  
##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc  
 Wird aufgerufen, indem [WindowProc](#windowproc) zum Verarbeiten von Nachrichten von der nachrichtenzuordnung nicht verarbeitet.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
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
  
 Die Funktion ohne Parameter ruft automatisch die erforderlichen Parameter aus der aktuellen Nachricht ab.  
  
##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage  
 Gibt die aktuelle Nachricht, verpackt in die `MSG` Struktur.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Nachricht.  
  
##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc  
 Gibt `WindowProc`, die aktuelle Fensterprozedur.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Fensterprozedur.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Fensterprozedur durch eigene ersetzen.  
  
##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo  
 Wird aufgerufen, indem [erstellen](#create) auf die fensterklasseninformationen zugreifen.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine statische Instanz [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `CWindowImpl` ruft diese Methode über die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) -Makro, das eine neue Fensterklasse angibt.  
  
 Auf der übergeordneten Klasse eine vorhandene Fensterklasse überordnen, leiten Sie eine Klasse von `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro überschreiben `GetWndClassInfo`. Weitere Informationen finden Sie unter der [CWindowImpl](../../atl/reference/cwindowimpl-class.md) (Übersicht).  
  
 Neben der Verwendung der `DECLARE_WND_CLASS` und `DECLARE_WND_SUPERCLASS` Makros, die Sie überschreiben `GetWndClassInfo` mit Ihrer eigenen Implementierung.  
  
##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc  
 Abhängig vom Fenster verweist auf eines der folgenden Verfahren Fenster.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Hinweise  
  
|Fenstertyp|Fensterprozedur|  
|--------------------|----------------------|  
|Ein Fenster basierend auf eine neue Windows-Klasse, angegeben durch die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) Makro.|Die [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32-Funktion.|  
|Ein Fenster auf der Grundlage von einer Fensterklasse, die eine vorhandene Klasse, die durch die angegebenen ändert die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro.|Die vorhandenen des Fensterprozedur der Fensterklasse.|  
|Ein untergeordnetes Fenster.|Ursprüngliche Fensterprozedur der der untergeordnetes Fenster.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) sendet Nachrichten Informationen an die Fensterprozedur in gespeicherten `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage  
 Nach dem Empfang der letzten Nachricht aufgerufen (in der Regel `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Ein Handle für das Fenster zerstört wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `OnFinalMessage` wird keine Aktion ausgeführt, aber Sie können diese Funktion, um die Bereinigung zu verarbeiten, bevor die Zerstören eines Fensters überschreiben. Wenn Ihr Objekt auf die fensterzerstörung automatisch gelöscht werden sollen, können Sie aufrufen `delete this;` in dieser Funktion.  
  
##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow  
 Unterklassen des Fensters identifizierten `hWnd` und fügt es der `CWindowImpl` Objekt.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Fenster wird als Unterklasse.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn das Fenster, erfolgreich untergeordnetes; andernfalls ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Untergeordnete Fenster jetzt unter Verwendung der [CWindowImpl:: WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Rufen Sie nicht `SubclassWindow` , wenn Sie bereits aufgerufen haben [erstellen](#create).  
  
##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow  
 Trennt die untergeordnete Fenster von der `CWindowImpl` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Fenster, das zuvor als Unterklasse.  
  
##  <a name="windowproc"></a>  CWindowImpl:: WindowProc  
 Diese statische Funktion implementiert die Fensterprozedur.  
  
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
 `WindowProc` verwendet die Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) zur Weiterleitung von Nachrichten an die entsprechenden Handler. Bei Bedarf `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für zusätzliche Nachrichtenverarbeitung. Wenn die endgültige Nachricht nicht behandelt wird, `WindowProc` bewirkt Folgendes:  
  
-   Führt unsubclassing, wenn das Fenster unsubclassed wurde.  
  
-   Löscht `m_hWnd`.  
  
-   Aufrufe [OnFinalMessage](#onfinalmessage) bevor das Fenster zerstört wird.  
  
 Sie können außer Kraft setzen `WindowProc` angeben ein anderen Mechanismus zum Verarbeiten von Nachrichten.  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
