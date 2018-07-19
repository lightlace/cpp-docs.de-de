---
title: codecvt_utf8_utf16 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::cvt_utf8_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 545fda08a027b1610f82d17c89ae98241ee5502b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958129"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Stellt ein [Gebietsschemafacet](../standard-library/locale-class.md) dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UTF-16 codiert sind, und einem Bytestream, der als UTF-8 codiert ist.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parameter

*Elem* der Breitzeichen-Elementtyp.
*Maxcode* die maximale Anzahl von Zeichen für das gebietsschemafacet.
*Modus* Konfigurationsinformationen für das gebietsschemafacet.

## <a name="remarks"></a>Hinweise

Der Bytestream kann in eine Binärdatei oder eine Textdatei geschrieben werden.

## <a name="requirements"></a>Anforderungen

Header: <codecvt> Namespace: std
