---
title: Parameterarray und Ellipse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2caf6415fdbceb506b736e209c6e7e384b567c5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384376"
---
# <a name="param-array-and-ellipsis"></a>Parameterarray und Ellipse

Rangfolge von Parameterarrays zum Auflösen von Aufrufen überladener Funktionen wurde von Managed Extensions für C++ in Visual C++ geändert.

In Managed Extensions und die neue Syntax ist es keine explizite Unterstützung für das Parameterarray, die C#- und Visual Basic unterstützen. Stattdessen kennzeichnet eine ein normales Array mit einem Attribut, wie folgt:

```
void Trace1( String* format, [ParamArray]Object* args[] );
void Trace2( String* format, Object* args[] );
```

Während beide identisch aussehen, die `ParamArray` Attribut kennzeichnet dieses für C#- oder andere CLR-Sprachen als ein Array, eine Variable Anzahl von Elementen mit jedem Aufruf aufnehmen. Die Änderung im Verhalten von Programmen mit Managed Extensions und der neuen Syntax bei der Auflösung einer überladenen Funktion legen Sie in der eine Instanz eine Ellipse deklariert wird und eine zweite deklariert eine `ParamArray` -Attribut, wie im folgenden Beispiel von bereitgestellt Artur Laksberg.

```
int fx(...); // 1
int fx( [ParamArray] Int32[] ); // 2
```

In Managed Extensions wurde mit der Auslassungspunkten Vorrang vor mit dem Attribut angegeben, die sinnvoll ist, da das Attribut nicht über eine formale Aspekt der Sprache ist. Allerdings in der neuen Syntax wird das Parameterarray wird jetzt direkt in die Sprache unterstützt, und erhält Vorrang vor auf die Auslassungspunkte, da diese Sprache stärker typisiert ist. Daher in Managed Extensions des Aufrufs

```
fx( 1, 2 );
```

Löst in `fx(...)` in die neue Syntax, löst es in der `ParamArray` Instanz. Bei einem aus, die das Verhalten des Programms auf den Aufruf der Instanz mit den Auslassungspunkten, bevorzugen abhängt die `ParamArray`, Sie müssen entweder die Signatur oder der Aufruf zu ändern.

## <a name="see-also"></a>Siehe auch

[Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)