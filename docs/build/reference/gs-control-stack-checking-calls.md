---
title: – Gs (Stapel-Überprüfungsaufrufe kontrollieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /GS
dev_langs:
- C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0c6a5af31eaba30af92201a2e2563b67aceed6e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104107"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Stapel-Überprüfungsaufrufe kontrollieren)
Steuert Stapelüberprüfungen

## <a name="syntax"></a>Syntax

```  
/Gs[size]
```  

## <a name="arguments"></a>Argumente
*size*<br/>
(Optional) Die Anzahl von Bytes, die von lokalen Variablen belegt werden können, bevor eine Stapelüberprüfung initiiert wird. Wenn die **/GS** Option wird angegeben, ohne eine `size` -Argument, es ist derselbe, als wenn **/Gs0**,

## <a name="remarks"></a>Hinweise
Eine Stapelüberprüfung ist eine Codesequenz, die der Compiler in jeden Funktionsaufruf einfügt. Sobald die Stapelüberprüfung initiiert ist, belegt sie im Speicher so viel Platz, wie zum Speichern der lokalen Variablen der Funktion nötig ist.

Wenn durch eine Funktion mehr als `size` Bytes an Stapelspeicher für lokale Variablen anfordert, wird für diese Funktion die Stapelüberprüfung initiiert. Standardmäßig generiert der Compiler Code, der eine Stapelüberprüfung initiiert, wenn für eine Funktion mehr als eine Seite Stapelspeicher erforderlich ist. Dies ist gleichbedeutend mit der Compileroption **/Gs4096** für X86 X64 und ARM-Plattformen. Mit diesem Wert sind eine Anwendung und der Speichermanager von Windows in der Lage, den für den Programmstapel reservierten Arbeitsspeicher zur Laufzeit dynamisch zu erhöhen.

> [!NOTE]
>  Der Standardwert von **/Gs4096** ermöglicht, dass der Programmstapel von Anwendungen für Windows zur Laufzeit ordnungsgemäß vergrößert. Wir empfehlen, den Standardwert nur dann zu ändern, wenn Sie genau wissen, warum Sie ihn ändern müssen.

Für einige Programme, beispielsweise virtuelle Gerätetreiber, ist dieser Standardmechanismus zum Vergrößern des Stapels nicht erforderlich. In solchen Fällen sind die Stapelüberprüfungen nicht erforderlich, und Sie können verhindern, dass der Compiler diese generiert, indem Sie `size` auf einen Wert festlegen, der so groß ist, wie ihn keine Funktion zum Speichern ihrer lokalen Variablen benötigt. Darf kein Leerzeichen zwischen **/GS** und `size`.

**/ Gs0** aktiviert stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen erforderlich ist. Das kann sich negativ auf die Leistung auswirken.

Können Sie stapelüberprüfungen ein- oder ausschalten aktivieren, indem Sie mithilfe von [Check_stack](../../preprocessor/check-stack.md). **/ GS** und `check_stack` Pragma haben keine Auswirkungen auf standardmäßige C-Bibliotheksroutinen und betreffen nur die Funktionen, die Sie kompilieren.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

2.  Wählen Sie die **C/C++-** Ordner.

3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.

4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)