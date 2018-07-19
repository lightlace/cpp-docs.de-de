---
title: CComEnum-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd8fe2120ad42d7df223d05a43591937ffcce6e2
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885388"
---
# <a name="ccomenum-class"></a>CComEnum-Klasse
Diese Klasse definiert ein COM-Enumerator-Objekt basierend auf einem Wertearray.  
  
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
 *Basis*  
 Eine COM-Enumerators ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) Schnittstelle.  
  
 *piid*  
 Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.  
  
 *T*  
 Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.  
  
 *Kopieren*  
 Eine homogene [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 *ThreadModel*  
 Das Threadingmodell der-Klasse. Dieser Parameter ist standardmäßig auf das globale Objekt Thread-Modell in Ihrem Projekt verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `CComEnum` definiert ein COM-Enumerator-Objekt basierend auf einem Wertearray. Diese Klasse ist analog zu [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) implementiert einen Enumerator, der basierend auf einem C++-Standardbibliothek-Container. Typische Schritte bei der Verwendung dieser Klasse werden im folgenden beschrieben. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Diese Klasse verwenden zu können:  
  
- **TypeDef** eine Spezialisierung dieser Klasse.  
  
-   Verwenden der **Typedef** als Vorlagenargument in einer Spezialisierung von `CComObject`.  
  
-   Erstellen Sie eine Instanz von der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt durch Aufrufen [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Die Enumeratorschnittstelle an den Client zurückgeben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
## <a name="example"></a>Beispiel  
 Der folgenden Code enthält eine wiederverwendbare Funktion zum Erstellen und initialisieren ein Enumeratorobjekt.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Diese Vorlagenfunktion kann zum Implementieren der `_NewEnum` Eigenschaft einer Auflistung-Schnittstelle, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Dieser Code erstellt eine **Typedef** für `CComEnum` , verfügbar macht, einen Vektor von Varianten, die über die `IEnumVariant` Schnittstelle. Die `CVariantArrayCollection` Klasse einfach spezialisiert `CreateEnumerator` zum Arbeiten mit Objekten der Enumerator von diesem Typ und übergibt die erforderlichen Argumente.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl-Klasse](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)
