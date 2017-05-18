---
title: Klasse CComObjectRoot | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
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
ms.sourcegitcommit: 31295a07704e272799398aa82c6a9f0bbac17717
ms.openlocfilehash: 34653d55091a8e872f075010a0ef7cecbb3484c8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectroot-class"></a>CComObjectRoot-Klasse
Diese Typdefinition des [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist für die Standardeinstellung des Servers Threadingmodell vorlagenbasiert.  
  
## <a name="syntax"></a>Syntax  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectRoot`ist ein `typedef` von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) für die Standardeinstellung des Servers Threadingmodell vorlagenbasiert. Daher [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) verweist entweder [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx`Objekt Verweis Anzahl Management für aggregierte und aggregierten Objekte verarbeitet werden. Sie enthält den Verweiszähler des Objekts, wenn das Objekt wird nicht aggregiert, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt gerade zusammengesetzt wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können zum Behandeln des Fehlers des inneren Objekts zu erstellen und zu schützen, das äußere Objekt löschen Wenn innere Schnittstellen freigegeben werden oder das innere Objekt werden gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx Klassenmember](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

