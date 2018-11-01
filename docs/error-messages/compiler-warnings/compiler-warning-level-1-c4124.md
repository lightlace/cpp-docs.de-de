---
title: Compilerwarnung (Stufe 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 04732619571420e777244b81bf4b93b775477a20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582567"
---
# <a name="compiler-warning-level-1-c4124"></a>Compilerwarnung (Stufe 1) C4124

__fastcall mit stapelüberprüfung ist ineffizient

Die `__fastcall` Schlüsselwort wurde verwendet, mit stapelüberprüfung aktiviert.

Die `__fastcall` Konvention generiert schnelleren Code, aber die stapelüberprüfung verursacht langsamere Code. Bei Verwendung `__fastcall`, deaktivieren Sie die stapelüberprüfung mit der **Check_stack** Pragma oder/GS.

Diese Warnung wird nur für die erste Funktion deklariert, die unter diesen Bedingungen ausgegeben.