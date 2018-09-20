---
title: Verwaltete Typen (C++-CL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 382228b9e8364d90d7929b4633744071c5eb0c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408030"
---
# <a name="managed-types-ccl"></a>Verwaltete Typen (C++/CL)

Die Syntax für die Deklaration von verwalteten Typen und die Erstellung und Verwendung von Objekten dieser Typen hat erheblich von Managed Extensions für C++ in Visual C++ geändert wurde. Dies erfolgte zur Förderung ihrer Integration in das ISO C++-Typsystem. Diese Änderungen werden ausführlicher in den folgenden Unterabschnitten angezeigt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)<br/>
Erläutert, wie eine verwaltete deklarieren `class`, `struct`, oder `interface`.

[Deklaration eines CLR-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md)<br/>
Deklarieren ein Typs Verweisklassenobjekts verwenden ein Trackinghandle erläutert.

[Deklaration eines CLR-Arrays](../dotnet/declaration-of-a-clr-array.md)<br/>
Erläutert das Deklarieren und Initialisieren eines Arrays.

[Änderungen in der Initialisierungsreihenfolge für Konstruktoren](../dotnet/changes-in-constructor-initialization-order.md)<br/>
Erläutert die wichtige Änderungen in der Initialisierungsreihenfolge für Konstruktoren Klasse.

[Änderungen in der Destruktorsemantik](../dotnet/changes-in-destructor-semantics.md)<br/>
Beschreibt die nicht deterministische Beendigung, `Finalize` im Vergleich zu `Dispose`, Auswirkungen für Verweisobjekte, und Verwenden einer expliziten `Finalize`.

**Hinweis:** die Erläuterung von Delegaten verzögert, bis [Delegaten und Ereignissen](../dotnet/delegates-and-events.md) um sie mit der Ereignis-Elemente innerhalb einer Klasse, die Themen zu präsentieren [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++ / CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)<br/>
[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Arrays](../windows/arrays-cpp-component-extensions.md)