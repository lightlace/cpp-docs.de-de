---
title: 'CriticalSection:: CriticalSection-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 532a7b2e046bbdb64db118741a939dadb049f081
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection-Konstruktor
Initialisiert ein Synchronisierungsobjekt, das ein Mutex-Objekt ähnelt, jedoch kann von nur die Threads eines einzelnen Prozesses verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `spincount`  
 Die Anzahl der Drehfeld für die kritischen Abschnittsobjekt. Der Standardwert ist 0.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über kritische Abschnitte und Spincounts finden Sie unter der **InitializeCriticalSectionAndSpinCount** -Funktion in der Synchronisierungsbereich des der Windows-API-Dokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSection-Klasse](../windows/criticalsection-class.md)
