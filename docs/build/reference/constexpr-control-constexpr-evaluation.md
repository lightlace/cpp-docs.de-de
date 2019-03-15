---
title: / constexpr (Constexpr-Auswertung steuern)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 178acc548fb9c89dcfde104d2a12d85637440e28
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810184"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/ constexpr (Constexpr-Auswertung steuern)

Verwenden der **/constexpr** Compileroptionen Steuerparameter für **"constexpr"** Auswertung zum Zeitpunkt der Kompilierung.

## <a name="syntax"></a>Syntax

> **/constexpr:depth**<em>N</em>
>  **/constexpr:backtrace**<em>N</em>
>  **/constexpr:steps**<em>N</em>

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

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
