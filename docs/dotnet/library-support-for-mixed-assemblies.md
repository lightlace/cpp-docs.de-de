---
title: Bibliotheksunterstützung für gemischte Assemblys | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: d4b584e0bacb1cb93cad33efdff807bb5fa9c8e2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704110"
---
# <a name="library-support-for-mixed-assemblies"></a>Bibliotheksunterstützung für verschiedene Assemblys

Visual C++ unterstützt die Verwendung von der C++-Standardbibliothek der C-Laufzeitbibliothek (CRT), ATL und MFC für Anwendungen mit kompiliert [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md). Dadurch können vorhandene Anwendungen, die diese Bibliotheken verwenden, um als auch .NET Framework-Funktionen zu verwenden.

> [!IMPORTANT]
> Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Diese Unterstützung umfasst die folgenden DLLs und Bibliotheken:

- Msvcmrt [d] .lib beim Kompilieren mit **"/ CLR"**. Gemischte Assemblys Link in die Bibliothek importieren.

Diese Unterstützung bietet mehrere Vorteile beziehen:

- Die CRT- und C++-Standardbibliothek sind für gemischten Code verfügbar. Die CRT- und C++-Standardbibliothek, die bereitgestellt sind nicht überprüfbar. Ihre Aufrufe werden letztlich weiterhin auf dem CRT- und C++-Standardbibliothek weitergeleitet, wie Sie von systemeigenem Code verwenden.

- Beheben Sie einheitliche Ausnahmebehandlung in gemischten Bildern.

- Statischen Initialisierung der C++-Variablen im gemischten Bilder.

- Unterstützung für pro-AppDomain- und pro-Prozess-Variablen in verwaltetem Code.

- Aufgelöst Loader Sperre Probleme, die in gemischten DLLs kompiliert in Visual Studio 2003 und früher angewendet wird.

Diese Unterstützung stellt darüber hinaus die folgenden Einschränkungen:

- Nur die CRT-DLL-Modell wird unterstützt, um kompilierten Code mit **"/ CLR"**. Es sind keine statischen CRT-Bibliotheken, die Unterstützung **"/ CLR"** erstellt.

Sie sollten die common Language Runtime (CLR) auf die aktuelle Version aktualisieren, da nicht gewährleistet ist, arbeiten mit früheren Versionen. Mit diesen Änderungen erstellte Code wird nicht ausgeführt, in CLR-Version 1.x.

## <a name="see-also"></a>Siehe auch

- [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
