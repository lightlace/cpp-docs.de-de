---
title: 'Hstring:: Makereference-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebc8632d273e650cf11e70177bbfbeb0e90e8601
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394854"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference-Methode

Erstellt eine `HStringReference` Objekt aus einem angegebenen Zeichenfolgenparameter.

## <a name="syntax"></a>Syntax

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Parameter

*sizeDest*<br/>
Ein Vorlagenparameter, der angibt, die Größe des Ziels `HStringReference` Puffer.

*str*<br/>
Ein Verweis auf eine Zeichenfolge mit Breitzeichen.

*Len*<br/>
Die maximale Länge von der *str* Parameterpuffer auf diesen Vorgang verwendet. Wenn die *Len* Parameter nicht angegeben ist, die gesamte *str* Parameter wird verwendet.

## <a name="return-value"></a>Rückgabewert

Ein `HStringReference` -Objekt, dessen Wert identisch mit dem angegebenen ist *str* Parameter.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)