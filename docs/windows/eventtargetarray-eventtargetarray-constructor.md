---
title: 'Eventtargetarray:: Eventtargetarray-Konstruktor | Microsoft-Dokumentation'
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
ms.openlocfilehash: 831c9a524f8120c855382d198a5f53ac312cada6
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569787"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray-Konstruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *HR*  
 Nach diesem Konstruktor-Vorgänge Parameter *hr* gibt an, ob das Array Zuordnung erfolgreich war oder nicht. Die folgende Tabelle enthält die möglichen Werte für *hr*.  
  
 S_OK  
 Der Vorgang wurde erfolgreich ausgeführt.  
  
 E_OUTOFMEMORY  
 Arbeitsspeicher konnte nicht für das Array zugeordnet werden.  
  
 S_FALSE  
 Parameter *Elemente* ist kleiner als oder gleich 0 (null).  
  
 *Elemente*  
 Die Anzahl der Elemente des Arrays zugewiesen werden.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem **EventTargetArray** Klasse.  
  
 **EventTargetArray** wird verwendet, um ein Array von Ereignishandlern in behalten eine `EventSource` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)