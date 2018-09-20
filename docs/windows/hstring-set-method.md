---
title: 'Hstring:: Set-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 391af2939d4fc46f386299241f009ab2249200da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372213"
---
# <a name="hstringset-method"></a>HString::Set-Methode

Legt den Wert des aktuellen **HString** Objekt, das die angegebene Zeichenfolge mit Breitzeichen oder **HString** Parameter.

## <a name="syntax"></a>Syntax

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Eine Zeichenfolge mit Breitzeichen.

*Len*<br/>
Die maximale Länge von der *str* Parameter, der mit dem aktuellen zugewiesen ist **HString** Objekt.

*HSTR*<br/>
Eine vorhandene **HString** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)