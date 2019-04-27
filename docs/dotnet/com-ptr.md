---
title: com::ptr
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
ms.openlocfilehash: 74e168fe916b930e499a82ca3fcf5c7d0d669719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209203"
---
# <a name="comptr"></a>com::ptr

Ein Wrapper für ein COM-Objekt, das als Mitglied einer CLR-Klasse verwendet werden kann. Der Wrapper automatisiert auch die Verwaltung der Lebensdauer der COM-Objekts, das im Besitz des Benutzers Verweise auf das Objekt freigeben, wenn der Destruktor aufgerufen wird. Analog zu [CComPtr-Klasse](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Syntax

```
#include <msclr\com\ptr.h>
```

## <a name="remarks"></a>Hinweise

[com:: PTR-Klasse](../dotnet/com-ptr-class.md) wird definiert, der \<msclr\com\ptr.h > Datei.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliothek](../dotnet/cpp-support-library.md)
