---
title: Zusammengesetztes Steuerelement Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b609801a1716e47b208644be02d4746abf8c288a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="composite-control-macros"></a>Makros von zusammengesetzten Steuerelementen
Diese Makros definieren ereignissenkenzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Markiert den Beginn der Ereignis-Sink-Zuordnung für den zusammengesetzten Steuerelements an.|  
|[END_SINK_MAP](#end_sink_map)|Markiert das Ende der Zuordnung Ereignissenke für den zusammengesetzten Steuerelements.|  
|[SINK_ENTRY](#sink_entry)|Der Eintrag in der Senke ereigniszuordnung.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Eintritt in die Senke ereigniszuordnung einen zusätzlichen Parameter.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Ähnliche SINK_ENTRY_EX, außer dass es sich um einen Zeiger auf die Iid verwendet.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Eintritt in die Senke ereigniszuordnung mit manuell angegebenen Typinformationen für die Verwendung mit [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Ähnliche SINK_ENTRY_INFO, außer dass es sich um einen Zeiger auf die Iid verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  

##  <a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 Deklariert den Anfang der Ereignis-Sink-Zuordnung für den zusammengesetzten Steuerelements an.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt das Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="end_sink_map"></a>END_SINK_MAP  
 Deklariert das Ende der Ereignis-Sink-Zuordnung für den zusammengesetzten Steuerelements an.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry"></a>SINK_ENTRY  
 Die Handlerfunktion deklariert ( `fn`) für das angegebene Ereignis ( `dispid`), der das angegebene Steuerelement `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Bezeichnet das Steuerelement.  
  
 `dispid`  
 [in] Gibt das angegebene Ereignis an.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwenden und über die entsprechenden Dispinterface-Stil Signatur verfügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry_ex"></a>SINK_ENTRY_EX und SINK_ENTRY_EX_P
 Deklariert die Handlerfunktion ( `fn`) für das angegebene Ereignis ( `dispid`), der die Dispatchschnittstelle ( *Iid)*, für das angegebene Steuerelement `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Bezeichnet das Steuerelement.  
  
 `iid`  
 [in] Identifiziert die Dispatchschnittstelle.  

 `piid`  
 [in] Zeiger auf die Dispatchschnittstelle.  
  
 `dispid`  
 [in] Gibt das angegebene Ereignis an.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwenden und über die entsprechenden Dispinterface-Stil Signatur verfügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry_info"></a>SINK_ENTRY_INFO und SINK_ENTRY_INFO_P  
 Verwenden der `SINK_ENTRY_INFO` Makro innerhalb einer Ereignissenke-Adresszuordnung mit dem Bereitstellen der erforderlichen Informationen für [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Route von Ereignissen an die entsprechenden Handlerfunktion.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifizieren die Ereignisquelle Ganzzahl ohne Vorzeichen. Dieser Wert muss übereinstimmen. die `nID` Vorlagenparameter verwendet, die in den zugehörigen [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Basisklasse.  
  
 `iid`  
 [in] Die IID, die die Schnittstelle für die Verteilung bezeichnet.  

 `piid`  
 [in] Ein Zeiger auf die IID, die die Schnittstelle für die Verteilung bezeichnet.
  
 `dispid`  
 [in] DISPID, die das angegebene Ereignis zu identifizieren.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwenden und über die entsprechenden Dispinterface-Stil Signatur verfügen.  
  
 `info`  
 [in] Informationen zum Ereignishandlerfunktion eingeben. Diese Typinformationen erfolgt in Form eines Zeigers auf eine `_ATL_FUNC_INFO` Struktur. `CC_CDECL`ist die einzige Option, die in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt, daher das Verhalten nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Die ersten vier Makroparameter sind identisch mit denen für die [SINK_ENTRY_EX](#sink_entry_ex) Makro. Der letzte Parameter stellt Typinformationen für das Ereignis bereit. CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  

## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale Funktionen zusammengesetzter Steuerelemente](../../atl/reference/composite-control-global-functions.md)
