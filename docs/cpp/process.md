---
title: process
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: 049360dddff2b9ca2ea460b96e027e86899f1ecb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591736"
---
# <a name="process"></a>process

Gibt an, dass der verwaltete Anwendungsprozess eine einzelne Kopie einer bestimmten globalen Variablen, einer statischen Membervariablen oder einer statischen lokalen Variablen haben soll, die von allen Anwendungsdomänen im Prozess verwendet wird. Dies wurde in erster Linie für die Verwendung vorgesehen werden beim Kompilieren mit **/CLR: pure**, das in Visual Studio 2017 als veraltet markiert und in Visual Studio 2017 nicht unterstützt. Beim Kompilieren mit **"/ CLR"**, globale und statische Variablen werden pro Prozess standardmäßig und müssen nicht mit **__declspec(process)**.

Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable des systemeigenen Typs kann mit markiert werden **__declspec(process)**.

**Prozess** ist nur gültig, beim Kompilieren mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).

Wenn Sie jede Anwendungsdomäne eine eigene Kopie einer globalen Variablen haben möchten, verwenden Sie [Appdomain](../cpp/appdomain.md).

Finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
