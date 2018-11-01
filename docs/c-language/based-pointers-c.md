---
title: Based-Zeiger (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79e515a3f108d0857d2f8860566e14ee0acdefe3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097574"
---
# <a name="based-pointers-c"></a>Basierte Zeiger (C)

**Microsoft-spezifisch**

[__based (C++-Verweis)](../cpp/based-pointers-cpp.md)

Für die 32-Bit- und 64-Bit-C-Compiler von Microsoft ist ein basierter Zeiger ein 32-Bit- oder 64-Bit-Offset einer 32-Bit- oder 64-Bit-Zeigerbasis. Die basierende Adressierung eignet sich zur Ausübung der Kontrolle über Abschnitte, denen Objekte zugeordnet sind; dadurch werden die Größe der ausführbaren Datei verringert und die Ausführungsgeschwindigkeit erhöht. Im Allgemeinen ist die Form zum Angeben eines basierten Zeigers

> *Typ* **__based(** *base* **)** *Deklarator*

Die "basierend auf Zeiger"-Variante der basierenden Adressierung ermöglicht die Angabe eines Zeigers als Basis. Der basierte Zeiger ist dann ein Offset im Arbeitsspeicherbereich, der am Anfang des Zeigers beginnt, auf dem er basiert. Zeiger, die auf Zeigeradressen basieren, sind die einzige Form des `__based`-Schlüsselworts, das in 32-Bit- und 64-Bit-Kompilierungen gültig ist. In solchen Kompilierungen sind sie 32-Bit- oder 64-Bit-Verschiebungen von einer 32-Bit- oder 64-Bit-Basis.

Eine Verwendung von Zeigern, die auf Zeigern basieren, ist für dauerhafte Bezeichner, die Zeiger enthalten. Eine verknüpfte Liste, die aus Zeigern auf Grundlage eines Zeigers besteht, kann auf Datenträger gespeichert werden, dann an eine andere Stelle im Arbeitsspeicher neu geladen werden, wobei die Zeiger weiterhin gültig bleiben.

Das folgende Beispiel zeigt einen Zeiger, der auf einem Zeiger basiert.

```C
void *vpBuffer;

struct llist_t
{
    void __based( vpBuffer ) *vpData;
    struct llist_t __based( vpBuffer ) *llNext;
};
```

Dem Zeiger `vpBuffer` wird die Adresse des später im Programm zugewiesenen Arbeitsspeichers zugeteilt. Die verknüpfte Liste wird relativ zum Wert von `vpBuffer` verschoben.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)