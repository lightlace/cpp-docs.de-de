---
title: Compilerwarnung C4577
description: Compilerwarnung C4577 Beschreibung und Projekt Mappe.
ms.date: 09/18/2019
helpviewer_keywords:
- C4577
ms.openlocfilehash: 637023f4c27f93238fbbd13b4a0e652e6cd958e0
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71241126"
---
# <a name="compiler-warning-level-1-c4577"></a>Compilerwarnung (Stufe 1) C4577

> "noaußer" wird verwendet, ohne dass der Ausnahme Behandlungs Modus angegeben wurde. Beendigung bei Ausnahme ist nicht gewährleistet. /EHsc angeben

Der Compiler hat eine `noexcept` Spezifikation erkannt, aber C++ es wurde keine Standard Ausnahmebehandlung angegeben. Der Compiler unterstützt die Ausnahmebehandlung nicht vollständig C++ gemäß dem Standard, es sei denn, die [/EHsc](../../build/reference/eh-exception-handling-model.md) -Compileroption ist angegeben. Um dieses Problem zu beheben, legen Sie die **/EHsc** -Compileroption fest.

Diese Warnung ist neu in Visual Studio 2015 und ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md)deaktivierte Compilerwarnungen.
