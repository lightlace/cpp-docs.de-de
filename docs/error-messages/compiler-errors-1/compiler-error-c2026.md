---
title: Compilerfehler C2026 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 055ac47d036a1027817aa6b3433bfe0e2e88570e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019548"
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