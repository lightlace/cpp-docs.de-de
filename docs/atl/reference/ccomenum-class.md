---
title: Klasse CComEnum | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 72c172d7a619bb4fd1bd265e465653b691c0bc7b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenum-class"></a>CComEnum-Klasse
Diese Klasse definiert ein COM-Enumerator-Objekt basierend auf einem Array.  
  
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
 Das Threadingmodell der-Klasse. Dieser Parameter ist standardmäßig das globale Objekt Threadmodell in Ihrem Projekt verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `CComEnum`definiert ein COM-Enumerator-Objekt basierend auf einem Array. Diese Klasse entspricht dem [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) implementiert einen Enumerator basierend auf einen Container für die C++-Standardbibliothek. Schritte für die Verwendung dieser Klasse werden im folgenden beschrieben. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Diese Klasse verwendet:  
  
- `typedef`eine Spezialisierung dieser Klasse.  
  
-   Verwenden der `typedef` als Vorlagenargument in eine Spezialisierung der `CComObject`.  
  
-   Erstellen Sie eine Instanz der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt durch Aufrufen von [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Die Enumeratorschnittstelle an den Client zurückgeben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
## <a name="example"></a>Beispiel  
 Der folgende Code bietet eine wieder verwendbare Funktion zum Erstellen und initialisieren ein Enumeratorobjekt.  
  
 [!code-cpp[NVC_ATL_COM&#32;](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Diese Vorlagenfunktion kann zur Implementierung der `_NewEnum` Eigenschaft einer Auflistung-Schnittstelle, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM&33;](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Dieser Code erstellt ein `typedef` für `CComEnum` , verfügbar macht einen Vektor von **VARIANT**s über die **IEnumVariant** Schnittstelle. Die **CVariantArrayCollection** Klasse einfach spezialisiert **CreateEnumerator** zum Arbeiten mit Objekten der Enumerator von diesem Typ auf und übergibt die erforderlichen Argumente.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl-Klasse](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)

