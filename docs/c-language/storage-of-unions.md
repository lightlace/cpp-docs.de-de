---
title: Speicherung von Unions
ms.date: 11/04/2016
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
ms.openlocfilehash: 49b99dc17fd7bdddd8a47e3bfd5913a70a7631a7
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152819"
---
# <a name="storage-of-unions"></a>Speicherung von Unions

Der Speicher, der einer Union-Variable zugeordnet wird, ist der Speicher, der für den größten Member der Union erforderlich ist. Wenn ein kleinerer Member gespeichert wird, kann die Union-Variable nicht verwendeten Speicherbereich enthalten. Alle Member werden im gleichen Speicherbereich gespeichert und beginnen an derselben Adresse. Der gespeicherte Wert wird jedes Mal überschrieben, wenn einem anderen Member ein Wert zugewiesen wird. Beispiel:

```
union         /* Defines a union named x */
{
    char *a, b;
    float f[20];
} x;
```

Die Elemente der `x`-Union fungieren in der Reihenfolge ihrer Deklaration als Zeiger auf einen `char`-Wert, einen `char`-Wert und ein Array von **float**-Werten. Der `x` zugeordnete Speicher ist der Speicher, der für das `f`-Array mit 20 Elementen erforderlich ist, da `f` der längste Union-Member ist. Da kein Tag der Union zugeordnet ist, ist ihr Typ unbenannt oder „anonym“.

## <a name="see-also"></a>Siehe auch

[Union-Deklarationen](../c-language/union-declarations.md)
