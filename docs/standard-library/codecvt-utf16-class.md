---
title: codecvt_utf16 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdfcf3c6a562f7aab0164e3d63d468ba39ec0023
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954098"
---
# <a name="codecvtutf16"></a>codecvt_utf16

Stellt ein [Gebietsschemafacet](../standard-library/locale-class.md) dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE oder UTF-16BE codiert ist.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parameter

*Elem* der Breitzeichen-Elementtyp.
*Maxcode* die maximale Anzahl von Zeichen für das gebietsschemafacet.
*Modus* Konfigurationsinformationen für das gebietsschemafacet.

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse führt eine Konvertierung durch zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE (im Modus „& little_endian“) oder UTF-16BE codiert ist.

Der Bytestream muss in eine binäre Datei geschrieben werden. Er kann beschädigt werden, wenn er in eine Textdatei geschrieben wird.

## <a name="requirements"></a>Anforderungen

Header: \<codecvt> Namespace: std