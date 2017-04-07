---
title: CWindowImpl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 76827682e96d2aea80880fa7d70c267abe02ee1c
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowimpl-class"></a>CWindowImpl-Klasse
Stellt Methoden für das Erstellen eines Fensters oder von Unterklassen eines Fensters bereit  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
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
 Ein ["traits"-Klasse](../../atl/understanding-window-traits.md) , die Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.  
  
## <a name="members"></a>Mitglieder  
  
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
 Sie können `CWindowImpl` ein Fenster oder eine Unterklasse ein vorhandenes Fenster erstellen. die `CWindowImpl` Fensterprozedur verwendet eine nachrichtenzuordnung, um Nachrichten an die entsprechenden Handler zu leiten.  
  
 `CWindowImpl::Create`erstellt ein Fenster, das anhand der Informationen der Fenster-Klasse, die von verwalteten [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl`enthält die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) -Makro, das bedeutet, dass `CWndClassInfo` eine neue Fensterklasse registriert. Wenn Sie eine vorhandene Fensterklasse überordnen möchten, leiten Sie eine Klasse von `CWindowImpl` und die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro. In diesem Fall wird mit `CWndClassInfo` eine Fensterklasse registriert, die auf einer vorhandenen Klasse basiert, aber `CWindowImpl::WindowProc` verwendet. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Da `CWndClassInfo` nur die Informationen für eine Fensterklasse verwaltet, basiert jedes Fenster, das durch eine Instanz von `CWindowImpl` erstellt wird, auf der gleichen Fensterklasse.  
  
 `CWindowImpl` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CWindowImpl`-Objekt an und ändert die Fensterprozedur in `CWindowImpl::WindowProc`. Jede Instanz von `CWindowImpl` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Für jeden angegebenen `CWindowImpl` Objekt, rufen Sie entweder **erstellen** oder `SubclassWindow`. Rufen Sie nicht beide Methoden für dasselbe Objekt auf.  
  
 Zusätzlich zu `CWindowImpl`, ATL stellt [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) ein Fenster, das enthalten ist in einem anderen Objekt erstellen.  
  
 Basisklassendestruktor (~ **CWindowImplRoot**) wird sichergestellt, dass das Fenster nicht mehr vorhanden ist, bevor das Objekt zerstört wird.  
  
 `CWindowImpl`leitet sich von **CWindowImplBaseT**, die sich daraus ableitet **CWindowImplRoot**, abgeleitet, das von **TBase** und [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
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
 **Header:** atlwin.h  
  
##  <a name="create"></a>CWindowImpl:: Create  
 Erstellt ein Fenster basierend auf einer neuen Fensterklasse.  
  
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
 [in] Das Handle für das übergeordnete Fenster oder das Besitzer.  
  
 `rect`  
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` Zeiger oder Verweis übergeben werden kann.  
  
 `szWindowName`  
 [in] Gibt den Namen des Fensters. Der Standardwert ist **NULL**.  
  
 `dwStyle`  
 [in] Der Stil des Fensters. Dieser Wert wird mit dem durch die "traits"-Klasse für das Fenster bereitgestellten Stil kombiniert. Der Standardwert bietet die "traits"-Klasse vollständige Kontrolle über das Format. Eine Liste der möglichen Werte finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Der erweiterte Fensterstil. Dieser Wert wird mit dem durch die "traits"-Klasse für das Fenster bereitgestellten Stil kombiniert. Der Standardwert bietet die "traits"-Klasse vollständige Kontrolle über das Format. Eine Liste der möglichen Werte finden Sie unter [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Für ein untergeordnetes Fenster, das Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menü-Handle für das Fenster. Der Standardwert ist **0 HE**.  
  
 `lpCreateParam`  
 [in] Ein Zeiger auf die Daten im Fenster erstellen. Eine vollständige Beschreibung finden Sie in der Beschreibung der letzte Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Rückgabewert  
 Falls erfolgreich, das Handle für das neu erstellte Fenster. Andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** zuerst die Fensterklasse registriert, wenn er noch nicht registriert wurde. Das neu erstellte Fenster wird automatisch angefügt, um die `CWindowImpl` Objekt.  
  
> [!NOTE]
>  Rufen Sie **erstellen** Wenn Sie bereits aufgerufen [SubclassWindow](#subclasswindow).  
  
 Um eine Windows-Klasse verwenden, die auf eine vorhandene Fensterklasse basiert, leiten Sie eine Klasse von `CWindowImpl` und die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro. Die vorhandene Fensterklasse Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc). Weitere Informationen finden Sie unter der [CWindowImpl](../../atl/reference/cwindowimpl-class.md) (Übersicht).  
  
> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die `MenuOrID` -Parameter muss als 0 HE angegeben werden (Standardwert), einen Compilerfehler zu vermeiden.  
  
##  <a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 Aufgerufen von [WindowProc](#windowproc) zum Verarbeiten von Nachrichten durch die Zuordnung der Nachricht nicht verarbeitet.  
  
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
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Verarbeitung der Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `DefWindowProc` Aufrufe der [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) Win32-Funktion zum Senden von Informationen der Nachricht an die Fensterprozedur in angegebenen [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
 Die Funktion keine Parameter übernimmt automatisch die erforderlichen Parameter aus der aktuellen Nachricht.  
  
##  <a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 Gibt die aktuelle Nachricht, verpackt in die `MSG` Struktur.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Nachricht.  
  
##  <a name="getwindowproc"></a>CWindowImpl::GetWindowProc  
 Gibt `WindowProc`, die aktuelle Fensterprozedur.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Fensterprozedur.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Fensterprozedur durch Ihren eigenen ersetzen.  
  
##  <a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 Aufgerufen von [erstellen](#create) auf die fensterklasseninformationen zugreifen.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine statische Instanz [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CWindowImpl` ruft diese Methode über die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) -Makro, das eine neue Windows-Klasse angibt.  
  
 Um eine vorhandene Fensterklasse überordnen, leiten Sie eine Klasse von `CWindowImpl` und die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro überschreiben `GetWndClassInfo`. Weitere Informationen finden Sie unter der [CWindowImpl](../../atl/reference/cwindowimpl-class.md) (Übersicht).  
  
 Neben der Verwendung der `DECLARE_WND_CLASS` und `DECLARE_WND_SUPERCLASS` Makros, die Sie überschreiben `GetWndClassInfo` durch eine eigene Implementierung.  
  
##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 Abhängig vom Fenster zeigt auf eines der folgenden Verfahren Fenster.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Hinweise  
  
|Typ des Fensters|Window-Prozedur|  
|--------------------|----------------------|  
|Ein Fenster basierend auf einer neuen Fensterklasse, angegeben durch die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) Makro.|Die [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32-Funktion.|  
|Ein Fenster auf der Grundlage von einer Fensterklasse, die eine vorhandene Klasse, die durch angegebene ändert die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro.|Die vorhandene Fensterklasse Fensterprozedur.|  
|Ein untergeordnetes Fenster.|Ursprüngliche Fensterprozedur der der untergeordnetes Fenster.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) Informationen an die Fensterprozedur in gespeicherte Nachricht `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 Nach dem Empfang der letzten Nachricht aufgerufen (in der Regel `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Ein Handle für das Fenster zerstört wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `OnFinalMessage` wird keine Aktion ausgeführt, aber Sie können diese Funktion, um die Bereinigung zu verarbeiten, bevor die Zerstörung eines Fensters überschreiben. Wenn das Objekt nach dem Zerstören automatisch gelöscht werden sollen, können Sie aufrufen `delete this;` in dieser Funktion.  
  
