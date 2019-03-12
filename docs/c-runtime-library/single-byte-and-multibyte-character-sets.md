---
title: Einzelbyte- und Mehrbyte-Zeichensätze
ms.date: 11/04/2016
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: 1e2d3f26891257101b4a9511f4e0b10f03113309
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745329"
---
# <a name="single-byte-and-multibyte-character-sets"></a>Einzelbyte- und Mehrbyte-Zeichensätze

Mit dem ASCII-Zeichensatz werden Zeichen im Bereich von 0x00 bis 0x7F definiert. Von einigen anderen Zeichensätzen (hauptsächlich europäischer Herkunft) werden wie beim ASCII-Zeichensatz die Zeichen im Bereich von 0x00 bis 0x7F definiert; zusätzlich wird ein erweiterter Zeichensatz im Bereich von 0x80 bis 0xFF definiert. Daher ist ein Einzelbyte-Zeichensatz (Single-Byte Character Set, SBCS) mit 8 Bits ausreichend, um den ASCII-Zeichensatz sowie viele andere Zeichensätze für europäische Sprachen darzustellen. Einige außereuropäische Zeichensätze, z.B. das japanische Kanji, enthalten jedoch so viele Zeichen, dass sie nicht mehr in Einzelbytecodierung dargestellt werden können. Sie müssen daher mit einem Multibyte-Zeichensatz (Multibyte Character Set, MBCS) codiert werden.

> [!NOTE]
> Viele SBCS-Routinen in der Microsoft-Laufzeitbibliothek behandeln Multibyte-Bytes, Zeichen und Zeichenfolgen entsprechend. Viele Multibyte-Zeichensätze definieren den ASCII-Zeichensatz als Teilmenge. In vielen Multibyte-Zeichensätzen sind die Zeichen im Bereich von 0x00 bis 0x7F mit den gleichwertigen Zeichen des ASCII-Zeichensatzes identisch. Das ein Byte lange Zeichen NULL („\0“) hat z.B. in ASCII- und MBCS-Zeichenfolgen den Wert 0x00 und steht für das abschließende NULL-Zeichen.

Ein Multibyte-Zeichensatz kann aus 1-Byte- und 2-Byte-Zeichen bestehen. Daher kann eine Multibyte-Zeichenfolge eine Mischung aus Einzelbyte- und Doppelbytezeichen enthalten. Ein 2-Byte-Multibytezeichen verfügt über ein führendes Byte und ein nachfolgendes Byte. In einem bestimmten Mehrbyte-Zeichensatz liegen die führenden Bytes ebenso wie die nachfolgenden Bytes innerhalb eines bestimmten Bereichs. Wenn sich diese Bereiche überschneiden, muss unter Umständen anhand des Kontexts ermittelt werden, ob ein bestimmtes Byte als führendes oder als nachfolgendes Byte verwendet wird.

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
