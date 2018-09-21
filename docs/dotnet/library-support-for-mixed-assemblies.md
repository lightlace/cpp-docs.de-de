---
title: Bibliotheksunterstützung für gemischte Assemblys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/18/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 868cae6701e17c79c9856b3a16c63c1e25b67bda
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494516"
---
# <a name="library-support-for-mixed-assemblies"></a>Bibliotheksunterstützung für verschiedene Assemblys

Visual C++ unterstützt die Verwendung von der C++-Standardbibliothek der C-Laufzeitbibliothek (CRT), ATL und MFC für Anwendungen, die mit kompiliert [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md). Dadurch können vorhandene Anwendungen, die diese Bibliotheken verwenden, um auch die .NET Framework-Funktionen zu verwenden.

> [!IMPORTANT]
> Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Diese Unterstützung umfasst die folgenden DLLs und Bibliotheken:

- Msvcmrt [d]-lib, bei der Kompilierung mit **"/ CLR"**. Gemischte Assemblys-Link zu dieser Bibliothek importieren.

Diese Unterstützung bietet mehrere Vorteile im Zusammenhang:

- Die CRT- und C++-Standardbibliothek sind für den gemischten Code verfügbar. Die CRT- und C++-Standardbibliothek, die bereitgestellt sind nicht überprüfbar. Letztendlich werden Ihre Aufrufe immer noch auf die gleiche CRT- und C++-Standardbibliothek weitergeleitet, wie die Verwendung von systemeigenem Code.

- Richtige einheitliche Behandlung von Ausnahmen in gemischte Bilder.

- Statischen Initialisierung der C++-Variablen in gemischten Bildern.

- Unterstützung für pro-AppDomain und prozessspezifische Variablen in verwaltetem Code.

- Löst den Problemen mit Loadersperren, die auf den gemischten DLLs kompiliert in Visual Studio 2003 und früheren Versionen angewendet.

Diese Unterstützung stellt darüber hinaus die folgenden Einschränkungen:

- Nur die CRT-DLL-Modell wird unterstützt, für die Kompilierung von Code mit **"/ CLR"**. Es gibt keine statischen CRT-Bibliotheken, die Unterstützung von **"/ CLR"** erstellt.


## <a name="see-also"></a>Siehe auch

- [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
