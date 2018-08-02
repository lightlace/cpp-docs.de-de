---
title: Spectre | Microsoft-Dokumentation
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
ms.openlocfilehash: a51d47764ea4515fcbc2cb3b7aa37fd341cd130e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463228"
---
# <a name="spectre"></a>spectre

**Microsoft-spezifisch**

Weist den Compiler nicht auf die Spectre-Variante 1 spekulative Ausführung Barrier-Anweisungen für eine Funktion einzufügen.

## <a name="syntax"></a>Syntax

> **__declspec( spectre(nomitigation) )**  

## <a name="remarks"></a>Hinweise

Die ["/ qspectre"](../build/reference/qspectre.md) Compileroption veranlasst den Compiler, spekulative Ausführung Barriere Anweisungen einfügen, wo Analysis gibt an, ein Sicherheitsrisiko für Spectre-Variante 1 vorhanden ist. Folgen Sie den Anweisungen ausgegeben, richten sich nach den Prozessor. Diese Anweisungen einen minimalen Auswirkung auf die Codegröße oder die Leistung haben soll, auch gibt es Fälle, in denen Ihr Code wird durch die Sicherheitslücke nicht beeinflusst, und ist die maximale Leistung erforderlich.

Expertenanalyse möglicherweise bestimmen Sie, dass eine Funktion einen Fehler in Spectre Variant 1 Grenzen Check Bypass vor. In diesem Fall können Sie die Generierung von Code der Lösung innerhalb einer Funktion unterdrücken, indem Sie anwenden `__declspec(spectre(nomitigation))` auf die Funktionsdeklaration.

> [!CAUTION]
> Die **"/ qspectre"** spekulative Ausführung Barriere Anweisungen bieten wichtige Sicherheit und haben eine geringfügige Auswirkung auf die Leistung. Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.

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
