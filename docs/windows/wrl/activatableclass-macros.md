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
ms.openlocfilehash: eee8267e2e76eead267eb2486836dbcc38a90231
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336013"
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