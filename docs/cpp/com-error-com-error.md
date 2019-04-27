---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 8856289605cce430fdab36d6e3e8b743190e02ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155123"
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

*hr*<br/>
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

*that*<br/>
Eine vorhandene **_com_error** Objekt.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein neues Objekt angegeben wird, ein HRESULT und optionalen `IErrorInfo` Objekt. Der zweite Konstruktor erstellt eine Kopie eines vorhandenen **_com_error** Objekt.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)