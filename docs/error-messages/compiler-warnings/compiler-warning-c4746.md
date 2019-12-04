---
title: Compilerwarnung C4746
ms.date: 11/04/2016
f1_keywords:
- C4746
helpviewer_keywords:
- C4746
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 9e761deb1b8c1b00e025f49775a845d07985fd2c
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810578"
---
# <a name="compiler-warning-c4746"></a>Compilerwarnung C4746

flüchtiger Zugriff auf "\<Expression >" unterliegt/volatile: [ISO&#124;MS] Setting; Verwenden Sie __iso_volatile_load intrinsischen/Store-Funktionen.

C4746 wird ausgegeben, wenn direkt auf eine flüchtige Variable zugegriffen wird. Er soll Entwicklern helfen, Code Speicherorte zu identifizieren, die von dem derzeit angegebenen aktuellen, flüchtigen Modell betroffen sind (das mit der [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption gesteuert werden kann). Insbesondere kann es hilfreich sein, von compilergenerierten Hardware Speicherbarrieren zu suchen, wenn/volatile: ms verwendet wird.

Die __iso_volatile_load/Store-systeminternen Funktionen können verwendet werden, um explizit auf flüchtigen Speicher zuzugreifen, ohne dass das flüchtige Modell davon betroffen ist. Die Verwendung dieser systeminternen Funktionen löst C4746 nicht aus.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .