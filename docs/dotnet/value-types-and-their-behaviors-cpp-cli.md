---
title: Werttypen und ihr Verhalten (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- value types
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d2d980e48a6f948c35faf0c4e42969795ef8dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404656"
---
# <a name="value-types-and-their-behaviors-ccli"></a>Werttypen und ihr Verhalten (C++/CLI)

Werttypen haben Visual c++ auf verschiedene Arten von Managed Extensions for C++ geändert. In diesem Abschnitt untersuchen wir die CLR-Enumerationstyp und den Typ des Wert-Klasse, zusammen mit einem Blick auf Boxing und den Zugriff auf die geschachtelte Instanz auf dem CLR-Heap als auch einen Blick auf innerer und fester Zeiger. Es wurden umfangreiche sprachänderungen in diesem Bereich.

## <a name="in-this-section"></a>In diesem Abschnitt

[CLR-Enumerationstyp](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
Werden Änderungen in der Deklaration und das Verhalten von Enumerationen erläutert.

[Implizites Boxing von Werttypen](../dotnet/implicit-boxing-of-value-types.md)<br/>
Erläutert die Motivation für implizites Boxing von Werttypen und die daraus entstehenden Änderungen im Verhalten.

[Ein Trackinghandle für einen geschachtelten Wert](../dotnet/a-tracking-handle-to-a-boxed-value.md)<br/>
Erläutert, wie implizites Boxing Werts Typen ein Trackinghandle für das Objekt der geschachtelte Wert ergibt.

[Werttypsemantik](../dotnet/value-type-semantics.md)<br/>
Werden Änderungen an Werttypsemantik, einschließlich geerbte virtuelle Methoden, die Standard-Klasse, Konstruktoren, die inneren Zeigern und Festhalten von Zeigern erläutert.

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)<br/>
[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)