---
title: Compilerfehler C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: da4c03c681f95efaa5edb159869315b41d027e99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303527"
---
# <a name="compiler-error-c2026"></a>Compilerfehler C2026

die Zeichenfolge ist zu lang, Zeichen am Ende wurden

Die Zeichenfolge war länger als das Limit von 16380 Einzelbyte-Zeichen.

Vor der angrenzende Zeichenfolgen verkettet werden darf keine Zeichenfolge länger als 16380 Einzelbyte-Zeichen sein.

Eine Unicode-Zeichenfolge von etwa halb so lang würde auch diesen Fehler generieren.

Wenn Sie eine Zeichenfolge, die wie folgt definiert haben, werden C2026 generiert:

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Sie können es wie folgt aufteilen:

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Möglicherweise möchten Sie zum Speichern von sehr umfangreiche Zeichenfolgenliterale (32 KB oder mehr) aus einer benutzerdefinierten Ressource oder eine externe Datei. Finden Sie unter [Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource](../../windows/creating-a-new-custom-or-data-resource.md) für Weitere Informationen.