---
title: auto_gcroot-Klasse
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
ms.openlocfilehash: cb89035d928b251c9cc0427612ce6853a96456a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534237"
---
# <a name="autogcroot-class"></a>auto_gcroot-Klasse

Automatische ressourcenverwaltung (z. B. [Auto_ptr-Klasse](../standard-library/auto-ptr-class.md)) die zum Einbetten von eines virtuellen Handles in einen systemeigenen Typ verwendet werden können.

## <a name="syntax"></a>Syntax

```cpp
template<typename _element_type>
class auto_gcroot;
```

#### <a name="parameters"></a>Parameter

*_element_type*<br/>
Der verwaltete Typ eingebettet werden.

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\auto_gcroot.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot-Members](../dotnet/auto-gcroot-members.md)<br/>
[Vorgehensweise: Deklarieren von Handles in nativen Typen](../dotnet/how-to-declare-handles-in-native-types.md)<br/>
[auto_handle-Klasse](../dotnet/auto-handle-class.md)