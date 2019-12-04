---
title: Compilerwarnung C4577
description: Compilerwarnung C4577 Beschreibung und Projekt Mappe.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: e29e47b2a268d86f7f6a280b79a1604fe6eff8a4
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810556"
---
# <a name="compiler-warning-level-1-c4577"></a>Compilerwarnung (Stufe 1) C4577

> "noaußer" wird verwendet, ohne dass der Ausnahme Behandlungs Modus angegeben wurde. Beendigung bei Ausnahme ist nicht gewährleistet. /EHsc angeben

Der Compiler hat eine `noexcept` Spezifikation erkannt, aber C++ es wurde keine Standard Ausnahmebehandlung angegeben. Der Compiler unterstützt die Ausnahmebehandlung nicht vollständig C++ gemäß dem Standard, es sei denn, die [/EHsc](../../build/reference/eh-exception-handling-model.md) -Compileroption ist angegeben. Um dieses Problem zu beheben, legen Sie die **/EHsc** -Compileroption fest.

Diese Warnung ist neu in Visual Studio 2015 und ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md)deaktivierte Compilerwarnungen.
