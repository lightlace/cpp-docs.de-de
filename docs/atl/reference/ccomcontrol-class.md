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
ms.openlocfilehash: bf0f64d8c7b8e8a3347e4c0fcad902b9e8a0ecb4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497529"
---
# <a name="ccomcontrol-class"></a>CComControl-Klasse

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die das Steuerelement implementiert.

*WinBase*<br/>
Die Basisklasse, die windowingfunktionen implementiert. Der Standardwert ist [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComControl::CreateControlWindow](#createcontrolwindow)|Erstellt ein Fenster für das-Steuerelement.|
|[CComControl::FireOnChanged](#fireonchanged)|Benachrichtigt die Senke des Containers, dass sich eine Steuerelement Eigenschaft geändert hat.|
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Benachrichtigt die Senke des Containers, dass eine Steuerelement Eigenschaft im Begriff ist, geändert zu werden, und dass das Objekt die Senke anfordert, wie Sie fortfahren.|
|[CComControl::MessageBox](#messagebox)|Rufen Sie diese Methode auf, um ein Meldungs Feld zu erstellen, anzuzeigen und zu verwenden.|

## <a name="remarks"></a>Hinweise

`CComControl`ist ein Satz nützlicher Steuerungs Hilfsfunktionen und wichtiger Datenmember für ATL-Steuerelemente. Wenn Sie mithilfe des ATL-Steuerelement-Assistenten ein Standard Steuerelement oder ein DHTML-Steuerelement erstellen, leitet der `CComControl`Assistent automatisch die Klasse von ab. `CComControl`leitet die meisten Methoden von [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)ab.

Weitere Informationen zum Erstellen eines Steuer Elements finden Sie im [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen zum ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

Eine Demonstration von `CComControl` Methoden und Datenmembern finden Sie im [CIRC](../../overview/visual-cpp-samples.md) -Beispiel.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="ccomcontrol"></a>CComControl:: CComControl

Der Konstruktor.

```
CComControl();
```

### <a name="remarks"></a>Hinweise

Ruft den [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) -Konstruktor auf und `m_hWnd` übergibt dabei den durch [CWindowImpl](../../atl/reference/cwindowimpl-class.md)geerbten Datenmember.

##  <a name="controlqueryinterface"></a>CComControl:: controlqueryinterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der GUID der angeforderten Schnittstelle.

*ppv*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird, oder NULL, wenn die Schnittstelle nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Behandelt nur Schnittstellen in der com-Zuordnungs Tabelle.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

##  <a name="createcontrolwindow"></a>CComControl:: kreatecontrolwindow

Standardmäßig erstellt ein Fenster für das-Steuerelement, `CWindowImpl::Create`indem aufgerufen wird.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
in Handle für das übergeordnete Fenster oder Besitzer Fenster. Ein gültiges Fenster Handle muss angegeben werden. Das Steuerelement Fenster ist auf den Bereich seines übergeordneten Fensters beschränkt.

*rcPos*<br/>
in Die anfängliche Größe und Position des Fensters, das erstellt werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie ein anderes Fenster erstellen möchten, z. b., um zwei Fenster zu erstellen, von denen eine zu einer Symbolleiste für das Steuerelement wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

##  <a name="fireonchanged"></a>CComControl:: fireonchanged

Benachrichtigt die Senke des Containers, dass sich eine Steuerelement Eigenschaft geändert hat.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Parameter

*dispID*<br/>
in Der Bezeichner der geänderten Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Wenn Ihre Steuerelement Klasse von [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)abgeleitet ist, ruft diese Methode [cfirepropnotifyevent:: fireonchanged](cfirepropnotifyevent-class.md#fireonchanged) auf, `IPropertyNotifySink` um alle verbundenen Schnittstellen zu benachrichtigen, dass die angegebene Steuerelement Eigenschaft geändert wurde. Wenn Ihre Steuerelement Klasse nicht von `IPropertyNotifySink`abgeleitet ist, gibt diese Methode S_OK zurück.

Diese Methode kann auch dann aufgerufen werden, wenn das Steuerelement keine Verbindungspunkte unterstützt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

##  <a name="fireonrequestedit"></a>CComControl:: fireonrequestedit

Benachrichtigt die Senke des Containers, dass eine Steuerelement Eigenschaft im Begriff ist, geändert zu werden, und dass das Objekt die Senke anfordert, wie Sie fortfahren.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Parameter

*dispID*<br/>
in Der Bezeichner der Eigenschaft, die geändert werden soll.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Wenn Ihre Steuerelement Klasse von [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)abgeleitet ist, ruft diese Methode [cfirepropnotifyevent:: fireonrequestedit](cfirepropnotifyevent-class.md#fireonrequestedit) auf, `IPropertyNotifySink` um alle verbundenen Schnittstellen zu benachrichtigen, die von der angegebenen Steuerelement Eigenschaft geändert werden. Wenn Ihre Steuerelement Klasse nicht von `IPropertyNotifySink`abgeleitet ist, gibt diese Methode S_OK zurück.

Diese Methode kann auch dann aufgerufen werden, wenn das Steuerelement keine Verbindungspunkte unterstützt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

##  <a name="messagebox"></a>CComControl:: MessageBox

Rufen Sie diese Methode auf, um ein Meldungs Feld zu erstellen, anzuzeigen und zu verwenden.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Der Text, der im Meldungs Feld angezeigt werden soll.

*lpszCaption*<br/>
Der Dialogfeld Titel. Wenn der Wert NULL (Standard) ist, wird der Titel "Error" verwendet.

*nType*<br/>
Gibt den Inhalt und das Verhalten des Dialog Felds an. Eine Liste der verschiedenen verfügbaren Meldungs Felder finden Sie unter dem Eintrag [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) in der Windows SDK-Dokumentation. Der Standardwert ist eine einfache Schaltfläche **OK** .

### <a name="return-value"></a>Rückgabewert

Gibt einen ganzzahligen Wert zurück, der einen der unter [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) aufgeführten Menü Element Werte in der Windows SDK-Dokumentation angibt.

### <a name="remarks"></a>Hinweise

`MessageBox`ist sowohl während der Entwicklung nützlich als auch eine einfache Möglichkeit, dem Benutzer eine Fehler-oder Warnmeldung anzuzeigen.

## <a name="see-also"></a>Siehe auch

[CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComControlBase-Klasse](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl-Klasse](../../atl/reference/ccomcompositecontrol-class.md)
