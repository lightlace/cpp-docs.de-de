---
title: CAxDialogImpl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAxDialogImpl
- ATL.CAxDialogImpl
- CAxDialogImpl
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: 21
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
ms.openlocfilehash: 71e77ac6b8d2a89e384817020772bb855ce2d573
ms.lasthandoff: 02/24/2017

---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl-Klasse
Diese Klasse implementiert ein Dialogfeld (gebunden oder ungebunden), die ActiveX-Steuerelemente hostet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `CAxDialogImpl`.  
  
 *TBase*  
 Die Basis-Fensterklasse für **CDialogImplBaseT**.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode senkereigniszuordnung oder alle Einträge in das Objekt Senke zuordnen.|  
|[CAxDialogImpl::Create](#create)|Rufen Sie diese Methode zum Erstellen eines nicht modalen Dialogfelds.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Rufen Sie diese Methode, um ein nicht modales Dialogfeld löschen.|  
|[CAxDialogImpl::DoModal](#domodal)|Rufen Sie diese Methode, um ein modales Dialogfeld zu erstellen.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Rufen Sie diese Methode, um ein modales Dialogfeld löschen.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Rufen Sie diese Methode, um einen Zeiger auf die `DialogProc` Callback-Funktion.|  
|[CAxDialogImpl::GetIDD](#getidd)|Rufen Sie diese Methode, um das Dialogfeld Vorlage Ressourcen-ID abrufen|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Rufen Sie diese Methode, um zu bestimmen, ob eine Nachricht für das Dialogfeld vorgesehen ist, und ist es, verarbeiten Sie die Nachricht zu.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Eine Variable, die nur im Debugbuild vorhanden erstellt und ist festgelegt auf WAHR, wenn das Dialogfeld modal ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CAxDialogImpl`können Sie ein Dialogfeld mit oder ohne Modus erstellen. `CAxDialogImpl`Stellt die Prozedur für Standarddialogfelder, die die Standardkurve für die Nachricht verwendet wird, um Nachrichten an die entsprechenden Handler zu leiten.  
  
 `CAxDialogImpl`leitet sich von `CDialogImplBaseT`, die wiederum abgeleitet wird, von *TBase* (standardmäßig `CWindow`) und `CMessageMap`.  
  
 Die Klasse muss einen IDD-Member definieren, der die Dialogfeld Vorlage die Ressourcen-ID angibt Z. B. Hinzufügen eines ATL-Dialogfeld-Objekt mithilfe der **Klasse hinzufügen** Dialogfeld fügt automatisch die folgende Zeile zu Ihrer Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing&#41;](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 in dem `MyDialog` ist die **Kurznamen** im ATL-Dialogfeld-Assistenten eingegeben haben.  
  
 Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) Weitere Informationen.  
  
 Beachten Sie, mit denen ein ActiveX-Steuerelement in einem modalen Dialogfeld erstellt `CAxDialogImpl` Zugriffstasten werden nicht unterstützt. Zur Unterstützung von Zugriffstasten auf ein Dialogfeld mit erstellten `CAxDialogImpl`und erstellen Sie ein nicht modales Dialogfeld, Ihre eigene Nachrichtenschleife verwenden, [CAxDialogImpl::IsDialogMessage](#isdialogmessage) nach dem Abrufen einer Nachricht aus der Warteschlange um eine Zugriffstaste zu behandeln.  
  
 Weitere Informationen zu `CAxDialogImpl`, finden Sie unter [ATL Control Containment-häufig gestellte Fragen zu](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-nameadvisesinkmapa--caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap  
 Rufen Sie diese Methode senkereigniszuordnung oder alle Einträge in das Objekt Senke zuordnen.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 Auf true festgelegt, wenn alle Senke Einträge darüber informiert zu werden; False, wenn alle Senke Einträge sind unadvised sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namecreatea--caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::Create  
 Rufen Sie diese Methode zum Erstellen eines nicht modalen Dialogfelds.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster.  
  
 `dwInitParam`  
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der `lParam` Parameter von der **WM_INITDIALOG** Nachricht.  
  
 **RECT &**  
 Dieser Parameter wird nicht verwendet. Dieser Parameter wird vom übergebene `CComControl`.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das neu erstellte Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt. Rufen Sie zum Erstellen eines modalen Dialogfelds [DoModal](#domodal).  
  
 Die zweite Außerkraftsetzung bereitgestellt wurde, nur mit Dialogfeldern verwendet werden können [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="a-namedestroywindowa--caxdialogimpldestroywindow"></a><a name="destroywindow"></a>CAxDialogImpl::DestroyWindow  
 Rufen Sie diese Methode, um ein nicht modales Dialogfeld löschen.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Fenster erfolgreich zerstört wird. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `DestroyWindow` zerstört ein modales Dialogfeld. Rufen Sie [EndDialog](#enddialog) stattdessen.  
  
##  <a name="a-namedomodala--caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl::DoModal  
 Rufen Sie diese Methode, um ein modales Dialogfeld zu erstellen.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster. Der Standardwert ist der Rückgabewert von der [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32-Funktion.  
  
 `dwInitParam`  
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der `lParam` Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall den Wert des der `nRetCode` Parameter im Aufruf angegeben [EndDialog](#enddialog)ist, andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt.  
  
 Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).  
  
##  <a name="a-nameenddialoga--caxdialogimplenddialog"></a><a name="enddialog"></a>CAxDialogImpl::EndDialog  
 Rufen Sie diese Methode, um ein modales Dialogfeld löschen.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 [in] Der Wert von zurückgegeben werden [DoModal](#domodal).  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Dialogfeld zerstört wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 `EndDialog`muss über die Prozedur aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der `nRetCode` als Rückgabewert für `DoModal`, der das Dialogfeld erstellt.  
  
> [!NOTE]
>  Rufen Sie nicht `EndDialog` , ein nicht modales Dialogfeld zu zerstören. Rufen Sie [DestroyWindow](#destroywindow) stattdessen.  
  
##  <a name="a-namegetdialogproca--caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc  
 Rufen Sie diese Methode, um einen Zeiger auf die `DialogProc` Callback-Funktion.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die `DialogProc` Callback-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die `DialogProc` Funktion ist eine anwendungsdefinierte Rückruffunktion ausgeführt.  
  
##  <a name="a-namegetidda--caxdialogimplgetidd"></a><a name="getidd"></a>CAxDialogImpl::GetIDD  
 Rufen Sie diese Methode, um das Dialogfeld Vorlage die Ressourcen-ID abrufen  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Dialogfeld Vorlage die Ressourcen-ID  
  
##  <a name="a-nameisdialogmessagea--caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage  
 Rufen Sie diese Methode, um zu bestimmen, ob eine Nachricht für das Dialogfeld vorgesehen ist, und ist es, verarbeiten Sie die Nachricht zu.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Zeiger auf eine [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) -Struktur, die der Nachricht, die überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn die Nachricht verarbeitet, FALSE wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode soll eine Meldungsschleife aus aufgerufen werden.  
  
##  <a name="a-namembmodala--caxdialogimplmbmodal"></a><a name="m_bmodal"></a>CAxDialogImpl::m_bModal  
 Eine Variable, die nur im Debugbuild vorhanden erstellt und ist festgelegt auf WAHR, wenn das Dialogfeld modal ist.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDialogImpl-Klasse](../../atl/reference/cdialogimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

