---
title: ComPtr::Reset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 86e7716ff4e9a0b4f5132abfd431a2649f22f80f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593092"
---
# <a name="comptrreset"></a>ComPtr::Reset

Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist **ComPtr**.

## <a name="syntax"></a>Syntax

```cpp
unsigned long Reset();
```

## <a name="return-value"></a>Rückgabewert

Die Anzahl der freigegeben Verweise, sofern vorhanden.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)