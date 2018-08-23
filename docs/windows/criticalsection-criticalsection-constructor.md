---
title: 'CriticalSection:: CriticalSection-Konstruktor | Microsoft-Dokumentation'
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
ms.openlocfilehash: 892a32c6ff6f8e9a3a30452d05dd6e15c38a4fa8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605051"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection-Konstruktor

Initialisiert ein Synchronisierungsobjekt, das ist vergleichbar mit dem ein Mutex-Objekt, aber nur die Threads eines einzelnen Prozesses verwendet werden kann.

## <a name="syntax"></a>Syntax

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parameter

*spinCount*  
Die Spin-Anzahl für das Objekt des kritischen Abschnitts. Der Standardwert ist 0.

## <a name="remarks"></a>Hinweise

Weitere Informationen über kritische Abschnitte und Spincounts finden Sie unter den `InitializeCriticalSectionAndSpinCount` Funktion in der **Synchronisierung** Teil der Windows-API-Dokumentation.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[CriticalSection-Klasse](../windows/criticalsection-class.md)