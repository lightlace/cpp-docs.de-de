---
title: Absorptionsspektrum | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 153ff690b975ecb442c260fcebce73acd32d03fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422409"
---
# <a name="spectre"></a>Absorptionsspektrum

**Microsoft-spezifisch**

Weist den Compiler nicht, um Absorptionsspektrum Variant 1 spekulative Barriere Anweisungen zur Ausführung für eine Funktion einzufügen.

## <a name="syntax"></a>Syntax

> **__declspec( spectre(nomitigation) )**  

## <a name="remarks"></a>Hinweise

Die [/Qspectre](../build/reference/qspectre.md) (Compileroption) veranlasst den Compiler, spekulative Ausführung Barriere Anweisungen einzufügen, wo Analysis zeigt an, dass ein Sicherheitsrisiko für Absorptionsspektrum Variante 1. Die spezifischen Anweisungen ausgegeben, richten sich nach den Prozessor. Während dieser Anweisungen eine minimale Auswirkung auf die Codegröße oder die Leistung haben, es gibt möglicherweise Fälle, in dem Code wird nicht durch die Sicherheitslücke beeinflusst und maximale Leistung erfordert, vor.

Experten-Analyse kann bestimmen, dass eine Funktion einen Absorptionsspektrum Variant 1 Grenzen Überprüfung umgehen defekt ist. In diesem Fall können Sie das Minderung codegenerierung innerhalb einer Funktion unterdrücken, indem anwenden `__declspec(spectre(nomitigation))` für die Funktionsdeklaration.

> [!CAUTION]
> Die **/Qspectre** spekulative Ausführung Barriere Anweisungen bieten wichtige Sicherheit und haben eine geringfügige Auswirkung auf die Leistung. Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.

## <a name="example"></a>Beispiel

Im folgenden Code wird die Verwendung von `__declspec(spectre(nomitigation))` veranschaulicht.

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)  
[Schlüsselwörter](../cpp/keywords-cpp.md)  
[/Qspectre](../build/reference/qspectre.md)  
