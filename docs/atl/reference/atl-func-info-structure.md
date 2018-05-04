---
title: Sie _ATL_FUNC_INFO Struktur | Microsoft Docs
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
ms.openlocfilehash: d5f3b759591333a41c3bc9da083e8e724249d13d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="atlfuncinfo-structure"></a>Sie _ATL_FUNC_INFO-Struktur
Enthält die Typinformationen verwendet, um eine Methode oder Eigenschaft auf eine Dispinterface beschreiben.  
  
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
 **cc**  
 Die Aufrufkonvention. Bei Verwendung dieser Struktur mit den [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) -Klasse, bei diesem Member muss **CC_STDCALL**. `CC_CDECL` ist die einzige Option, die in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt, daher das Verhalten nicht definiert.  
  
 **vtReturn**  
 Der Rückgabewert der Varianten-Typs der Funktion.  
  
 **nParams**  
 Die Anzahl der Funktionsparameter.  
  
 **pVarTypes**  
 Ein Array von variant-Typen der Funktionsparameter.  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet diese Struktur intern zum Speichern von Informationen aus einer Typbibliothek abgerufen. Möglicherweise müssen Sie diese Struktur direkt zu bearbeiten, wenn die Bereitstellung von Typinformationen für ein Ereignishandler mit dem [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Klasse und [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) Makro.  
  
## <a name="example"></a>Beispiel  
 Erhält eine Dispinterface-Methode, die in der IDL definiert:  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 Definieren Sie eine `_ATL_FUNC_INFO` Struktur:  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





