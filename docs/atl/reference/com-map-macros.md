---
title: COM-Zuordnungs-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 00c15bf8567456254c8a338ed395a726fcbe8c9b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879308"
---
# <a name="com-map-macros"></a>COM-Zuordnungs-Makros
Diese Makros definieren Zuordnungen von COM-Schnittstelle.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Markiert den Beginn der Zuordnungseintrags-COM-Schnittstelle.|  
|[END_COM_MAP](#end_com_map)|Markiert das Ende der Zuordnungseintrags-COM-Schnittstelle.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_com_map"></a>  BEGIN_COM_MAP  
 Die COM-Zuordnung ist der Mechanismus, der für ein Objekt über für einen Client-Schnittstellen bereitstellen `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name des Klassenobjekts, den Sie für Schnittstellen bereitstellen.  
  
### <a name="remarks"></a>Hinweise  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) Zeiger für Schnittstellen in der COM-Zuordnung zurückgibt. Starten Sie die schnittstellenzuordnung ein, mit der-Makro, fügen Sie Einträge für die einzelnen Schnittstellen mit der [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) Makro oder eine ihrer Varianten, und führen Sie die Zuordnung mit der [END_COM_MAP](#end_com_map) -Makro.  

  
### <a name="example"></a>Beispiel  
 Von ATL [BEEPER](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>  END_COM_MAP  
 Beendet die Definition der Zuordnung COM-Schnittstelle.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale COM-Zuordnungs-Funktionen](../../atl/reference/com-map-global-functions.md)
