---
title: ActivatableClass-Makros
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 7d38db9e7d3fa94c89195b6379e14692f26f7ee5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62304136"
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

*className*<br/>
Name des zu erstellenden Klasse.

*factory*<br/>
Eine Factory, die eine Instanz der angegebenen Klasse erstellt.

*serverName*<br/>
Ein Name, der eine Teilmenge der Factorys im Modul angibt.

## <a name="remarks"></a>Hinweise

Verwenden Sie nicht diese Makros mit klassischen COM-es sei denn, Sie verwenden die `#undef` Richtlinie, um sicherzustellen, dass die `__WRL_WINRT_STRICT__` Makrodefinition entfernt wird.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](module-class.md)