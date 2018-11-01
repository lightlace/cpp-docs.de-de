---
title: Inkrementieren und Dekrementieren von Zeigern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e220c138ebcbb9010aef78931b07c2b04b095ea7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447647"
---
# <a name="incrementing-and-decrementing-pointers"></a>Inkrementieren und Dekrementieren von Zeigern

Verwenden Sie die folgenden Tipps:

- Zeigen Sie auf die führende Bytes, die nicht auf nachfolgende Bytes. Es ist in der Regel nicht sicher ist, um einen Zeiger auf ein nachfolgendes Byte zu erhalten. Normalerweise ist es sicherer, eine Zeichenfolge vorwärts und nicht in umgekehrter Reihenfolge zu scannen.

- Es gibt Zeiger Inkrement/Dekrement-Funktionen und Makros, die über ein ganzes Zeichen zu verschieben:

    ```cpp
    sz1++;
    ```

   wird:

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   Die `_mbsinc` und `_mbsdec` Funktionen ordnungsgemäß Inkrement- und Dekrement-im `character` Einheiten, unabhängig von der Zeichengröße.

- Dekrementiert benötigen Sie einen Zeiger an den Anfang der Zeichenfolge an, wie im folgenden dargestellt:

    ```cpp
    sz2--;
    ```

   wird:

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   Alternativ dazu Ihre hauptzeiger ist möglicherweise auf ein gültiges Zeichen in der Zeichenfolge, sodass:

    ```cpp
    sz2Head < sz2
    ```

   Sie benötigen einen Zeiger auf eine gültige führenden Byte.

- Möglicherweise möchten Sie einen Zeiger auf das vorherige Zeichen für schnellere Aufrufe verwalten `_mbsdec`.

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Byte-Indizes](../text/byte-indices.md)