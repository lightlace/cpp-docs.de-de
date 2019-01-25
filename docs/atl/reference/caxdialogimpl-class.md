---
title: CAxDialogImpl-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: 852656b33eca1a8c87c6931b58cd49c0c41fe3dc
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893638"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl-Klasse

Diese Klasse implementiert ein Dialogfeld (gebunden oder ungebunden), die ActiveX-Steuerelemente hostet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `CAxDialogImpl`.

*TBase*<br/>
Die Basis-Fensterklasse für `CDialogImplBaseT`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode oder abzumelden alle Einträge in ereigniszuordnung Map "Senke" des Objekts auf.|
|[CAxDialogImpl::Create](#create)|Rufen Sie diese Methode zum Erstellen eines nicht modalen Dialogfelds an.|
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Rufen Sie diese Methode, um ein nicht modales Dialogfeld zerstören.|
|[CAxDialogImpl::DoModal](#domodal)|Rufen Sie diese Methode, um ein modales Dialogfeld zu erstellen.|
|[CAxDialogImpl::EndDialog](#enddialog)|Rufen Sie diese Methode, um ein modales Dialogfeld zerstören.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Rufen Sie diese Methode, um einen Zeiger auf die `DialogProc` Callback-Funktion.|
|[CAxDialogImpl::GetIDD](#getidd)|Rufen Sie diese Methode, um das Dialogfeld Vorlage Ressourcen-ID zu erhalten.|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Rufen Sie diese Methode, um zu bestimmen, ob dieses Dialogfeld können Sie eine Nachricht bestimmt ist und wenn es sich handelt, verarbeiten Sie die Nachricht.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|Eine Variable, die nur im Debugbuild vorhanden ist, erstellt und ist auf "true", wenn das Dialogfeld modal ist.|

## <a name="remarks"></a>Hinweise

`CAxDialogImpl` können Sie ein modales oder nicht modales Dialogfeld erstellt. `CAxDialogImpl` enthält die Dialogfeldprozedur, die die Standard-meldungszuordnung verwendet werden, um Nachrichten an die entsprechenden Handler zu leiten.

`CAxDialogImpl` leitet sich von `CDialogImplBaseT`, die wiederum leitet sich von *TBase* (standardmäßig `CWindow`) und `CMessageMap`.

Die Klasse muss eine IDD-Element definieren, der angibt, die Dialogfeld Vorlage-Ressourcen-ID Beispielsweise durch Hinzufügen eines ATL-Dialogfeld-Objekts mit der **Klasse hinzufügen** das Dialogfeld fügt automatisch die folgende Zeile zu einer Klasse:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

in denen `MyDialog` ist die **Kurznamen** im ATL-Dialogfeld-Assistenten eingegeben haben.

Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) für Weitere Informationen.

Beachten Sie, die ein ActiveX-Steuerelement in einem modalen Dialogfeld mit erstellt `CAxDialogImpl` Zugriffstasten werden nicht unterstützt. Zur Unterstützung von Zugriffstasten in einem Dialogfeld mit erstellt `CAxDialogImpl`, erstellen Sie ein nicht modales Dialogfeld und Ihre eigene Nachrichtenschleife verwenden, [CAxDialogImpl::IsDialogMessage](#isdialogmessage) nach Eingang einer Nachricht aus der Warteschlange verarbeiten einer die Zugriffstaste.

Weitere Informationen zu `CAxDialogImpl`, finden Sie unter [ATL-Steuerelement Containment-häufig gestellte Fragen zu](../../atl/atl-control-containment-faq.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap

Rufen Sie diese Methode oder abzumelden alle Einträge in ereigniszuordnung Map "Senke" des Objekts auf.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parameter

*bAdvise*<br/>
Festgelegt auf "true", wenn alle Senke Einträge darüber informiert zu werden. False, wenn alle Senke-Einträge sind, sich abzumelden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="create"></a>  CAxDialogImpl::Create

Rufen Sie diese Methode zum Erstellen eines nicht modalen Dialogfelds an.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
[in] Das Handle für das besitzende Fenster.

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

*RECT&*<br/>
Dieser Parameter wird nicht verwendet. Dieser Parameter wird übergeben, indem `CComControl`.

### <a name="return-value"></a>Rückgabewert

Das Handle für das neu erstellte Dialogfeld.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt. Rufen Sie zum Erstellen eines modalen Dialogfelds [DoModal](#domodal).

Beim zweiten Überschreiben wird bereitgestellt, damit der Dialogfelder verwendet werden können, mit [CComControl](../../atl/reference/ccomcontrol-class.md).

##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow

Rufen Sie diese Methode, um ein nicht modales Dialogfeld zerstören.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Fenster erfolgreich zerstört wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie keine `DestroyWindow` zerstört ein modales Dialogfeld. Rufen Sie [EndDialog](#enddialog) stattdessen.

##  <a name="domodal"></a>  CAxDialogImpl::DoModal

Rufen Sie diese Methode, um ein modales Dialogfeld zu erstellen.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
[in] Das Handle für das besitzende Fenster. Der Standardwert ist der Rückgabewert von der [GetActiveWindow](/windows/desktop/api/winuser/nf-winuser-getactivewindow) Win32-Funktion.

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

### <a name="return-value"></a>Rückgabewert

Im Erfolgsfall den Wert des der *nRetCode* Parameter im Aufruf angegeben [EndDialog](#enddialog)ist, andernfalls -1.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch angefügt, um die `CAxDialogImpl` Objekt.

Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).

##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog

Rufen Sie diese Methode, um ein modales Dialogfeld zerstören.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parameter

*nRetCode*<br/>
[in] Der Wert, der von zurückgegeben werden [DoModal](#domodal).

### <a name="return-value"></a>Rückgabewert

True, wenn das Dialogfeld zerstört wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

`EndDialog` muss über die Dialogfeldprozedur aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der *nRetCode* als Rückgabewert für `DoModal`, dem Sie das Dialogfeld erstellt.

> [!NOTE]
>  Rufen Sie keine `EndDialog` zum Zerstören eines nicht modalen Dialogfelds. Rufen Sie [DestroyWindow](#destroywindow) stattdessen.

##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc

Rufen Sie diese Methode, um einen Zeiger auf die `DialogProc` Callback-Funktion.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `DialogProc` Callback-Funktion.

### <a name="remarks"></a>Hinweise

Die `DialogProc` -Funktion ist ein anwendungsdefinierten Rückruffunktion.

##  <a name="getidd"></a>  CAxDialogImpl::GetIDD

Rufen Sie diese Methode, um das Dialogfeld Vorlage-Ressourcen-ID zu erhalten.

```
int GetIDD();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Dialogfeld Vorlage Ressourcen-ID zurück.

##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage

Rufen Sie diese Methode, um zu bestimmen, ob dieses Dialogfeld können Sie eine Nachricht bestimmt ist und wenn es sich handelt, verarbeiten Sie die Nachricht.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Zeiger auf eine [MSG](/windows/desktop/api/winuser/ns-winuser-msg) -Struktur, die der Nachricht, die überprüft werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Nachricht verarbeitet wurde, FALSE andernfalls wurde.

### <a name="remarks"></a>Hinweise

Diese Methode wird in einer Meldungsschleife aufgerufen werden soll.

##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal

Eine Variable, die nur im Debugbuild vorhanden ist, erstellt und ist auf "true", wenn das Dialogfeld modal ist.

```
bool m_bModal;
```

## <a name="see-also"></a>Siehe auch

[CDialogImpl-Klasse](../../atl/reference/cdialogimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
