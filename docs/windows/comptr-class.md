---
title: ComPtr-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94146661b9a00b17732ce75f75bcc0194dcbddd4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882787"
---
# <a name="comptr-class"></a>ComPtr-Klasse
Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. ComPtr verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf 0 geht.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename T>  
class ComPtr;  
  
template<class T>  
friend class ComPtr;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Schnittstelle, der das ComPtr-Objekt entspricht.  
  
 `U`  
 Eine Klasse, für die das aktuelle ComPtr-Objekt ein Freund ist. (Die Vorlage, die diesen Parameter verwendet, ist geschützt.)  
  
## <a name="remarks"></a>Hinweise  
 ComPtr<> deklariert einen Typ, der den zugrunde liegenden Schnittstellenzeiger darstellt. ComPtr <> verwenden, um eine Variable deklarieren und verwenden Sie dann auf den Pfeil-Memberzugriffsoperator (`->`) auf eine Schnittstellenmemberfunktion zuzugreifen.  
  
 Weitere Informationen zu intelligenten Zeigern finden Sie in der MSDN Library im Thema [COM Coding Practices](http://msdn.microsoft.com/en-us/76aca556-b4d6-4e67-a2a3-4439900f0c39)im Unterabschnitt „Intelligente Zeiger für COM“.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InterfaceType`|Ein Synonym für den Typ, der durch den `T` -Vorlagenparameter angegeben ist.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtr::ComPtr-Konstruktor](../windows/comptr-comptr-constructor.md)|Initialisiert eine neue Instanz der ComPtr-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.|  
|[ComPtr::~ComPtr-Destruktor](../windows/comptr-tilde-comptr-destructor.md)|Hebt die Initialisierung einer Instanz von ComPtr auf.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtr::As-Methode](../windows/comptr-as-method.md)|Gibt ein ComPtr-Objekt zurück, das die Schnittstelle darstellt, die durch den angegebenen Vorlagenparameter gekennzeichnet ist.|  
|[ComPtr::AsIID-Methode](../windows/comptr-asiid-method.md)|Gibt ein ComPtr-Objekt zurück, das die Schnittstelle darstellt, die durch die angegebene Schnittstellen-ID gekennzeichnet ist.|  
|[ComPtr::AsWeak-Methode](../windows/comptr-asweak-method.md)|Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.|  
|[ComPtr::Attach-Methode](../windows/comptr-attach-method.md)|Verknüpft dieses ComPtr-Objekt mit dem Schnittstellentyp, der durch den Typparameter der aktuellen Vorlage angegeben ist.|  
|[ComPtr::CopyTo-Methode](../windows/comptr-copyto-method.md)|Kopiert die aktuelle oder angegebene-Schnittstelle, die diesem ComPtr-Objekt zugeordnet ist, in den angegebenen Ausgabezeiger.|  
|[ComPtr::Detach-Methode](../windows/comptr-detach-method.md)|Hebt die Zuordnung dieses ComPtr-Objekts zu der Benutzeroberfläche auf, der das Objekt entspricht.|  
|[ComPtr::Get-Methode](../windows/comptr-get-method.md)|Ruft einen Zeiger auf die Schnittstelle ab, die diesem ComPtr-Objekt zugeordnet ist.|  
|[ComPtr::GetAddressOf-Methode](../windows/comptr-getaddressof-method.md)|Ruft die Adresse des [ptr_](../windows/comptr-ptr-data-member.md) -Datenmembers ab, der einen Zeiger auf die Schnittstelle enthält, der dieses ComPtr-Objekt entspricht.|  
|[ComPtr::ReleaseAndGetAddressOf-Methode](../windows/comptr-releaseandgetaddressof-method.md)|Gibt die Schnittstelle frei, die diesem ComPtr-Objekt zugeordnet ist, und ruft dann die Adresse des [ptr_](../windows/comptr-ptr-data-member.md) -Datenmembers ab, der einen Zeiger auf die Schnittstelle enthält, die freigegeben wurde.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|Gibt alle Verweise für den Zeiger auf die Schnittstelle an, die diesem ComPtr zugeordnet ist.|  
|[ComPtr::Swap-Methode](../windows/comptr-swap-method.md)|Tauscht die Schnittstelle, die von dem aktuellen ComPtr-Objekt verwaltet wird, gegen der Schnittstelle, die vom angegebenen ComPtr-Objekt verwaltet wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtr::InternalAddRef-Methode](../windows/comptr-internaladdref-method.md)|Inkrementiert den Verweiszähler der Schnittstelle, die diesem ComPtr-Objekt zugeordnet ist.|  
|[ComPtr::InternalRelease-Methode](../windows/comptr-internalrelease-method.md)|Führt einen COM-Freigabe-Vorgang für die Schnittstelle aus, die diesem ComPtr-Objekt zugeordnet ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Gibt an, ob ein ComPtr-Objekt die Objektlebensdauer einer Schnittstelle verwaltet.|  
|[ComPtr::operator&-Operator](../windows/comptr-operator-ampersand-operator.md)|Ruft die Adresse des aktuellen ComPtr-Objekts ab.|  
|[ComPtr::operator=-Operator](../windows/comptr-operator-assign-operator.md)|Weist dem aktuellen ComPtr-Objekt einen Wert zu.|  
|[ComPtr::operator->-Operator](../windows/comptr-operator-arrow-operator.md)|Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.|  
|[ComPtr::operator==-Operator](../windows/comptr-operator-equality-operator.md)|Gibt an, ob zwei ComPtr-Objekte gleich sind.|  
|[ComPtr::operator!=-Operator](../windows/comptr-operator-inequality-operator.md)|Gibt an, ob zwei ComPtr-Objekte ungleich sind.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ComPtr::ptr_-Datenmember](../windows/comptr-ptr-data-member.md)|Enthält einen Zeiger auf die Schnittstelle, die diesem ComPtr-Objekt zugeordnet ist und von ihm verwaltet wird.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)