---
title: HStringReference-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs: C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97900bd44dfdcede187b20b181c64d235eac60fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreference-class"></a>HStringReference-Klasse
Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Lebensdauer des Hintergrundpuffers im neuen HSTRING wird nicht von Windows-Runtime verwaltet. Der Aufrufer ordnet eine Quellzeichenfolge auf dem Stapelrahmen zu, um eine Heapzuweisung zu vermeiden und das Risiko eines Speicherverlusts auszuschließen. Außerdem muss der Aufrufer sicherstellen, dass die Quellzeichenfolge während der Lebensdauer des angefügten HSTRING unverändert bleibt. Weitere Informationen finden Sie unter [WindowsCreateStringReference Funktion](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HStringReference::HStringReference-Konstruktor](../windows/hstringreference-hstringreference-constructor.md)|Initialisiert eine neue Instanz der HStringReference-Klasse.|  
  
### <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[HStringReference::CopyTo-Methode](../windows/hstringreference-copyto-method.md)|Kopiert das aktuelle HStringReference-Objekt zu einem HSTRING-Objekt.|  
|[HStringReference::Get-Methode](../windows/hstringreference-get-method.md)|Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HStringReference::Operator=-Operator](../windows/hstringreference-operator-assign-operator.md)|Verschiebt den Wert eines anderen HStringReference-Objekts zum aktuellen HStringReference-Objekt.|  
|[HStringReference::Operator==-Operator](../windows/hstringreference-operator-equality-operator.md)|Gibt an, ob die zwei Parameter gleich sind.|  
|[HStringReference::Operator!=-Operator](../windows/hstringreference-operator-inequality-operator.md)|Gibt an, ob die zwei Parameter ungleich sind.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HStringReference`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)