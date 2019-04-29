---
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: 42c9c8643edc795748c1f12c5180471f281c4142
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405260"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Stellt ein [Gebietsschemafacet](../standard-library/locale-class.md) dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UTF-16 codiert sind, und einem Bytestream, der als UTF-8 codiert ist.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parameter

*Elem*<br/>
Der Breitzeichen-Elementtyp.

*Maxcode*<br/>
Die maximale Anzahl der Zeichen für das Gebietsschemafacet.

*Modus*<br/>
Konfigurationsinformationen für das Gebietsschemafacet.

## <a name="remarks"></a>Hinweise

Der Bytestream kann in eine Binärdatei oder eine Textdatei geschrieben werden.

## <a name="requirements"></a>Anforderungen

Header: \<codecvt>

Namespace: std
