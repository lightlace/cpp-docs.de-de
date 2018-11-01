---
title: IAxWinAmbientDispatchEx-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: 5b4afabe2c12dff048bc6a6fb904a82b3cea4d01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539437"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx-Schnittstelle

Diese Schnittstelle implementiert, ergänzende Ambiente-Eigenschaften für ein gehostetes Steuerelement.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.|

## <a name="remarks"></a>Hinweise

Schließen Sie diese Schnittstelle in ATL-Anwendungen, die statisch verknüpft sind, ATL und Host ActiveX-Steuerelemente, vor allem ActiveX-Steuerelemente, die Ambient-Eigenschaften an. Diese Schnittstelle nicht eingeschlossen wird diese Assertion generiert: "Haben Sie vergessen, die LIBID CComModule übergeben"

Diese Schnittstelle wird durch die ATL-ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Abgeleitet von [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` Fügt eine Methode, die Sie an, um die ambient-Eigenschaft-Schnittstelle, die vom ATL ein eigenes bereitgestellten ergänzen kann.

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) wird versucht, Typinformationen zum Laden `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.

Wenn Sie ATL90.dll, verknüpfen möchten **AXHost** lädt die Typinformationen aus der Typbibliothek in der DLL.

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) Weitere Details.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist in einer Reihe von Formen annehmen, verfügbar, wie in der folgenden Tabelle gezeigt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|atliface.idl|
|Typbibliothek|ATL.dll|
|C++|konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parameter

*pDispatch*<br/>
Zeiger auf die neue Benutzeroberfläche.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn `SetAmbientDispatch` wird aufgerufen, mit der ein Zeiger auf eine neue Schnittstelle, die diese neue Schnittstelle verwendet werden, zum Aufrufen von Eigenschaften oder Methoden, die für die durch das gehostete Steuerelement gefragt werden, ob diese Eigenschaften nicht bereits enthalten sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>Siehe auch

[IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)
