---
title: 'com:: PTR | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr
dev_langs:
- C++
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5e6a3f7936e21d22282fe37a29b5d91f2e50caa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434491"
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