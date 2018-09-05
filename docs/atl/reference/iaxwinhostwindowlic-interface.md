---
title: IAxWinHostWindowLic-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 849f5269a715013431da2d8b91997c577008bf68
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767083"
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

*bstrLic*  
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

*bstrLic*  
[in] BSTR, das den Lizenzschlüssel für das Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) eine Beschreibung der verbleibende Parameter und Rückgabewert.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLicEx`.

