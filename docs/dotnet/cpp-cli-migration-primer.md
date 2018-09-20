---
title: C++ / CLI Migration Primer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88b32ea226971c0fa5b6d269a8992629c3c4de77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385430"
---
# <a name="ccli-migration-primer"></a>Einführung in die C++/CLI-Migration

Dies ist eine Anleitung zur Migration von Visual C++-Programmen von Managed Extensions für C++, Visual C++.

C++/CLI erweitert ein dynamisches Komponentenprogrammierparadigma auf die ISO-C++-Standardsprache. Die neue Sprache hat gegenüber Managed Extensions eine ganze Reihe bedeutender Verbesserungen zu bieten. Dieser Abschnitt enthält eine Auflistung der Managed Extensions for C++-Sprachfeatures und deren Zuordnung zu Visual C++, in dem eine solche Zuordnung vorhanden ist, und hebt diese Konstrukte für die keine Zuordnung vorhanden ist.

## <a name="in-this-section"></a>In diesem Abschnitt

[Gliederung der Änderungen (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)<br/>
Eine ausführliche Gliederung als Kurzreferenz mit einer Auflistung der Änderungen unter fünf allgemeinen Kategorien.

[Sprachschlüsselwörter (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)<br/>
Behandelt Änderungen im Zusammenhang mit Sprachschlüsselwörtern, darunter die Beseitigung doppelter Unterstriche und die Einführung sowohl von kontextbezogenen Schlüsselwörtern als auch von durch Leerzeichen getrennten Schlüsselwörtern.

[Verwaltete Typen (C++ / CL)](../dotnet/managed-types-cpp-cl.md)<br/>
Betrachtet syntaktische Änderungen in der Deklaration von der Common Type System (CTS) – dazu gehören Änderungen in der Deklaration von Klassen, Arrays (einschließlich des Parameterarrays), Enumerationen und So weiter.

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
Präsentiert die Änderungen bei Klassenmembern, z. B. Skalare Eigenschaften, Indexeigenschaften, Operatoren, Delegaten und Ereignisse.

[Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
Konzentriert sich auf Werttypen und die neue Familie innerer und fester Zeiger. Befasst sich außerdem mit einer Reihe signifikanter semantischer Änderungen, wie der Einführung von implizitem Boxing, der Unveränderlichkeit geschachtelter Werttypen und dem Wegfall der Unterstützung für Standardkonstruktoren innerhalb von Wertklassen.

[Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
Geht ausführlich auf semantische Änderungen ein, wie die Unterstützung von Umwandlungsnotation, das Verhalten von Zeichenfolgenliteralen und semantische Änderungen von C++/CLI gegenüber ISO-C++.

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)