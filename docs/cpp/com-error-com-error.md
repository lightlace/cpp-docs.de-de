---
title: _com_error::_com_error | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89377e33e56b0796fc850c050c8e79eac86ee07d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040465"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error

**Microsoft-spezifisch**

Erstellt eine **_com_error** Objekt.

## <a name="syntax"></a>Syntax

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Parameter

*HR*<br/>
HRESULT-Informationen.

*perrinfo*<br/>
`IErrorInfo`-Objekt

*fAddRef*<br/>
Der Standardwert veranlasst den Konstruktor, AddRef auf einer nicht-Null Aufrufen `IErrorInfo` Schnittstelle. Dadurch wird eine richtige verweiszählung im typischen Fall, in dem Besitz der Schnittstelle übergeben wird, die **_com_error** Objekt, z. B.:

```cpp
throw _com_error(hr, perrinfo);
```

Wenn Sie nicht möchten, dass Ihr Code zum Übertragen des Besitzes zu der **_com_error** -Objekt, und die `AddRef` ist erforderlich, um den offset der `Release` in die **_com_error** Destruktor, erstellen Sie das Objekt als Die folgende:

```cpp
_com_error err(hr, perrinfo, true);
```

*,*<br/>
Eine vorhandene **_com_error** Objekt.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein neues Objekt angegeben wird, ein HRESULT und optionalen `IErrorInfo` Objekt. Der zweite Konstruktor erstellt eine Kopie eines vorhandenen **_com_error** Objekt.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)