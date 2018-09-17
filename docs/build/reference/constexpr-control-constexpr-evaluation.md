---
title: -Constexpr (Constexpr-Auswertung steuern) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /constexpr
- -constexpr
dev_langs:
- C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 462690a2b237d08adb9b16a68d38ad5258e958e2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703741"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/ constexpr (Constexpr-Auswertung steuern)

Verwenden der **/constexpr** Compileroptionen Steuerparameter für **"constexpr"** Auswertung zum Zeitpunkt der Kompilierung.

## <a name="syntax"></a>Syntax

> **Depth**<em>N</em>
>  **/constexpr: Backtrace**<em>N</em>
>  ** /constexpr: Steps** <em>N</em>

## <a name="arguments"></a>Argumente

**Tiefe**<em>N</em> schränken Sie die Tiefe von rekursiven **"constexpr"** Funktionsaufruf auf *N* Ebenen. Der Standardwert ist 512.

**Backtrace**<em>N</em> anzeigen bis zu *N* **"constexpr"** auswertungen bei der Diagnose. Der Standard ist 10.

**Schritte**<em>N</em> Terminate **"constexpr"** Auswertung nach *N* Schritte. Der Standardwert ist 100.000.

## <a name="remarks"></a>Hinweise

Die **/constexpr** Compileroptionen steuern kompilierzeitauswertung von **"constexpr"** Ausdrücke. Evaluierungsschritte, Rekursionsebenen und Backtrace Tiefe werden gesteuert, um zu verhindern, dass den Compiler Ausgaben zu viel Zeit für **"constexpr"** Auswertung. Weitere Informationen zu den **"constexpr"** Language-Element, finden Sie unter ["constexpr" (C++)](../../cpp/constexpr-cpp.md).

Die **/constexpr** Optionen sind verfügbar ab der in Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.

2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Befehlszeile** Eigenschaftenseite.

3. Geben Sie ein beliebiges **/constexpr** Compileroptionen der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)