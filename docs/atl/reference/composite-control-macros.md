---
title: Makros zusammengesetzter Steuerelemente | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 9fb8a907c8052c9816d6b87247e903a63f34a5be
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-macros"></a>Makros zusammengesetzter Steuerelemente
Diese Makros definieren ereignissenkenzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Kennzeichnet den Anfang der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.|  
|[END_SINK_MAP](#end_sink_map)|Markiert das Ende der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.|  
|[SINK_ENTRY](#sink_entry)|Eintrag der Ereignis-Sink-Zuordnung.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Eintrag der Ereignis-Sink-Zuordnung mit einem zusätzlichen Parameter.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Ähnlich wie SINK_ENTRY_EX außer dass es sich um einen Zeiger auf die Iid verwendet.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Eintrag in der Ereignis-Sink-Zuordnung mit manuell angegebenen Typinformationen für die Verwendung mit [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Ähnlich wie SINK_ENTRY_INFO außer dass es sich um einen Zeiger auf die Iid verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  

##  <a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 Deklariert den Beginn der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt das Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="end_sink_map"></a>END_SINK_MAP  
 Deklariert das Ende der Ereignis-Sink-Zuordnung für das zusammengesetzte Steuerelement.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry"></a>SINK_ENTRY  
 Die Handlerfunktion deklariert ( `fn`) für das angegebene Ereignis ( `dispid`), der das angegebene Steuerelement `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Steuerelement.  
  
 `dispid`  
 [in] Gibt das angegebene Ereignis.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwendet und die entsprechenden Dispinterface-Stil Signatur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry_ex"></a>SINK_ENTRY_EX und SINK_ENTRY_EX_P
 Die Handlerfunktion deklariert ( `fn`) für das angegebene Ereignis ( `dispid`), der Dispatchschnittstelle ( *Iid)*, für das angegebene Steuerelement `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Steuerelement.  
  
 `iid`  
 [in] Identifiziert die Dispatchschnittstelle.  

 `piid`  
 [in] Zeiger auf die Dispatchschnittstelle.  
  
 `dispid`  
 [in] Gibt das angegebene Ereignis.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwendet und die entsprechenden Dispinterface-Stil Signatur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#136;](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Hinweise  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
##  <a name="sink_entry_info"></a>SINK_ENTRY_INFO und SINK_ENTRY_INFO_P  
 Verwenden der `SINK_ENTRY_INFO` Makro in eine Event Sink-Zuordnung, die vom benötigten Informationen bereitzustellen [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Weiterleiten von Ereignissen an die entsprechenden Handler-Funktion.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifizieren die Ereignisquelle Ganzzahl ohne Vorzeichen. Dieser Wert muss übereinstimmen der `nID` Vorlagenparameter verwendet, in der verknüpften [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) Basisklasse.  
  
 `iid`  
 [in] Die IID, die die Dispatchschnittstelle identifiziert.  

 `piid`  
 [in] Ein Zeiger auf die IID, die die Dispatchschnittstelle identifiziert.
  
 `dispid`  
 [in] DISPID identifizieren das angegebene Ereignis.  
  
 `fn`  
 [in] Name der Ereignishandlerfunktion. Diese Funktion verwenden, muss die **_stdcall** -Aufrufkonvention verwendet und die entsprechenden Dispinterface-Stil Signatur.  
  
 `info`  
 [in] Geben Sie Informationen für die Ereignishandlerfunktion. Diese Typinformationen erfolgt in Form eines Zeigers auf eine `_ATL_FUNC_INFO` Struktur. `CC_CDECL`ist die einzige Option, die in Windows CE für unterstützt die `CALLCONV` Feld der `_ATL_FUNC_INFO` Struktur. Jeder andere Wert wird nicht unterstützt somit das Verhalten nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Die ersten vier Makroparameter sind identisch mit denen für die [SINK_ENTRY_EX](#sink_entry_ex) Makro. Der letzte Parameter stellt Typinformationen für das Ereignis bereit. CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  

## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale Funktionen zusammengesetzter Steuerelemente](../../atl/reference/composite-control-global-functions.md)

