---
title: COM-Zuordnungsmakros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74f8903d81a126a6647bc43018f8422296ddf970
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358422"
---
# <a name="com-map-macros"></a>COM-Zuordnungsmakros
Diese Makros definieren Zuordnungen von COM-Schnittstelle.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Markiert den Beginn der COM-Schnittstelle-Zuordnungseinträge.|  
|[END_COM_MAP](#end_com_map)|Markiert das Ende der COM-Schnittstelle-Zuordnungseinträge.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_com_map"></a>  BEGIN_COM_MAP  
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
  

  
##  <a name="end_com_map"></a>  END_COM_MAP  
 Beendet die Definition der COM-schnittstellenzuordnung an.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale COM-Zuordnungs-Funktionen](../../atl/reference/com-map-global-functions.md)
