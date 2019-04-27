---
title: IAxWinHostWindowLic-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: aca3970d13db53ffa04fe9582bbe9b8db78e820d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275989"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic-Schnittstelle

Diese Schnittstelle bietet Methoden zum Bearbeiten von ein lizenziertes Steuerelement und dessen Host-Objekt.

## <a name="syntax"></a>Syntax

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CreateControlLic](#createcontrollic)|Erstellt ein lizenziertes Steuerelement und hängt es an den Hostobjekt.|
|[CreateControlLicEx](#createcontrollicex)|Erstellt ein lizenziertes Steuerelement, auf das Hostobjekt angefügt und optional ein Ereignishandler eingerichtet.|

## <a name="remarks"></a>Hinweise

`IAxWinHostWindowLic` erbt von [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) und fügt die Methoden, die die Erstellung von lizenzierte Steuerelemente zu unterstützen.

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, die Mitglieder dieser Schnittstelle verwendet.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

Erstellt ein lizenziertes Steuerelement, initialisiert es und hostet es im Fenster identifizierte `hWnd`.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parameter

*bstrLic*<br/>
[in] BSTR, das den Lizenzschlüssel für das Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) eine Beschreibung der verbleibende Parameter und Rückgabewert.

Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLic`.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parameter

*bstrLic*<br/>
[in] BSTR, das den Lizenzschlüssel für das Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) eine Beschreibung der verbleibende Parameter und Rückgabewert.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLicEx`.
