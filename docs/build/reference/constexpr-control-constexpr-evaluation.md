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
ms.openlocfilehash: 475702792686a3de8d1ae52bd9e40ef113c49da1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202573"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/ constexpr (Constexpr-Auswertung steuern)  
  
Verwenden der **/constexpr** Compileroptionen Steuerparameter für **"constexpr"** Auswertung zum Zeitpunkt der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
> **Depth**<em>N</em>  
> **/ constexpr: Backtrace**<em>N</em>  
> **/ constexpr: Steps**<em>N</em>  
  
## <a name="arguments"></a>Argumente  
  
**Tiefe**<em>N</em>  
Schränken Sie die Tiefe von rekursiven **"constexpr"** Funktionsaufruf auf *N* Ebenen. Der Standardwert ist 512.  
  
**Backtrace**<em>N</em>  
Anzeigen von bis zu *N* **"constexpr"** auswertungen bei der Diagnose. Der Standard ist 10.  
  
**Schritte**<em>N</em>  
Beenden Sie **"constexpr"** Auswertung nach *N* Schritte. Der Standardwert ist 100.000.  
  
## <a name="remarks"></a>Hinweise  
  
Die **/constexpr** Compileroptionen steuern kompilierzeitauswertung von **"constexpr"** Ausdrücke. Evaluierungsschritte, Rekursionsebenen und Backtrace Tiefe werden gesteuert, um zu verhindern, dass den Compiler Ausgaben zu viel Zeit für **"constexpr"** Auswertung. Weitere Informationen zu den **"constexpr"** Language-Element, finden Sie unter ["constexpr" (C++)](../../cpp/constexpr-cpp.md).  

Die **/constexpr** Optionen sind verfügbar ab der in Visual Studio 2015.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.   
  
2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
3. Geben Sie ein beliebiges **/constexpr** Compileroptionen der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
  
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)