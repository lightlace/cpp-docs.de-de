---
title: Compilerwarnung (Stufe 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: a6949586cf3faa00aafed37a72e58c1b80266cf5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401383"
---
# <a name="compiler-warning-level-4-c4092"></a>Compilerwarnung (Stufe 4) C4092

Sizeof gibt "unsigned long" zurück.

Der Operand der `sizeof` Operator war sehr groß, sodass `sizeof` Vorzeichen zurückgegeben **lange**. Diese Warnung tritt auf, die Microsoft-Erweiterungen ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). ANSI-Kompatibilität (/ Za) wird stattdessen das Ergebnis abgeschnitten.