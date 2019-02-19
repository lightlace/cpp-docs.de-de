---
title: Typ "char"
ms.date: 11/04/2016
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
ms.openlocfilehash: bc8d3bef85b82d5bb5c2575b3bc6c6d8a4887140
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152208"
---
# <a name="type-char"></a>Typ "char"

Der `char`-Typ wird verwendet, um den ganzzahligen Wert eines Members des darstellbaren Zeichensatzes zu speichern. Dieser ganzzahlige Wert ist der ASCII-Code, der dem angegebenen Zeichen entspricht.

**Microsoft-spezifisch**

Zeichenwerte des Typs `unsigned char` haben einen Bereich von 0 bis zu den hexadezimalen Zahlen 0xFF. Ein **signed char** hat den Bereich 0x80 bis 0x7F. Diese Bereiche entsprechen 0 bis 255 dezimal bzw. -128 bis +127 dezimal. Die /J-Compileroption ändert den Standard von **signed** in `unsigned`.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)
