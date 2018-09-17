---
title: Konfigurieren von Visual C++ für ARM-Prozessoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3d95f221-656a-480d-9651-9ad263895747
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce0e7e1f7c0936daed0fa6a51f6e254403205e0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714960"
---
# <a name="configure-visual-c-for-arm-processors"></a>Konfigurieren von Visual C++ für ARM-Prozessoren

Dieser Abschnitt der Dokumentation enthält Informationen darüber, wie die Visual C++-Buildtools zum Abstimmen auf ARM-Hardware verwendet werden.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über ARM-ABI-Konventionen](../build/overview-of-arm-abi-conventions.md) wird beschrieben, die Application binary Interface, das von Windows auf ARM für die registernutzung, die Aufrufkonventionen und Ausnahmebehandlung verwendet.

[Übersicht über die ABI-Konventionen für ARM64](../build/arm64-windows-abi-conventions.md) wird beschrieben, die Application binary Interface, das von Windows auf ARM64 für die registernutzung, die Aufrufkonventionen und Ausnahmebehandlung verwendet.

[Allgemeine Visual C++ ARM-Migrationsprobleme](../build/common-visual-cpp-arm-migration-issues.md) beschreibt C++-Codeelemente, die im Allgemeinen wird angenommen, dass über Architekturen portabel sein, aber das für ARM als für X86 und X64 zu unterschiedlichen Ergebnissen führen.

[ARM-Ausnahmebehandlung](../build/arm-exception-handling.md) beschreibt das Codierungsschema für die Stackentladung während der strukturierten Ausnahmebehandlung in Windows auf ARM.

[ARM64-Ausnahmebehandlung](../build/arm64-exception-handling.md) beschreibt das Codierungsschema für die Stackentladung während der strukturierten Ausnahmebehandlung in Windows auf ARM64.

## <a name="related-sections"></a>Verwandte Abschnitte

[Systeminterne ARM-Funktionen](../intrinsics/arm-intrinsics.md) beschreibt intrinsische Compilerfunktionen für Prozessoren, die die ARM-Architektur verwenden.