##  <a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 Unterklassen des Fensters identifizierten `hWnd` und fügt es der `CWindowImpl` Objekt.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Fenster erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist das Fenster erfolgreich Unterklassen, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Untergeordnete Fenster verwendet jetzt [CWindowImpl:: WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Rufen Sie `SubclassWindow` , wenn Sie bereits aufgerufen [erstellen](#create).  
  
##  <a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 Trennt die untergeordnete Fenster aus der `CWindowImpl` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Fenster, das zuvor als Unterklasse.  
  
##  <a name="windowproc"></a>CWindowImpl:: WindowProc  
 Die statische Funktion implementiert die Fensterprozedur.  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Fenster.  
  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Verarbeitung der Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 `WindowProc`verwendet die Standard-Nachricht-Zuordnung (deklariert mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)), Nachrichten an die entsprechenden Handler zu leiten. Falls erforderlich, `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für die weitere Verarbeitung. Wenn die letzte Meldung nicht behandelt wird, `WindowProc` bewirkt Folgendes:  
  
-   Führt unsubclassing, wenn das Fenster unsubclassed war.  
  
-   Löscht `m_hWnd`.  
  
-   Aufrufe [OnFinalMessage](#onfinalmessage) , bevor das Fenster zerstört wird.  
  
 Sie können außer Kraft setzen `WindowProc` unterschiedliche Mechanismen für die Verarbeitung von Nachrichten angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

