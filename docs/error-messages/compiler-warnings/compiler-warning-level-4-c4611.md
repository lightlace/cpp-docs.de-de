---
title: Compilerwarnung (Stufe 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: b799c568d73a081a4d4cf5616f376f3efc9eeffb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542310"
---
# <a name="compiler-warning-level-4-c4611"></a>Compilerwarnung (Stufe 1) C4600

Interaktion zwischen "Function" und C++-objektlöschung ist nicht portabel

Auf manchen Plattformen ist die Funktionen, die umfassen **catch** unterstützen möglicherweise keine C++-Objektsemantik der Zerstörung, wenn außerhalb des gültigen Bereichs.

Verwenden Sie zum Vermeiden von unerwartetem Verhalten **catch** in Funktionen, die Konstruktoren und Destruktoren besitzen.

Diese Warnung wird nur einmal ausgegeben; finden Sie unter [Pragma-Warnung](../../preprocessor/warning.md).