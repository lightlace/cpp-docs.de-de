---
title: _ATL_FUNC_INFO-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8852deacfd36ba988b9b31bdad363c05aee12b6e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882207"
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
 `cc`  
 Die Aufrufkonvention. Bei Verwendung dieser Struktur mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) -Klasse, dieses Element muss CC_STDCALL sein. `CC_CDECL` ist die einzige Option in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt somit das Verhalten nicht definiert.  
  
 `vtReturn`  
 Der Variante-Typ der Funktion-Rückgabewert.  
  
 `nParams`  
 Die Anzahl der Funktionsparameter.  
  
 `pVarTypes`  
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
  [Klassen und Strukturen](../../atl/reference/atl-classes.md)  
 [IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





