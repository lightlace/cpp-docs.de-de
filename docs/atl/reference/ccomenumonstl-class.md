---
title: CComEnumOnSTL Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs: C++
helpviewer_keywords: CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 740d1d35781fcea7820bfcb32171b744534b20fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL-Klasse
Diese Klasse definiert ein COM-Enumerator-Objekt auf Grundlage einer C++-Standardbibliothek-Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>  
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
 T,
    Copy,
 CollType>,
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
 Ein [Richtlinie kopieren](../../atl/atl-copy-policy-classes.md) Klasse.  
  
 `CollType`  
 Eine C++-Standardbibliothek Container-Klasse.  
  
## <a name="remarks"></a>Hinweise  
 `CComEnumOnSTL`definiert ein COM-Enumerator-Objekt auf Grundlage einer C++-Standardbibliothek-Auflistung. Diese Klasse kann verwendet werden, alleine oder zusammen mit [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Typische Schritte bei der Verwendung dieser Klasse werden unten aufgeführt. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>So verwenden diese Klasse mit ICollectionOnSTLImpl:  
  
- `typedef`eine Spezialisierung dieser Klasse.  
  
-   Verwenden der `typedef` als Vorlagenargument in eine Spezialisierung der endgültigen `ICollectionOnSTLImpl`.  
  
 Finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md) ein Beispiel.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>So verwenden Sie diese Klasse unabhängig von ICollectionOnSTLImpl:  
  
- `typedef`eine Spezialisierung dieser Klasse.  
  
-   Verwenden der `typedef` als Vorlagenargument in einer Spezialisierung von `CComObject`.  
  
-   Erstellen Sie eine Instanz von der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt, durch den Aufruf [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).  
  
-   Die Enumeratorschnittstelle an den Client zurückzugeben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
## <a name="example"></a>Beispiel  
 Der unten gezeigte Code stellt eine generische Funktion, um die Erstellung und Initialisierung der Enumerator-Objekt zu behandeln:  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 Diese Vorlagenfunktion dienen zum Implementieren der `_NewEnum` Eigenschaft eine Auflistungsschnittstelle, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 Dieser Code erstellt ein `typedef` für `CComEnumOnSTL` verfügbar macht einen Vektor von `CComVariant`s mithilfe von der **IEnumVariant** Schnittstelle. Die **CVariantCollection** Klasse einfach spezialisiert **CreateSTLEnumerator** zum Arbeiten mit Objekten der Enumerator dieses Typs.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [-Beispiel: Demonstriert, ICollectionOnSTLImpl CComEnumOnSTL und benutzerdefinierte Richtlinienkopierklassen](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [IEnumOnSTLImpl-Klasse](../../atl/reference/ienumonstlimpl-class.md)
