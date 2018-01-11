---
title: ComPtrRef-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef
dev_langs: C++
helpviewer_keywords: ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b1bbe134f15fdba6863f1725cbcc7effcb6d94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrref-class"></a>ComPtrRef-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein [ComPtr\<T >](../windows/comptr-class.md) Typ "oder" daraus abgeleitete, nicht nur die Schnittstelle, die durch das comptr-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Repräsentiert einen Verweis auf ein Objekt des Typs ComPtr\<T >.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef-Konstruktor](../windows/comptrref-comptrref-constructor.md)|Initialisiert eine neue Instanz der ComPtrRef-Klasse aus dem angegebenen Zeiger auf ein anderes ComPtrRef-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf-Methode](../windows/comptrref-getaddressof-method.md)|Ruft die Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen ComPtrRef-Objekt dargestellt wird.|  
|[ComPtrRef::ReleaseAndGetAddressOf-Methode](../windows/comptrref-releaseandgetaddressof-method.md)|Löscht die aktuelle ComPtrRef-Objekt und gibt einen Zeiger-auf-a-Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wurde.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType**-Operator](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Löscht die aktuelle ComPtrRef-Objekt und gibt einen Zeiger-auf-a-Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wurde.|  
|[ComPtrRef::operator T*-Operator](../windows/comptrref-operator-t-star-operator.md)|Gibt den Wert der [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember des aktuellen ComPtrRef-Objekts.|  
|[ComPtrRef::operator void**-Operator](../windows/comptrref-operator-void-star-star-operator.md)|Löscht die aktuelle ComPtrRef-Objekt, wandelt den Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wurde, als ein Zeiger-auf-Zeiger-auf `void`, und klicken Sie dann die Cast-Zeiger zurückgibt.|  
|[ComPtrRef::operator*-Operator](../windows/comptrref-operator-star-operator.md)|Ruft ab, die Zeiger auf die Schnittstelle, die vom aktuellen ComPtrRef-Objekt dargestellt wird.|  
|[ComPtrRef::operator==-Operator](../windows/comptrref-operator-equality-operator.md)|Gibt an, ob zwei ComPtrRef-Objekte gleich sind.|  
|[ComPtrRef::operator!=-Operator](../windows/comptrref-operator-inequality-operator.md)|Gibt an, ob zwei ComPtrRef-Objekte nicht gleich sind.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)