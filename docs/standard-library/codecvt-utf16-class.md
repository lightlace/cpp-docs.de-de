---
title: codecvt_utf16 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3d999ffc40241169dab6847e882b1994beccc1b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtutf16"></a>codecvt_utf16
Stellt ein [Gebietsschemafacet](../standard-library/locale-class.md) dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE oder UTF-16BE codiert ist.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```
## <a name="parameters"></a>Parameter
`Elem`  
Der Breitzeichen-Elementtyp.  
`Maxcode`  
Die maximale Anzahl der Zeichen für das Gebietsschemafacet.  
`Mode`  
Konfigurationsinformationen für das Gebietsschemafacet.  

## <a name="remarks"></a>Hinweise
Diese Vorlagenklasse führt eine Konvertierung durch zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE (im Modus „& little_endian“) oder UTF-16BE codiert ist.

Der Bytestream muss in eine binäre Datei geschrieben werden. Er kann beschädigt werden, wenn er in eine Textdatei geschrieben wird.

## <a name="requirements"></a>Anforderungen
Header: \<codecvt> Namespace: std