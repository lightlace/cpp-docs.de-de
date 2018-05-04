---
title: CComObjectRoot Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6a7d350f7bd50476c1c327d824089981d3e8321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot-Klasse
Diese Typdefinition des [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist für die Standardeinstellung des Servers Threadingmodell vorlagenbasiert.  
  
## <a name="syntax"></a>Syntax  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectRoot` ist eine `typedef` von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) für die Standardeinstellung des Servers Threadingmodell vorlagenbasiert. Daher [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) verweist entweder [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx` objektverwaltung Verweis Anzahl für aggregierte und aggregierte Objekte verarbeitet werden. Sie enthält den Verweiszählerwert des Objekts, wenn Ihr Objekt wird nicht aggregiert, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt aggregiert wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können verwendet werden, die Fehler beim Erstellen des inneren Objekts behandeln und zu schützen, das äußere Objekt löschen, wenn innere Schnittstellen freigegeben werden oder das innere Objekt werden gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx Klassenmember](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
