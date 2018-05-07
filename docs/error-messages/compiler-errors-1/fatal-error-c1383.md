---
title: Schwerwiegender Fehler C1383 | Microsoft Docs
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
ms.openlocfilehash: ae5e16959597e16f25320778be4d4b45ca5950e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1383"></a>Schwerwiegender Fehler C1383
Die Compileroption /GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.  
  
 C1383 tritt auf, wenn Sie eine frühere Version der Common Language Runtime mit einem neueren Compiler verwenden und bei der Kompilierung **/clr** und **/GL.** verwenden.  
  
 Verwenden Sie entweder nicht **/GL** mit **/clr** , oder installieren Sie die im Lieferumfang des Compilers enthaltene Version der Common Language Runtime.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).