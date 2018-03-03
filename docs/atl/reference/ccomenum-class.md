---
title: CComEnum Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 792c5ff95858936d38d9a87350dd3ca405c5ec66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomenum-class"></a>CComEnum-Klasse
Diese Klasse definiert ein COM-Enumerator-Objekt basierend auf ein Array.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
 public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Eine COM-Enumerator ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.  
  
 `T`  
 Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.  
  
 `Copy`  
 Eine homogene [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Das Threadingmodell der-Klasse. Dieser Parameter ist standardmäßig auf das globale Thread Objektmodell in Ihrem Projekt verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `CComEnum`definiert ein COM-Enumerator-Objekt basierend auf ein Array an. Diese Klasse ist analog zu [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) implementiert einen Enumerator basierend auf einen Container für die C++-Standardbibliothek. Typische Schritte bei der Verwendung dieser Klasse werden unten aufgeführt. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Diese Klasse verwenden zu können:  
  
- `typedef`eine Spezialisierung dieser Klasse.  
  
-   Verwenden der `typedef` als Vorlagenargument in einer Spezialisierung von `CComObject`.  
  
-   Erstellen Sie eine Instanz von der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt, durch den Aufruf [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Die Enumeratorschnittstelle an den Client zurückzugeben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
## <a name="example"></a>Beispiel  
 Der unten gezeigte Code bietet eine wieder verwendbare Funktion zum Erstellen und initialisieren ein Enumeratorobjekt.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Diese Vorlagenfunktion dienen zum Implementieren der `_NewEnum` Eigenschaft eine Auflistungsschnittstelle, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Dieser Code erstellt ein `typedef` für `CComEnum` verfügbar macht einen Vektor von **VARIANT**s über die **IEnumVariant** Schnittstelle. Die **CVariantArrayCollection** Klasse einfach spezialisiert **CreateEnumerator** zum Arbeiten mit Objekten der Enumerator von diesem Typ auf und übergibt die erforderlichen Argumente.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl-Klasse](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)
