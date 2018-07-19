---
title: 'CriticalSection:: CriticalSection-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d86c80d169cb6d9794f163290c30bf1b2563588b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870896"
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
