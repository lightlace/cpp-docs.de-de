---
title: 'Module:: Module-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e96e6cf984196cbca3051eec397ae06e48e2f1c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406658"
---
# <a name="modulemodule-constructor"></a>Module::Module-Konstruktor

Initialisiert eine neue Instanz der dem **Modul** Klasse.

## <a name="syntax"></a>Syntax

```cpp
Module();
```

## <a name="remarks"></a>Hinweise

Dieser Konstruktor ist geschützt und kann nicht aufgerufen werden, mit der **neue** Schlüsselwort. Rufen Sie stattdessen entweder [Module:: GetModule-Methode](../windows/module-getmodule-method.md) oder [Module:: Create-Methode](../windows/module-create-method.md).

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)