---
title: 'CriticalSection:: CriticalSection-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf4e9cd4d4fde31f1809e7d583e662188558d5b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 Weitere Informationen über Crticial Abschnitte und Spincounts finden Sie unter der **InitializeCriticalSectionAndSpinCount** -Funktion in der Synchronisierungsbereich des der Windows-API-Dokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSection-Klasse](../windows/criticalsection-class.md)