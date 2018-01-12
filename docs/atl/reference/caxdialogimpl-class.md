---
title: CAxDialogImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
dev_langs: C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2db97c0de9f262936212cf7f38abddf7c91eb5a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl-Klasse
Diese Klasse implementiert ein Dialogfeld (gebunden oder ungebunden), der als Host-ActiveX-Steuerelemente.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CAxDialogImpl`.  
  
 *TBase*  
 Die Basis-Fensterklasse für **CDialogImplBaseT**.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode senkereigniszuordnung oder alle Einträge in das Objekt Senke Zuordnung Ereignis zuordnen.|  
|[CAxDialogImpl::Create](#create)|Rufen Sie diese Methode, um ein nicht modales Dialogfeld erstellen.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Rufen Sie diese Methode, um ein nicht modales Dialogfeld zu zerstören.|  
|[CAxDialogImpl::DoModal](#domodal)|Rufen Sie diese Methode, um ein modales Dialogfeld erstellen.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Rufen Sie diese Methode, um ein modales Dialogfeld zu zerstören.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Rufen Sie diese Methode zum Abrufen eines Zeigers auf die `DialogProc` Rückruffunktion.|  
|[CAxDialogImpl::GetIDD](#getidd)|Rufen Sie diese Methode, um das Dialogfeld Vorlage Ressourcen-ID abrufen|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Rufen Sie diese Methode, um zu bestimmen, ob eine Nachricht zu diesem Dialogfeld vorgesehen ist, und wenn dies der Fall, verarbeiten Sie die Nachricht.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Eine Variable, die nur im Debugbuild vorhanden erstellt und auf das Dialogfeld modal ist "true" festgelegt ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CAxDialogImpl`können Sie ein Dialogfeld mit oder ohne Modus zu erstellen. `CAxDialogImpl`Stellt die für Standarddialogfelder, die die Standard-meldungszuordnung zur Weiterleitung von Nachrichten an die entsprechenden Handler verwendet.  
  
 `CAxDialogImpl`leitet sich von `CDialogImplBaseT`, der wiederum abgeleitet aus *TBase* (standardmäßig `CWindow`) und `CMessageMap`.  
  
 Die Klasse muss eine LEISTE-Element definieren, der angibt, das Dialogfeld Vorlage Ressourcen-ID Z. B. Hinzufügen eines Objekts mit ATL-Dialogfeld die **Klasse hinzufügen** Dialogfeld fügt automatisch die folgende Zeile auf die Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 auf dem `MyDialog` ist die **Kurzname** im ATL-Dialogfeld-Assistenten eingegeben haben.  
  
 Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) für Weitere Informationen.  
  
 Beachten Sie, die mit einem ActiveX-Steuerelement in ein modales Dialogfeld erstellt `CAxDialogImpl` Zugriffstasten wird nicht unterstützt. Zur Unterstützung von Zugriffstasten ein Dialogfeld mit erstellt `CAxDialogImpl`, erstellen Sie ein nicht modales Dialogfeld und Ihre eigene Nachrichtenschleife verwenden, [CAxDialogImpl::IsDialogMessage](#isdialogmessage) nach Eingang einer Nachricht aus der Warteschlange verarbeiten einer Zugriffstaste.  
  
 Weitere Informationen zu `CAxDialogImpl`, finden Sie unter [ATL-Steuerelement Containment-häufig gestellte Fragen zu](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap  
 Rufen Sie diese Methode senkereigniszuordnung oder alle Einträge in das Objekt Senke Zuordnung Ereignis zuordnen.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 Festgelegt auf "true", wenn alle Senke Einträge darauf hingewiesen werden. "false", wenn alle Senke Einträge sind unadvised aufweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="create"></a>CAxDialogImpl::Create  
 Rufen Sie diese Methode, um ein nicht modales Dialogfeld erstellen.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster.  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der `lParam` Parameter von der **WM_INITDIALOG** Nachricht.  
  
 **RECT &**  
 Dieser Parameter wird nicht verwendet. Dieser Parameter wird durch übergeben `CComControl`.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das neu erstellte Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt. Rufen Sie zum Erstellen eines modales Dialogfelds [DoModal](#domodal).  
  
 Die zweite Außerkraftsetzung wird angegeben, nur verwendet werden, damit Dialogfelder mit verwendet werden können [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>CAxDialogImpl::DestroyWindow  
 Rufen Sie diese Methode, um ein nicht modales Dialogfeld zu zerstören.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Fenster erfolgreich zerstört wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht `DestroyWindow` zerstört ein modales Dialogfeld. Rufen Sie ["EndDialog"](#enddialog) stattdessen.  
  
##  <a name="domodal"></a>CAxDialogImpl::DoModal  
 Rufen Sie diese Methode, um ein modales Dialogfeld erstellen.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster. Der Standardwert ist der Rückgabewert von der [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32-Funktion.  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der `lParam` Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall den Wert des der `nRetCode` Parameter im Aufruf angegeben ["EndDialog"](#enddialog)ist, andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt.  
  
 Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).  
  
##  <a name="enddialog"></a>CAxDialogImpl::EndDialog  
 Rufen Sie diese Methode, um ein modales Dialogfeld zu zerstören.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 [in] Der Wert von zurückgegeben werden sollen [DoModal](#domodal).  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Dialogfeld zerstört wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 `EndDialog`muss über die für Standarddialogfelder aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der `nRetCode` als Rückgabewert für `DoModal`, der das Dialogfeld erstellt.  
  
> [!NOTE]
>  Rufen Sie nicht `EndDialog` , ein nicht modales Dialogfeld zu zerstören. Rufen Sie [DestroyWindow](#destroywindow) stattdessen.  
  
##  <a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc  
 Rufen Sie diese Methode zum Abrufen eines Zeigers auf die `DialogProc` Rückruffunktion.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die `DialogProc` Rückruffunktion.  
  
### <a name="remarks"></a>Hinweise  
 Die `DialogProc` Funktion ist eine anwendungsdefinierte Rückruffunktion.  
  
##  <a name="getidd"></a>CAxDialogImpl::GetIDD  
 Rufen Sie diese Methode, um das Dialogfeld Vorlage Ressourcen-ID abrufen  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Dialogfeld Vorlage Ressourcen-ID.  
  
##  <a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage  
 Rufen Sie diese Methode, um zu bestimmen, ob eine Nachricht zu diesem Dialogfeld vorgesehen ist, und wenn dies der Fall, verarbeiten Sie die Nachricht.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Zeiger auf eine [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) Struktur mit der Nachricht überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Nachricht verarbeitet, "false" andernfalls war.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode dient eine Nachrichtenschleife aus aufgerufen werden.  
  
##  <a name="m_bmodal"></a>CAxDialogImpl::m_bModal  
 Eine Variable, die nur im Debugbuild vorhanden erstellt und auf das Dialogfeld modal ist "true" festgelegt ist.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDialogImpl-Klasse](../../atl/reference/cdialogimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
