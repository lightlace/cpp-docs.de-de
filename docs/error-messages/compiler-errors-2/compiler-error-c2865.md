---
title: Compilerfehler C2865 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc0a49f8e6ab42f7e607cd5f4f7cc91f6895abe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035162"
---
# <a name="compiler-error-c2865"></a>Compilerfehler C2865

'Funktion': Unzulässiger Vergleich für Handle_or_pointer

Sie können Verweise auf Vergleichen [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) oder verwaltet von Verweistypen, die nur auf Gleichheit zu überprüfen, ob sie auf das gleiche Objekt (==) oder auf andere Objekte verweisen (! =).

Sie können nicht verglichen werden für die Sortierung, da die .NET Runtime verwaltete Objekte zu jedem Zeitpunkt verschoben werden kann das Ergebnis des Tests ändern.