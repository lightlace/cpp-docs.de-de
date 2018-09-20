---
title: Änderungen bei Konvertierungsoperatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03b17c5abc559289a9f85a10b9c5914b49498922
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381106"
---
# <a name="changes-to-conversion-operators"></a>Änderungen bei Konvertierungsoperatoren

Die Syntax für Konvertierungsoperatoren hat Visual c++ von Managed Extensions for C++ geändert.

Ein Beispiel ist die schreiben `op_Implicit` eine Konvertierung angeben. Hier ist eine Definition der `MyDouble` der Sprachspezifikation entnommen:

```
__gc struct MyDouble {
   static MyDouble* op_Implicit( int i );
   static int op_Explicit( MyDouble* val );
   static String* op_Explicit( MyDouble* val );
};
```

Dies bedeutet, das der Algorithmus zum Konvertieren von ganzen Zahl in eine ganze Zahl mit einem `MyDouble` erfolgt über die `op_Implicit` Operator. Darüber hinaus wird diese Konvertierung implizit vom Compiler ausgeführt werden. Auf ähnliche Weise erhält ein `MyDouble` -Objekt, das die beiden `op_Explicit` Operatoren geben die entsprechenden Algorithmen zum Konvertieren von diesem Objekts in eine ganze Zahl oder einen verwalteten `String` Entität. Der Compiler führt jedoch nicht die Konvertierung, sofern nicht explizit vom Benutzer angefordert werden.

In c# sieht dies wie folgt aus:

```
class MyDouble {
   public static implicit operator MyDouble( int i );
   public static explicit operator int( MyDouble val );
   public static explicit operator string( MyDouble val );
};
```

Der C#-Code sieht C++ mehr aus, als Managed Extensions for C++. Das ist nicht der Fall, in der neuen Syntax.

Die ISO-C++ Kommission führte das Schlüsselwort `explicit`, um unerwartete Ergebnisse liefern – z. B. zu verringern. eine `Array` Klasse, die ein einzelnes ganzzahliges Argument akzeptiert, wie eine Dimension implizit eine beliebige ganze Zahl in konvertiert eine `Array` -Objekt, das ist nicht erwünscht. Eine Möglichkeit, dies zu verhindern besteht einen Entwurfsausdruck, der ein dummy zweites Argument eines Konstruktors

Andererseits, sollten Sie ein Konvertierungspaar nicht bereitstellen, beim Entwerfen eines Klassentyps in C++. Das beste Beispiel dafür ist die standard-String-Klasse. Die implizite Konvertierung ist die Einzelargumentkonstruktor übernimmt eine Zeichenfolge im C-Stil. Allerdings ermöglicht sie keinen entsprechenden Operator für implizite Konvertierung -, der Konvertierung einer Zeichenfolge, die Sie Objekt in eine Zeichenfolge im C-Stil, aber stattdessen muss der Benutzer eine benannte Funktion – in diesem Fall explizit aufrufen, um `c_str()`.

Daher ist anscheinend Zuordnung implizite/explizite Verhalten auf ein Konvertierungsoperator (und wie die Kapselung von Konvertierungen in eine einzige Deklaration) eine Verbesserung gegenüber der ursprünglichen C++-Unterstützung von Konvertierungsoperatoren, die schließlich zu den geführthat`explicit` Schlüsselwort. Die Visual C++-sprachunterstützung für Konvertierungsoperatoren sieht aufgrund des standardmäßigen Verhaltens des Operators, der eine implizite Anwendung des Konvertierungsalgorithmus etwas weniger ausführlich als c# wird wie folgt aus:

```
ref struct MyDouble {
public:
   static operator MyDouble^ ( int i );
   static explicit operator int ( MyDouble^ val );
   static explicit operator String^ ( MyDouble^ val );
};
```

Eine weitere Änderung ist, einen Einzelargumentkonstruktor behandelt wird, als ob er als deklariert wird `explicit`. Dies bedeutet, dass um seine Aufrufe auszulösen, eine explizite Umwandlung erforderlich ist. Beachten Sie jedoch, dass wenn Sie ein expliziten Konvertierungsoperator definiert ist, er und nicht die Einzelargumentkonstruktor, aufgerufen wird.

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)