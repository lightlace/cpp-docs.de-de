---
title: 'Eventtargetarray:: Eventtargetarray-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbfd12ea513044f1062e60f5c73f5089683f043d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872714"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray-Konstruktor
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hr`  
 Nachdem diese Vorgänge Konstruktor Parameter `hr` gibt an, ob die Zuordnung des Arrays erfolgreich war oder nicht. Die folgende Tabelle enthält die möglichen Werte für `hr`.  
  
 S_OK  
 Der Vorgang wurde erfolgreich ausgeführt.  
  
 E_OUTOFMEMORY  
 Arbeitsspeicher konnte nicht für das Array zugeordnet werden.  
  
 S_FALSE  
 Parameter `items` ist kleiner oder gleich 0 (null).  
  
 `items`  
 Die Anzahl von Arrayelementen zu reservieren.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der EventTargetArray-Klasse.  
  
 EventTargetArray wird verwendet, um ein Array von Ereignishandlern in einem EventSource-Objekt beizubehalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)