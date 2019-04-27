---
title: IPropertyPageImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: a3b92e3d2f72ca48238eb22404947d2eafde0378
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197876"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPropertyPageImpl`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPropertyPageImpl::Activate](#activate)|Erstellt das Dialogfeldfenster für die Eigenschaftenseite.|
|[IPropertyPageImpl::Apply](#apply)|Die zugrunde liegenden Objekte, die durch die angegebenen aktuellen eigenschaftsseitenwerte gilt `SetObjects`. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IPropertyPageImpl::Deactivate](#deactivate)|Zerstört das Fenster mit erstellt `Activate`.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Ruft Informationen über die Eigenschaftenseite.|
|[IPropertyPageImpl::Help](#help)|Ruft die Windows-Hilfe für die Eigenschaftenseite.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Gibt an, ob die Eigenschaftenseite geändert wurde, da er aktiviert wurde.|
|[IPropertyPageImpl::Move](#move)|Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.|
|[IPropertyPageImpl::SetDirty](#setdirty)|Kennzeichnet die Eigenschaftenseite-Status, als geändert oder unverändert.|
|[IPropertyPageImpl::SetObjects](#setobjects)|Bietet eine Reihe von `IUnknown` Entscheidungshilfen für die Auswahl auf der Seite der zugeordneten Objekte. Diese Objekte erhalten, die aktuellen Eigenschaftswerte für die Seite durch einen Aufruf von `Apply`.|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Die Eigenschaft auf der Seite mit einer `IPropertyPageSite` -Zeiger ist, über die Eigenschaftenseite, die mit der Eigenschaftenrahmen kommuniziert.|
|[IPropertyPageImpl::Show](#show)|Macht die Eigenschaftenseiten-Dialogfeld, ein- oder ausgeblendet.|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet eine Tastatureingabe angegebene.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Gibt an, ob die Eigenschaftenseite Zustand geändert hat.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Speichert den Ressourcenbezeichner, der die Beschreibung auf der Seite der Zeichenfolge zugeordnet.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Speichert den Kontextbezeichner für das Hilfethema, das die Eigenschaftenseite zugeordnet.|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei, die die Eigenschaftenseite beschreibt zugeordnet.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Speichert den Ressourcenbezeichner verknüpft ist, mit der Textzeichenfolge, die auf der Registerkarte für die Eigenschaftenseite angezeigt wird.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Speichert die Anzahl der Objekte, die die Eigenschaftenseite zugeordnet.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Verweist auf die `IPropertyPageSite` Schnittstelle, die über die Eigenschaftenseite, die mit der Eigenschaftenrahmen kommuniziert.|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Verweist auf ein Array von `IUnknown` Zeiger auf die auf der Seite der zugeordneten Objekte.|
|[IPropertyPageImpl::m_size](#m_size)|Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel an.|

## <a name="remarks"></a>Hinweise

Die [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) Schnittstelle ermöglicht es, ein Objekt eine bestimmten Eigenschaftenseite innerhalb eines Eigenschaftenblatts zu verwalten. Klasse `IPropertyPageImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="activate"></a>  IPropertyPageImpl::Activate

Erstellt das Dialogfeldfenster für die Eigenschaftenseite.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Hinweise

Das Dialogfeld wird standardmäßig immer nicht modales, unabhängig vom Wert für die *bModal* Parameter.

Finden Sie unter [IPropertyPage::Activate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-activate) in das Windows SDK.

##  <a name="apply"></a>  IPropertyPageImpl::Apply

Die zugrunde liegenden Objekte, die durch die angegebenen aktuellen eigenschaftsseitenwerte gilt `SetObjects`.

```
HRESULT Apply();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::Apply](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-apply) in das Windows SDK.

##  <a name="deactivate"></a>  IPropertyPageImpl::Deactivate

Zerstört das Dialogfeldfenster mit erstellt [aktivieren](#activate).

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::Deactivate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-deactivate) in das Windows SDK.

##  <a name="getpageinfo"></a>  IPropertyPageImpl::GetPageInfo

Füllt die *pPageInfo* Struktur mit Informationen, die in der Datenmember enthalten.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Hinweise

`GetPageInfo` Lädt die Zeichenfolgenressourcen zugeordneten [M_dwDocString](#m_dwdocstring), [M_dwHelpFile](#m_dwhelpfile), und [M_dwTitle](#m_dwtitle).

Finden Sie unter [IPropertyPage::GetPageInfo](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) in das Windows SDK.

##  <a name="help"></a>  IPropertyPageImpl::Help

Ruft die Windows-Hilfe für die Eigenschaftenseite.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::Help](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-help) in das Windows SDK.

##  <a name="ipropertypageimpl"></a>  IPropertyPageImpl::IPropertyPageImpl

Der Konstruktor.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Hinweise

Initialisiert alle Datenmember.

##  <a name="ispagedirty"></a>  IPropertyPageImpl::IsPageDirty

Gibt an, ob die Eigenschaftenseite geändert wurde, da er aktiviert wurde.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Hinweise

`IsPageDirty` Gibt S_OK zurück, wenn die Seite geändert wurde, da er aktiviert wurde.

##  <a name="m_bdirty"></a>  IPropertyPageImpl::m_bDirty

Gibt an, ob die Eigenschaftenseite Zustand geändert hat.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>  IPropertyPageImpl::m_nObjects

Speichert die Anzahl der Objekte, die die Eigenschaftenseite zugeordnet.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>  IPropertyPageImpl::m_dwHelpContext

Speichert den Kontextbezeichner für das Hilfethema, das die Eigenschaftenseite zugeordnet.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>  IPropertyPageImpl::m_dwDocString

Speichert den Ressourcenbezeichner, der die Beschreibung auf der Seite der Zeichenfolge zugeordnet.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>  IPropertyPageImpl::m_dwHelpFile

Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei, die die Eigenschaftenseite beschreibt zugeordnet.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>  IPropertyPageImpl::m_dwTitle

Speichert den Ressourcenbezeichner verknüpft ist, mit der Textzeichenfolge, die auf der Registerkarte für die Eigenschaftenseite angezeigt wird.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>  IPropertyPageImpl::m_pPageSite

Verweist auf die [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) Schnittstelle, die über die Eigenschaftenseite, die mit der Eigenschaftenrahmen kommuniziert.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>  IPropertyPageImpl::m_ppUnk

Verweist auf ein Array von `IUnknown` Zeiger auf die auf der Seite der zugeordneten Objekte.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>  IPropertyPageImpl::m_size

Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel an.

```
SIZE m_size;
```

##  <a name="move"></a>  IPropertyPageImpl::Move

Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::Move](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-move) in das Windows SDK.

##  <a name="setdirty"></a>  :: SetDirty

Kennzeichnet die Eigenschaftenseite Status als geändert oder unverändert, abhängig vom Wert *bDirty*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parameter

*bDirty*<br/>
[in] Bei "true", wird die Eigenschaftenseite Status als geändert markiert. Anderenfalls ist es markiert als unverändert.

### <a name="remarks"></a>Hinweise

Bei Bedarf `SetDirty` informiert den Frame, die die Eigenschaftenseite geändert wurde.

##  <a name="setobjects"></a>  IPropertyPageImpl::SetObjects

Bietet eine Reihe von `IUnknown` Entscheidungshilfen für die Auswahl auf der Seite der zugeordneten Objekte.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::SetObjects](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setobjects) in das Windows SDK.

##  <a name="setpagesite"></a>  IPropertyPageImpl::SetPageSite

Die Eigenschaft auf der Seite mit einer [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) -Zeiger ist, über die Eigenschaftenseite, die mit der Eigenschaftenrahmen kommuniziert.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::SetPageSite](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setpagesite) in das Windows SDK.

##  <a name="show"></a>  IPropertyPageImpl::Show

Macht die Eigenschaftenseiten-Dialogfeld, ein- oder ausgeblendet.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::Show](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-show) in das Windows SDK.

##  <a name="translateaccelerator"></a>  IPropertyPageImpl::TranslateAccelerator

Verarbeitet die Tastatureingabe in angegebenen `pMsg`.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPage2Impl-Klasse](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
