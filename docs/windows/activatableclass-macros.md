---
title: ActivatableClass-Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs: C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6cd75d4075cfe590151f7746281640febb334ce9
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
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
Eine Factory, die eine Instanz der angegebenen Klasse erstellen.

*serverName*  
Ein Name, der eine Teilmenge der Factorys in das Modul angibt.

## <a name="remarks"></a>Hinweise

Verwenden Sie nicht diese Makros mit klassischen COM-es sei denn, Sie verwenden die `#undef` Richtlinie, um sicherzustellen, dass die **&#95; &#95; WRL_WINRT_STRICT &#95; &#95;**  Makrodefinition wird entfernt.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)