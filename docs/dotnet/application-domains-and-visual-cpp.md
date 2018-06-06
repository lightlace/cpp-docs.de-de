---
title: Anwendungsdomänen und Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b935b9a5d1561fa1c8b961ee48b92f59b98e2bd2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704333"
---
# <a name="application-domains-and-visual-c"></a>Anwendungsdomänen und Visual C++

Wenn Sie haben eine `__clrcall` virtuelle Funktion, werden die Vtable pro Anwendungsdomäne (Appdomain). Wenn Sie ein Objekt in einer Appdomain erstellen, können Sie nur die virtuelle Funktion von innerhalb dieser Appdomain aufrufen. Im gemischten Modus (**"/ CLR"**) Sie haben prozessspezifisch-v-Tabellen auf, wenn Ihr Typ keine enthält `__clrcall` virtuelle Funktionen. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Weitere Informationen finden Sie unter:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>Siehe auch

- [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)