---
title: Allgemeine Sprachänderungen (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b48ebdf0bf25399b08f8a1cb1240a857cfad352
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418457"
---
# <a name="general-language-changes-ccli"></a>Allgemeine Sprachänderungen (C++/CLI)

Eine Anzahl von CLR-Sprachfunktionen, die von Managed Extensions for C++ auf Visual C++ geändert.

Die Änderungen, die in diesem Abschnitt beschriebenen sind eine Art von Sprache – Vermischtes. Es beinhaltet eine Änderung bei der Behandlung von Zeichenfolgenliteralen, die eine Änderung der Auflösung von funktionsüberladungen zwischen einem Auslassungszeichen und `Param` Attribut, die Änderung des `typeof` zu `typeid`, eine Änderung in der Aufruf von Initialisierungslisten, und die Einführung in eine neue Umwandlungsnotation, mit der `safe_cast`.

[Zeichenfolgenliteral](../dotnet/string-literal.md)<br/>
Erläutert, wie die Behandlung von Zeichenfolgenliteralen geändert hat.

[Parameterarray und Ellipse](../dotnet/param-array-and-ellipsis.md)<br/>
Erläutert, wie `ParamArray` erhält Vorrang vor jetzt auf die Auslassungspunkte (`...`) zum Auflösen von Funktionsaufrufen, die mit einer unterschiedlichen Anzahl von Argumenten.

[typeof wird zu T::typeid](../dotnet/typeof-goes-to-t-typeid.md)<br/>
Erläutert, wie die `typeof` -Operator wurde ersetzt wurde, indem `typeid`.

[Initialisiererlisten](../dotnet/initializer-lists.md)<br/>
Werden Änderungen in die Aufrufreihenfolge von Initialisiererlisten erläutert.

[Umwandlungsnotation und Einführung in safe_cast<>](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<br/>
Erläutert Änderungen Umwandlungsnotation und insbesondere bei die Einführung von `safe_cast`.

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)