---
title: ActivatableClass-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs:
- C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa178126b3a749e3af67b9dae3711c0a5cf9f408
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645785"
---
# <a name="activatableclass-macros"></a>ActivatableClass-Makros

Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können.

## <a name="syntax"></a>Syntax

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>Parameter

*Klassenname*  
Name des zu erstellenden Klasse.  

*Factory*  
Eine Factory, die eine Instanz der angegebenen Klasse erstellt.

*ServerName*  
Ein Name, der eine Teilmenge der Factorys im Modul angibt.

## <a name="remarks"></a>Hinweise

Verwenden Sie nicht diese Makros mit klassischen COM-es sei denn, Sie verwenden die `#undef` Richtlinie, um sicherzustellen, dass die `__WRL_WINRT_STRICT__` Makrodefinition entfernt wird.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)