---
title: Prozess | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b36ec42447aa076d0623707951f82b7b9c95d563
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704905"
---
# <a name="process"></a>process

Gibt an, dass der verwaltete Anwendungsprozess eine einzelne Kopie einer bestimmten globalen Variablen, einer statischen Membervariablen oder einer statischen lokalen Variablen haben soll, die von allen Anwendungsdomänen im Prozess verwendet wird. Dies wurde hauptsächlich verwendet werden, bei der Kompilierung mit **/CLR: pure**, d. h. in Visual Studio 2017 als veraltet markiert und in Visual Studio 2017 nicht unterstützt. Beim Kompilieren mit **"/ CLR"**, globale und statische Variablen werden standardmäßig pro-Prozess und müssen nicht mit `__declspec(process)`.

Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable des systemeigenen Typs können durch `__declspec(process)` markiert werden.

`process` gilt nur beim Kompilieren mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).

Wenn Sie jede Anwendungsdomäne eine eigene Kopie einer globalen Variablen haben soll, verwenden Sie [Appdomain](../cpp/appdomain.md).

Finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

- [__declspec](../cpp/declspec.md)
- [Schlüsselwörter](../cpp/keywords-cpp.md)
