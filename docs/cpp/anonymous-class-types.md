---
title: Anonyme Klassentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f194bcae9710b68a0be6a0c4d25a9f47f3340064
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090172"
---
# <a name="anonymous-class-types"></a>Anonyme Klassentypen

Klassen können anonym sein – sie können also deklariert werden, ohne eine *Bezeichner*. Dies ist nützlich, wenn Sie einen Klassennamen durch Ersetzen einer **Typedef** anzugeben, wie im folgenden gezeigt:

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
>  Die Verwendung von anonymen Klassen, die im vorherigen Beispiel gezeigt wird, ist für das Beibehalten der Kompatibilität mit existierendem C-Code nützlich. In manchem C-Code die Verwendung von **Typedef** zusammen mit anonymen Strukturen ist weit verbreitet.

Anonyme Klassen sind außerdem nützlich, wenn Sie möchten, dass ein Verweis auf einen Klassenmember so angezeigt wird, als befände er sich nicht in einer separaten Klasse, wie im Folgenden gezeigt:

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

Im vorangehenden Code `iValue` kann zugegriffen werden, mit der Objekt-Memberauswahloperator (**.**) wie folgt:

```cpp
int i = ptv.iValue;
```

Anonyme Klassen unterliegen bestimmten Einschränkungen. (Weitere Informationen über anonyme Unions finden Sie unter [Unions](../cpp/unions.md).) Anonyme Klassen:

- Können keinen Konstruktor oder Destruktor aufweisen.

- Können nicht als Argumente an Funktionen übergeben werden (es sei denn, die Typüberprüfung wird mithilfe von Ellipsen außer Kraft gesetzt).

- Können nicht als Rückgabewerte von Funktionen zurückgegeben werden.

## <a name="anonymous-structs"></a>Anonyme Strukturen

### <a name="microsoft-specific"></a>Microsoft-spezifisch

Eine Microsoft C-Erweiterung ermöglicht es Ihnen, eine Strukturvariable innerhalb einer anderen Struktur zu deklarieren, ohne ihr einen Namen zu geben. Diese geschachtelten Strukturen werden als anonyme Strukturen bezeichnet. In C++ sind anonyme Strukturen nicht zulässig.

Sie können auf Member einer anonymen Struktur zugreifen, als ob sie Member der enthaltenden Struktur wären.

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**Ende Microsoft-spezifisch**