---
title: 'Handlet:: Close-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab919b3aeba45462a15900429493225f00909d5a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602453"
---
# <a name="handletclose-method"></a>HandleT::Close-Methode

Schließt das aktuelle **HandleT** Objekt.

## <a name="syntax"></a>Syntax

```cpp
void Close();
```

## <a name="remarks"></a>Hinweise

Das Handle, das das aktuelle zugrunde liegende **HandleT** wird geschlossen, und die **HandleT** auf einen ungültigen Zustand festgelegt ist.

Wenn das Handle nicht ordnungsgemäß geschlossen wird, wird eine Ausnahme im aufrufenden Thread ausgelöst.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HandleT-Klasse](../windows/handlet-class.md)