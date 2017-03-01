---
title: Sie _ATL_FUNC_INFO Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c18e1c5a41ef910cfe327fdbdd8d8885ef30a092
ms.lasthandoff: 02/24/2017

---
# <a name="atlfuncinfo-structure"></a>Sie _ATL_FUNC_INFO-Struktur
Enthält Informationen zum Beschreiben einer Methode oder Eigenschaft auf eine Disp-Schnittstelle verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>Mitglieder  
 **cc**  
 Die Aufrufkonvention. Bei Verwendung dieser Struktur mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) -Klasse, bei diesem Member muss **CC_STDCALL**. `CC_CDECL`ist die einzige Option, die in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt somit das Verhalten nicht definiert.  
  
 **vtReturn**  
 Der Rückgabewert der Varianten-Typs der Funktion.  
  
 **nParams**  
 Die Anzahl der Funktionsparameter.  
  
 **pVarTypes**  
 Ein Array von variant-Typen der Funktionsparameter.  
  
## <a name="remarks"></a>Hinweise  
 Intern verwendet ATL diese Struktur zum Speichern von Informationen aus einer Typbibliothek abgerufen. Möglicherweise können Sie diese Struktur direkt bearbeiten, wenn die Bereitstellung von Typinformationen für ein Ereignishandler mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Klasse und [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) Makro.  
  
## <a name="example"></a>Beispiel  
 Erhält eine Dispinterface-Methode, die in der IDL definiert:  
  
 [!code-cpp[NVC_ATL_Windowing&#139;](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 Definieren Sie eine `_ATL_FUNC_INFO` Struktur:  
  
 [!code-cpp[NVC_ATL_Windowing&#140;](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)






