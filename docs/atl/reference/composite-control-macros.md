---
title: Makros zusammengesetzter Steuerelemente
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 2c6d3e350755ef4a0cf4a84561e34619ab3974be
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299113"
---
# <a name="composite-control-macros"></a>Makros zusammengesetzter Steuerelemente

Diese Makros definieren ereignissenkenzuordnungen und Einträge.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|Markiert den Beginn der Ereignis-Senke Zuordnung für das zusammengesetzte Steuerelement.|
|[END_SINK_MAP](#end_sink_map)|Markiert das Ende der Zuordnung Ereignissenke für das zusammengesetzte Steuerelement.|
|[SINK_ENTRY](#sink_entry)|Der Eintrag in die Senke ereigniszuordnung.|
|[SINK_ENTRY_EX](#sink_entry_ex)|Der Eintrag in der Ereignis-Sink-Zuordnung mit einem zusätzlichen Parameter.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Ähnlich wie SINK_ENTRY_EX außer dass es sich um einen Zeiger auf die Iid verwendet.|
|[SINK_ENTRY_INFO](#sink_entry_info)|Einen Eintrag in die Senke ereigniszuordnung mit manuell angegebenen Typinformationen für die Verwendung mit [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Ähnlich wie SINK_ENTRY_INFO außer dass es sich um einen Zeiger auf die Iid verwendet.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP

Deklariert den Beginn der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>Parameter

*_class*<br/>
[in] Gibt das Steuerelement.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Hinweise

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

##  <a name="end_sink_map"></a>  END_SINK_MAP

Deklariert das Ende der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.

```
END_SINK_MAP()
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Hinweise

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

##  <a name="sink_entry"></a>  SINK_ENTRY

Deklariert die Handler-Funktion (*fn*) für das angegebene Ereignis (*Dispid*), der das angegebene Steuerelement *Id*.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Bezeichnet das Steuerelement.

*dispid*<br/>
[in] Bezeichnet das angegebene Ereignis.

*fn*<br/>
[in] Name des Ereignishandlerfunktion. Diese Funktion verwenden, muss die `_stdcall` Aufrufkonvention und die Signatur entsprechenden Dispinterface-Format haben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Hinweise

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX und SINK_ENTRY_EX_P

Deklariert die Handler-Funktion (*fn*) für das angegebene Ereignis (*Dispid*), der die Dispatchschnittstelle (*Iid*), für das Steuerelement, das identifizierte *Id*.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Bezeichnet das Steuerelement.

*iid*<br/>
[in] Identifiziert die Dispatchschnittstelle.

*piid*<br/>
[in] Zeiger auf die Dispatchschnittstelle.

*dispid*<br/>
[in] Bezeichnet das angegebene Ereignis.

*fn*<br/>
[in] Name des Ereignishandlerfunktion. Diese Funktion verwenden, muss die `_stdcall` Aufrufkonvention und die Signatur entsprechenden Dispinterface-Format haben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>Hinweise

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO und SINK_ENTRY_INFO_P

Verwenden Sie das SINK_ENTRY_INFO-Makro in eine Senke-Event-Zuordnung, die vom benötigten Informationen bereitstellen [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) zum Weiterleiten von Ereignissen an die entsprechende Handler-Funktion.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Ganzzahl ohne Vorzeichen, die Ereignisquelle identifizieren. Dieser Wert muss übereinstimmen der *nID* Template-Parameter verwendet, die in den zugehörigen [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Basisklasse.

*iid*<br/>
[in] Die IID, die die Dispatchschnittstelle identifiziert.

*piid*<br/>
[in] Zeiger auf die IID, die die Dispatchschnittstelle identifiziert.

*dispid*<br/>
[in] DISPID, die das angegebene Ereignis zu identifizieren.

*fn*<br/>
[in] Name des Ereignishandlerfunktion. Diese Funktion verwenden, muss die `_stdcall` Aufrufkonvention und die Signatur entsprechenden Dispinterface-Format haben.

*info*<br/>
[in] Typinformationen Sie für die Ereignishandlerfunktion. Diese Typinformationen erfolgt in Form eines Zeigers auf ein `_ATL_FUNC_INFO` Struktur. CC_CDECL ist die einzige Option, die in Windows CE unterstützt wird, für das Feld CALLCONV, der die `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt somit das Verhalten nicht definiert.

### <a name="remarks"></a>Hinweise

Die ersten vier Makroparameter sind identisch mit denen für die [SINK_ENTRY_EX](#sink_entry_ex) Makro. Der letzte Parameter stellt die Typinformationen für das Ereignis bereit. CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[Globale Funktionen zusammengesetzter Steuerelemente](../../atl/reference/composite-control-global-functions.md)
