---
title: Schwerwiegender Fehler C1383 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98f6fe881b2cdc46d4d2848d6faf850381f54c7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062188"
---
# <a name="fatal-error-c1383"></a>Schwerwiegender Fehler C1383

Die Compileroption /GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.

C1383 tritt auf, wenn Sie eine frühere Version der Common Language Runtime mit einem neueren Compiler verwenden und bei der Kompilierung **/clr** und **/GL.** verwenden.

Verwenden Sie entweder nicht **/GL** mit **/clr** , oder installieren Sie die im Lieferumfang des Compilers enthaltene Version der Common Language Runtime.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).