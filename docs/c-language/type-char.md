---
title: Typ „char“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec964d9b81ee93f888bbd4152f06f6bdf51b6d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053829"
---
# <a name="type-char"></a>Typ "char"

Der `char`-Typ wird verwendet, um den ganzzahligen Wert eines Members des darstellbaren Zeichensatzes zu speichern. Dieser ganzzahlige Wert ist der ASCII-Code, der dem angegebenen Zeichen entspricht.

**Microsoft-spezifisch**

Zeichenwerte des Typs `unsigned char` haben einen Bereich von 0 bis zu den hexadezimalen Zahlen 0xFF. Ein **signed char** hat den Bereich 0x80 bis 0x7F. Diese Bereiche entsprechen 0 bis 255 dezimal bzw. -128 bis +127 dezimal. Die /J-Compileroption ändert den Standard von **signed** in `unsigned`.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)