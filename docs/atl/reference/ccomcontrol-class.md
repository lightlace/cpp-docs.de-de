---
title: CComControl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: ffbec7c1a83c0dd829878f4c73340528d32fb852
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771551"
---
# <a name="ccomcontrol-class"></a>CComControl-Klasse

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die Implementierung des Steuerelements.

*WinBase*<br/>
Die Basisklasse, die Windowing-Funktionen implementiert. Standardmäßig [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComControl::CreateControlWindow](#createcontrolwindow)|Erstellt ein Fenster für das Steuerelement.|
|[CComControl::FireOnChanged](#fireonchanged)|Benachrichtigt den Container-Senke, die eine Steuerelementeigenschaft geändert wurde.|
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Benachrichtigt den Container-Senke, dass eine Eigenschaft des Steuerelements geändert wird und das Objekt der Senke Vorgehensweise gefragt wird.|
|[CComControl::MessageBox](#messagebox)|Rufen Sie diese Methode zum Erstellen, anzeigen und verwenden ein Meldungsfeld an.|

## <a name="remarks"></a>Hinweise

`CComControl` ist eine Reihe von nützlichen Steuerelemente Hilfsfunktionen und wichtige Datenelemente für ATL-Steuerelementen an. Wenn Sie ein standard-Steuerelement oder ein DHTML-Steuerelement, das mit dem ATL-Steuerelement-Assistenten erstellen, der Assistent wird automatisch Ableiten der Klasse aus `CComControl`. `CComControl` leitet die meisten Methoden aus [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).

Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter den [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

Eine Demonstration der `CComControl` Methoden und Datenmember, finden Sie unter den [CIRC](../../overview/visual-cpp-samples.md) Beispiel.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="ccomcontrol"></a>  CComControl::CComControl

Der Konstruktor.

```
CComControl();
```

### <a name="remarks"></a>Hinweise

Ruft die [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) -Konstruktors und übergibt die `m_hWnd` Datenmember über geerbt [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Die GUID der Schnittstelle angefordert wird.

*ppv*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="remarks"></a>Hinweise

behandelt nur Schnittstellen in der COM-Zuordnungstabelle.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow

Standardmäßig erstellt ein Fenster für das Steuerelement durch Aufrufen von `CWindowImpl::Create`.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
[in] Handle für das übergeordnete Element oder Besitzer-Fenster. Ein gültiges Fensterhandle muss angegeben werden. Das Fenster des Steuerelements ist auf den Bereich des übergeordneten Fensters beschränkt.

*rcPos*<br/>
[in] Die anfängliche Größe und Position des Fensters erstellt werden.

### <a name="remarks"></a>Hinweise

Diese Methode überschreiben, sollten Sie etwas anders als ein einziges Fenster zu erstellen, z. B. um zwei Fenster zu erstellen, von denen eine Symbolleiste für das Steuerelement wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

##  <a name="fireonchanged"></a>  CComControl::FireOnChanged

Benachrichtigt den Container-Senke, die eine Steuerelementeigenschaft geändert wurde.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Parameter

*dispID*<br/>
[in] Der Bezeichner der Eigenschaft, die geändert wurde.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Wenn die Steuerelementklasse abgeleitet [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink), diese Methode ruft [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) zu benachrichtigen, alle verbundenen `IPropertyNotifySink` Schnittstellen, das angegebene Steuerelement -Eigenschaft geändert hat. Wenn eine Klasse nicht von abgeleitet ist `IPropertyNotifySink`, diese Methode gibt S_OK zurück.

Diese Methode ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit

Benachrichtigt den Container-Senke, dass eine Eigenschaft des Steuerelements geändert wird und das Objekt der Senke Vorgehensweise gefragt wird.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Parameter

*dispID*<br/>
[in] Der Bezeichner der Eigenschaft zu ändern.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Wenn die Steuerelementklasse abgeleitet [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink), ruft diese Methode [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) zu benachrichtigen, alle verbundenen `IPropertyNotifySink` Schnittstellen, der angegebenen Eigenschaft des Steuerelements wird geändert. Wenn eine Klasse nicht von abgeleitet ist `IPropertyNotifySink`, diese Methode gibt S_OK zurück.

Diese Methode ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

##  <a name="messagebox"></a>  CComControl::MessageBox

Rufen Sie diese Methode zum Erstellen, anzeigen und verwenden ein Meldungsfeld an.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Der Text im Meldungsfeld angezeigt werden.

*lpszCaption*<br/>
Der Titel des Dateidialogfelds. Wenn NULL (Standard), den Titel "Error" wird verwendet.

*nType*<br/>
Gibt den Inhalt und Verhalten des Dialogfelds. Finden Sie unter den [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) Eintrag in der Windows-SDK-Dokumentation finden Sie eine Liste von den verschiedenen Meldungsfeldern verfügbar. Standardmäßig bietet ein einfaches **OK** Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Gibt einen ganzzahligen Wert angeben, die Menüelement Werte aufgeführt [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) in der Windows SDK-Dokumentation.

### <a name="remarks"></a>Hinweise

`MessageBox` ist nützlich, sowohl während der Entwicklung als auch eine einfache Möglichkeit, eine Warnung oder Fehlermeldung für den Benutzer anzuzeigen.

## <a name="see-also"></a>Siehe auch

[CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComControlBase-Klasse](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl-Klasse](../../atl/reference/ccomcompositecontrol-class.md)
