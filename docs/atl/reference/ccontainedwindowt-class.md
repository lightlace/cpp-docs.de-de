---
title: CContainedWindow Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindow
- CContainedWindowT
- ATL.CContainedWindowT
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e10aa4b455696fd217f88b6eb1de2421fccda6de
ms.lasthandoff: 02/24/2017

---
# <a name="ccontainedwindowt-class"></a>CContainedWindow-Klasse
Diese Klasse implementiert ein Fenster in einem anderen Objekt enthalten sind.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Parameter  
 *TBase*  
 Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist `CWindow`.  
  
 `TWinTraits`  
 Eine "traits"-Klasse, die Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) ist eine Spezialisierung von `CContainedWindowT`. Wenn Sie die Basisklasse oder die Merkmale ändern möchten, verwenden Sie `CContainedWindowT` direkt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Konstruktor. Initialisiert die Datenelemente, um anzugeben, welche Nachricht Zuordnung den im Fenster Nachrichten verarbeitet werden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindow:: Create auf](#create)|Erstellt ein Fenster.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Registriert die Fensterklasse des Fensters enthalten.|  
|[SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Ändert die Zuordnung der Nachricht verwendet wird, zum Verarbeiten von Nachrichten mit den im Fenster.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Statisch) Verarbeitet die Nachrichten an den im Fenster.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Gibt an, welche meldungszuordnung den im Fenster Nachrichten verarbeitet werden.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Gibt den Namen für eine vorhandene Fensterklasse, auf der eine neue Windows-Klasse basieren soll.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Verweist auf das enthaltende Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CContainedWindowT`implementiert ein Fenster in einem anderen Objekt enthalten sind. `CContainedWindowT`einer Fenster Prozedur verwendet, die eine Nachricht in dem Objekt direkten Nachrichten an die entsprechenden Handler zugeordnet. Beim Erstellen einer `CContainedWindowT` -Objekts können Sie angeben, welche meldungszuordnung verwendet werden soll.  
  
 `CContainedWindowT`können Sie ein neues Fenster durch Erstellen von übergeordneten Klassen erstellen, eine vorhandene Fensterklasse. Die **erstellen** Methode zum ersten Mal eine Fensterklasse, die auf einer vorhandenen Klasse basiert, verwendet jedoch registriert `CContainedWindowT::WindowProc`. **Erstellen Sie** erstellt dann ein Fenster basierend auf dieser neuen Fensterklasse. Jede Instanz des `CContainedWindowT` können Sie die übergeordnete Klasse eine andere Windows-Klasse.  
  
 `CContainedWindowT` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CContainedWindowT`-Objekt an und ändert die Fensterprozedur in `CContainedWindowT::WindowProc`. Jede Instanz von `CContainedWindowT` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Für jeden angegebenen `CContainedWindowT` Objekt, rufen Sie entweder **erstellen** oder `SubclassWindow`. Sie sollten nicht beide Methoden für dasselbe Objekt aufrufen.  
  
 Bei Verwendung der **Hinzufügen des Steuerelements basierend auf** option in der ATL-Projekt-Assistent wird automatisch vom Assistenten hinzugefügt. eine `CContainedWindowT` -Datenmember der Klasse des Steuerelements. Das folgende Beispiel zeigt, wie die im Fenster deklariert wird:  
  
 [!code-cpp[NVC_ATL_Windowing&#38;](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing Nr.&39;](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#40;](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------|---------|  
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) und nachfolgenden Themen in der[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-nameccontainedwindowta--ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
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
 [in] Der Name der eine vorhandene Fensterklasse, die der im Fenster basieren soll.  
  
 `pObject`  
 [in] Ein Zeiger auf das enthaltende Objekt, das die Nachricht Zuordnung deklariert. Klasse des Objekts durch Ableiten von [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Gibt die Nachricht-Zuordnung, die den im Fenster Nachrichten verarbeitet werden. Der Standardwert 0, gibt die Standard-Nachricht-Karte, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Um eine andere Nachricht Zuordnung verwenden, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), übergeben Sie `msgMapID`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein neues Fenster über erstellen [erstellen](#create), müssen Sie den Namen der für eine vorhandene Fensterklasse übergeben der `lpszClassName` Parameter. Ein Beispiel finden Sie unter der [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
 Es gibt drei Konstruktoren:  
  
-   Der Konstruktor mit drei Argumenten ist in der Regel aufgerufen.  
  
-   Der Konstruktor mit zwei Argumenten verwendet den Klassennamen von **TBase::GetWndClassName**.  
  
-   Wenn Sie später die Argumente angeben möchten, wird der Konstruktor ohne Argumente verwendet. Sie müssen die Fensterklassennamen Nachricht Map-Objekt und Nachricht Zuordnungs-ID angeben, wenn Sie später Aufrufen **erstellen**.  
  
 Wenn Sie ein vorhandenes Fenster unterordnen über [SubclassWindow](#subclasswindow), `lpszClassName` Wert wird nicht verwendet werden, daher können Sie übergeben **NULL** für diesen Parameter.  
  
##  <a name="a-namecreatea--ccontainedwindowtcreate"></a><a name="create"></a>CContainedWindow:: Create auf  
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
 [in] Der Name der eine vorhandene Fensterklasse, die der im Fenster basieren soll.  
  
 `pObject`  
 [in] Ein Zeiger auf das enthaltende Objekt, das die Nachricht Zuordnung deklariert. Klasse des Objekts durch Ableiten von [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Gibt die Nachricht-Zuordnung, die den im Fenster Nachrichten verarbeitet werden. Der Standardwert 0, gibt die Standard-Nachricht-Karte, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Um eine andere Nachricht Zuordnung verwenden, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), übergeben Sie `msgMapID`.  
  
 `hWndParent`  
 [in] Das Handle für das übergeordnete Fenster oder das Besitzer.  
  
 `rect`  
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` Zeiger oder Verweis übergeben werden kann.  
  
 `szWindowName`  
 [in] Gibt den Namen des Fensters. Der Standardwert ist **NULL**.  
  
 `dwStyle`  
 [in] Der Stil des Fensters. Der Standardwert ist **WS_CHILD | WS_VISIBLE**. Eine Liste der möglichen Werte finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Der erweiterte Fensterstil. Der Standardwert ist 0, d. h. keine erweiterten Stil. Eine Liste der möglichen Werte finden Sie unter [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Für ein untergeordnetes Fenster, das Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menü-Handle für das Fenster. Der Standardwert ist **0 HE**.  
  
 `lpCreateParam`  
 [in] Ein Zeiger auf die Daten im Fenster erstellen. Eine vollständige Beschreibung finden Sie in der Beschreibung der letzte Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Rückgabewert  
 Falls erfolgreich, das Handle für das neu erstellte Fenster; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Name der vorhandenen Fensterklasse wird gespeichert, [M_lpszClassName](#m_lpszclassname). **Erstellen Sie** erstellt dann ein Fenster basierend auf dieser neuen Klasse. Das neu erstellte Fenster wird automatisch angefügt, um die `CContainedWindowT` Objekt.  
  
> [!NOTE]
>  Rufen Sie **erstellen** , wenn Sie bereits aufgerufen [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die `MenuOrID` -Parameter muss als 0 HE angegeben werden (Standardwert), einen Compilerfehler zu vermeiden.  
  
##  <a name="a-namedefwindowproca--ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Aufgerufen von [WindowProc](#windowproc) zum Verarbeiten von Nachrichten durch die Zuordnung der Nachricht nicht verarbeitet.  
  
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
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Verarbeitung der Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `DefWindowProc` Aufrufe der [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) Win32-Funktion zum Senden von Informationen der Nachricht an die Fensterprozedur in angegebenen [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
##  <a name="a-namegetcurrentmessagea--ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Gibt die aktuelle Nachricht zurück ( **M_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Nachricht, verpackt in die `MSG` Struktur.  
  
##  <a name="a-namemdwmsgmapida--ccontainedwindowtmdwmsgmapid"></a><a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Enthält die ID der Nachricht Zuordnung wird derzeit für den im Fenster verwendet.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Nachricht Zuordnung muss in dem Objekt deklariert werden.  
  
 Die Standard-meldungszuordnung, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), wird immer&0; (null) identifiziert. Eine Zuordnung alternative Nachricht, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), wird durch identifiziert `msgMapID`.  
  
 `m_dwMsgMapID`wird zuerst vom Konstruktor initialisiert und kann geändert werden, durch Aufrufen von [SwitchMessageMap](#switchmessagemap). Ein Beispiel finden Sie unter der [CContainedWindow Übersicht](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="a-namemlpszclassnamea--ccontainedwindowtmlpszclassname"></a><a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Gibt den Namen einer vorhandenen Fensterklasse.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Fenster erstellen [erstellen](#create) registriert eine neue Windows-Klasse, die auf diesem vorhandenen Klasse basiert, verwendet jedoch [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie unter der [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
##  <a name="a-namempfnsuperwindowproca--ccontainedwindowtmpfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Wenn es sich bei der im Fenster als Unterklasse definiert ist, `m_pfnSuperWindowProc` verweist auf die ursprüngliche Fensterprozedur der Fensterklasse.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Fenster enthaltene Komponente ist, d. h. es basiert auf eine Fensterklasse, die eine vorhandene Klasse, ändert `m_pfnSuperWindowProc` verweist auf die vorhandene Fensterklasse Fensterprozedur.  
  
 Die [DefWindowProc](#defwindowproc) Methode sendet Informationen an die Fensterprozedur in gespeicherten `m_pfnSuperWindowProc`.  
  
##  <a name="a-namempobjecta--ccontainedwindowtmpobject"></a><a name="m_pobject"></a>CContainedWindowT::m_pObject  
 Verweist auf das Objekt mit dem `CContainedWindowT` Objekt.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Container, dessen Klasse durch von ableiten [CMessageMap](../../atl/reference/cmessagemap-class.md), deklariert die Nachricht-Zuordnung, die von den im Fenster verwendet.  
  
 `m_pObject`wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie unter der [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) (Übersicht).  
  
##  <a name="a-nameregisterwndsuperclassa--ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Aufgerufen von [erstellen](#create) Window-Klasse des Fensters enthaltenen registrieren.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall Atom eindeutig identifiziert, die Fensterklasse registriert werden; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Dieser Fensterklasse basiert auf einer vorhandenen Klasse verwendet jedoch [CContainedWindowT::WindowProc](#windowproc). Die vorhandene Fensterklasse Namen und Fenster-Prozedur werden gespeichert, [M_lpszClassName](#m_lpszclassname) und [M_pfnSuperWindowProc](#m_pfnsuperwindowproc)bzw..  
  
##  <a name="a-namesubclasswindowa--ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>SubclassWindow  
 Unterklassen des Fensters identifizierten `hWnd` und fügt es der `CContainedWindowT` Objekt.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Fenster erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist das Fenster erfolgreich Unterklassen, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Untergeordnete Fenster verwendet jetzt [CContainedWindowT::WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Rufen Sie `SubclassWindow` , wenn Sie bereits aufgerufen [erstellen](#create).  
  
##  <a name="a-nameswitchmessagemapa--ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Ändert die Zuordnung der Nachricht zum Verarbeiten von Nachrichten mit den im Fenster verwendet wird.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMsgMapID`  
 [in] Der Meldungsbezeichner zuordnen. Die Zuordnung der Standard-Nachricht verwenden, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), übergeben Sie&0; (null). Um eine andere Nachricht Zuordnung verwenden, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), übergeben Sie `msgMapID`.  
  
### <a name="remarks"></a>Hinweise  
 In dem Objekt muss die Nachricht Zuordnung definiert werden.  
  
 Legen Sie zu Beginn der Zuordnung Meldungsbezeichner im Konstruktor.  
  
##  <a name="a-nameunsubclasswindowa--ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Trennt die untergeordnete Fenster aus der `CContainedWindowT` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bForce`  
 [in] Legen Sie auf **TRUE** zu erzwingen, dass die ursprüngliche Fensterprozedur wiederhergestellt werden auch wenn die Fensterprozedur für diesen `CContainedWindowT` Objekt ist nicht aktiv. Wenn `bForce` Wert **FALSE** und die Fensterprozedur für diesen `CContainedWindowT` Objekt ist nicht aktiv, wird die ursprüngliche Fensterprozedur nicht wiederhergestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Fenster, das zuvor als Unterklasse. Wenn `bForce` Wert **FALSE** und die Fensterprozedur für dieses `CContainedWindowT` -Objekt ist nicht aktiv ist, gibt **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur, wenn Sie möchten, um die ursprüngliche Fensterprozedur wiederherzustellen, bevor Sie das Fenster zerstört wird. Andernfalls [WindowProc](#windowproc) wird geschieht dies automatisch, wenn das Fenster zerstört wird.  
  
##  <a name="a-namewindowproca--ccontainedwindowtwindowproc"></a><a name="windowproc"></a>CContainedWindowT::WindowProc  
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
 `WindowProc`leitet Nachrichten an die identifizierten meldungszuordnung [M_dwMsgMapID](#m_dwmsgmapid). Falls erforderlich, `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für die weitere Verarbeitung.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindow-Klasse](../../atl/reference/cwindow-class.md)   
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap-Klasse](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

