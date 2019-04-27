---
title: _ATL_FUNC_INFO-Struktur
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: f6cf32bab86d741f3b0750c150c7bbc647b27ddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248692"
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO-Struktur

Enthält Informationen verwendet, um eine Methode oder Eigenschaft auf einen Disp-Schnittstelle zu beschreiben.

## <a name="syntax"></a>Syntax

```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Member

`cc`<br/>
Die Aufrufkonvention. Bei Verwendung dieser Struktur mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) -Klasse, dieses Element muss CC_STDCALL sein. `CC_CDECL` ist die einzige Option in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt somit das Verhalten nicht definiert.

`vtReturn`<br/>
Der Variante-Typ der Funktion-Rückgabewert.

`nParams`<br/>
Die Anzahl der Funktionsparameter.

`pVarTypes`<br/>
Ein Array von variant-Typen der Funktionsparameter.

## <a name="remarks"></a>Hinweise

Intern verwendet ATL diese Struktur zum Speichern von Informationen aus einer Typbibliothek abgerufen. Möglicherweise müssen Sie diese Struktur direkt bearbeiten, wenn Sie angeben, dass Typinformationen für einen Ereignishandler, der verwendet wird, mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Klasse und [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) Makro.

## <a name="example"></a>Beispiel

Eine Dispinterface-Methode, die in der IDL definiert:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

Definieren Sie eine `_ATL_FUNC_INFO` Struktur:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Anforderungen

Header: atlcom.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
