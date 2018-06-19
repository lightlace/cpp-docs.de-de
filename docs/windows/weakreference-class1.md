---
title: WeakReference Class1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a44b992138371ff33a9059990a5ec3e93689c679
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891645"
---
# <a name="weakreference-class1"></a>WeakReference Class1
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>Hinweise  
 Stellt eine *schwachen Verweis* , mit dem Windows-Runtime oder eine klassische COM verwendet werden kann Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.  
  
 Ein `WeakReference` -Objekt verwaltet einen *starken Verweis*, ist ein Zeiger auf ein Objekt und ein *starken Verweiszähler*, dies entspricht der Anzahl von Kopien der starke Verweis, die durch verteilt wurden die 'Resolve()'-Methode. Während die Anzahl der starken Verweis ungleich NULL ist, der starke Verweis gültig ist und das Objekt zugegriffen werden kann. Wenn die Anzahl der starken Verweis 0 (null) wird, der starke Verweis ungültig ist, und das Objekt kann nicht zugegriffen werden.  
  
 WeakReference-Objekt wird normalerweise verwendet, um ein Objekt darzustellen, dessen Vorhandensein von einem externen Thread oder einer Anwendung gesteuert wird. Erstellen Sie z. B. ein WeakReference-Objekt aus einen Verweis auf ein Objekt "Datei". Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.  
  
 Die WeakReference-Methoden sind threadsicher.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakReference::WeakReference-Konstruktor](../windows/weakreference-weakreference-constructor.md)|Initialisiert eine neue Instanz der WeakReference-Klasse.|  
|[WeakReference::~WeakReference-Destruktor](../windows/weakreference-tilde-weakreference-destructor.md)|Hebt die Initialisierung (zerstört) der aktuellen Instanz der WeakReference-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference-Methode](../windows/weakreference-decrementstrongreference-method.md)|Dekrementiert den Wert der starke Verweis zählen das aktuelle WeakReference-Objekt.|  
|[WeakReference::IncrementStrongReference-Methode](../windows/weakreference-incrementstrongreference-method.md)|Inkrementiert den Verweiszähler starken Verweis von der aktuellen WeakReference-Objekt.|  
|[WeakReference::Resolve-Methode](../windows/weakreference-resolve-method.md)|Legt des angegebenen Zeigers auf den aktuellen Wert der starken Verweis, wenn die Anzahl der starken Verweis ungleich NULL ist.|  
|[WeakReference::SetUnknown-Methode](../windows/weakreference-setunknown-method.md)|Legt fest, den starken Verweis von der aktuellen WeakReference-Objekt an den angegebenen Schnittstellenzeiger auf.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `WeakReference`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)