---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: a84ca6da22825ca3fa7ab43e43a574fb05caa1a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689826"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

Stellt ein [Gebietsschemafacet](../standard-library/locale-class.md) dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE oder UTF-16BE codiert ist.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parameter

*Elem* -\
Der Breitzeichen-Elementtyp.

*Maxcode* -\
Die maximale Anzahl der Zeichen für das Gebietsschemafacet.

*Modus* \
Konfigurationsinformationen für das Gebietsschemafacet.

## <a name="remarks"></a>Hinweise

Diese Klassen Vorlage konvertiert zwischen breit Zeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Byte Datenstrom, der als UTF-16LE codiert ist, wenn Mode & LITTLE_ENDIAN, oder UTF-16BE andernfalls.

Der Bytestream muss in eine binäre Datei geschrieben werden. Er kann beschädigt werden, wenn er in eine Textdatei geschrieben wird.

## <a name="requirements"></a>Anforderungen

Header: \<codecvt >

Namespace: Std