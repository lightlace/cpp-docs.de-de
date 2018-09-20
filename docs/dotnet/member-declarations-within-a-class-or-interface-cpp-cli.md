---
title: Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- members, declaration syntax
- class members, declaration syntax
ms.assetid: 95d312a4-198b-46f0-b8f5-15253807c55e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 80b872b4c614677c05b0d28b821d3a48255905c5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430632"
---
# <a name="member-declarations-within-a-class-or-interface-ccli"></a>Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)

Die Deklaration von Eigenschaften und Operatoren wurde von Managed Extensions für C++ für Visual C++, Ausblenden von Details der zugrunde liegenden Implementierung, die in der Managed Extensions-Entwurf verfügbar gemacht wurden umfassend überarbeitet. Ereignisdeklarationen wurden ebenfalls geändert.

In der Kategorie der ändert sich wurde, dass haben keine Unterstützung für Managed Extensions, statische Konstruktoren kann nun definierten Out-of-Line (sie wurden erforderlich, um Inline in Managed Extensions definiert werden), und das Konzept von einem delegierenden Konstruktor eingeführt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Eigenschaftendeklaration](../dotnet/property-declaration.md)<br/>
Werden Änderungen an Eigenschaftendeklarationen erläutert.

[Deklaration von Eigenschaftenindizes](../dotnet/property-index-declaration.md)<br/>
Werden Änderungen an indizierten Eigenschaftendeklarationen erläutert.

[Delegaten und Ereignisse](../dotnet/delegates-and-events.md)<br/>
Werden Änderungen an die Syntax zum Deklarieren von Delegaten und Ereignissen erläutert.

[Versiegeln einer virtuellen Funktion](../dotnet/sealing-a-virtual-function.md)<br/>
Werden Änderungen an die Syntax für das Versiegeln einer Funktion erläutert.

[Überladene Operatoren](../dotnet/overloaded-operators.md)<br/>
Werden Änderungen an Überladen von Operatoren erläutert.

[Änderungen bei Konvertierungsoperatoren](../dotnet/changes-to-conversion-operators.md)<br/>
Werden Änderungen bei Konvertierungsoperatoren erläutert.

[Explizites Überschreiben eines Schnittstellenmembers](../dotnet/explicit-override-of-an-interface-member.md)<br/>
Werden Änderungen an die Methode zum expliziten Überschreiben eines Schnittstellenmembers erläutert.

[Private virtuelle Funktionen](../dotnet/private-virtual-functions.md)<br/>
Erläutert die Änderungen auf die Weise, die private virtuelle Funktionen in abgeleiteten Klassen verarbeitet werden.

[Die Bindung von static const int-Membern ist nicht mehr literal](../dotnet/static-const-int-linkage-is-no-longer-literal.md)<br/>
Erläutert die Änderungen bei der Datenerfassung `static const` ganzzahlige Membern verknüpft sind und wie Sie explizit deklarieren, eine Konstante, die mit dem neuen `literal` Schlüsselwort.

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)