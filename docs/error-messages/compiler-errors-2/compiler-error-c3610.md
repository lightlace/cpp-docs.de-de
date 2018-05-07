---
title: Compilerfehler C3610 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f58d66e9d3dacfa2c0b38eb84fe51e0813a892d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3610"></a>Compilerfehler C3610
"Valuetype": Werttyp muss geschachtelt werden, bevor die Methode 'Methode' aufgerufen werden kann  
  
 Standardmäßig ist ein Werttyp nicht auf dem verwalteten Heap. Bevor Sie Methoden aus .NET Common Language Runtime-Klassen, z. B. aufrufen können `Object`, müssen Sie den Werttyp auf den verwalteten Heap zu verschieben.  
  
 C3610 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
