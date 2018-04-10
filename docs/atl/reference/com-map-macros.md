---
title: COM-Zuordnungsmakros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e97db324dc8e130418419ef435e2665c84eb0b64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-macros"></a>COM-Zuordnungsmakros
Diese Makros definieren Zuordnungen von COM-Schnittstelle.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Markiert den Beginn der COM-Schnittstelle-Zuordnungseinträge.|  
|[END_COM_MAP](#end_com_map)|Markiert das Ende der COM-Schnittstelle-Zuordnungseinträge.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 Die COM-Zuordnung ist der Mechanismus, der auf ein Objekt, das einem Client über Schnittstellen verfügbar macht `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name des Klassenobjekts, den Sie auf Schnittstellen bereitstellen.  
  
### <a name="remarks"></a>Hinweise  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) gibt nur die Zeiger für Schnittstellen in der COM-Zuordnung zurück. Starten Sie die schnittstellenzuordnung ein, mit der `BEGIN_COM_MAP` -Makro, fügen Sie Einträge für jede der Schnittstellen mit der [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) -Makro oder einer dessen Varianten und schließen Sie die Zuordnung mit der [END_COM_MAP](#end_com_map) Makro.  

  
### <a name="example"></a>Beispiel  
 Von ATL [BEEPER](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 Beendet die Definition der COM-schnittstellenzuordnung an.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale COM-Zuordnungs-Funktionen](../../atl/reference/com-map-global-functions.md)
