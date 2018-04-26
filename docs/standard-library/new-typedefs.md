---
title: '&lt;new&gt; typedefs | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.openlocfilehash: 53a13168986171d3240cc15e405fc08b3db07e96
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

||
|-|
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
