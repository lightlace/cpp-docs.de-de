---
title: Compilerfehler C3610 | Microsoft-Dokumentation
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
ms.openlocfilehash: b46b3669978ff3735d5a16015ca0a01e65f07ae9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037852"
---
# <a name="compiler-error-c3610"></a>Compilerfehler C3610

"Valuetype": Werttyp muss geschachtelt werden, bevor die Methode 'Methode' aufgerufen werden kann

Standardmäßig ist ein Werttyp nicht auf dem verwalteten Heap. Bevor Sie Methoden aus .NET Common Language Runtime-Klassen, z. B. aufrufen können `Object`, müssen Sie den Werttyp auf den verwalteten Heap zu verschieben.

C3610 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
