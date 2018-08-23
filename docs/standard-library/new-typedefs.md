---
title: '&lt;new&gt; typedefs | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: bbfe7d2c24cb589925c70c70235f6de112d274f1
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541455"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

| |
| - |
|[new_handler](#new_handler)|

## <a name="new_handler"></a> new_handler

Der Typ verweist auf eine Funktion, die als neuer Handler geeignet ist.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Hinweise

Diese Art von Handler-Funktion wird durch **operatornew** oder `operator new[]` aufgerufen, wenn diese eine Anforderung für zusätzlichen Speicher nicht erfüllen können.

### <a name="example"></a>Beispiel

Unter [set_new_handler](../standard-library/new-functions.md#set_new_handler) finden Sie ein Beispiel mit `new_handler` als Rückgabewert.

## <a name="see-also"></a>Siehe auch

[\<new>](../standard-library/new.md)<br/>
