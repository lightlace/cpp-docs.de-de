---
title: Absorptionsspektrum | Microsoft Docs
ms.custom: 
ms.date: 1/23/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs: C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b515d25d4818cf8b6213a37f3fe78df4f3882a69
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
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
