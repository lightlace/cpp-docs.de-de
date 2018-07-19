---
title: 'Event:: Event Constructor (Windows Runtime C++-Vorlagenbibliothek) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs:
- C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a63e7ddbf2528b78eac7761bbcf4891f31cc886
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882627"
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event Constructor (C++-Vorlagenbibliothek der Windows Runtime)
Initialisiert eine neue Instanz der Ereignisklasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Handle für ein Ereignis. `h` wird standardmäßig mit `nullptr` initialisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/event-class-windows-runtime-cpp-template-library.md)