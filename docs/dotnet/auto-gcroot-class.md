---
title: Auto_gcroot-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48412a932ff3752b0613f7045cd88992332b7917
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423226"
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