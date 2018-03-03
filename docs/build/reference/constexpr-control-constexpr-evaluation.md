---
title: -Constexpr (Steuerelement Constexpr evaluieren) | Microsoft Docs
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e594eb697c8972d28b513a3638d3eb704258b5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (Steuerelement Constexpr evaluieren)  
  
Verwenden der **/constexpr** Compileroptionen in Steuerelementparameter für `constexpr` Auswertung zum Zeitpunkt der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
> /constexpr:Depth*N*  
> /constexpr:Backtrace*N*  
> /constexpr:Steps*N*  
  
## <a name="arguments"></a>Argumente  
  
**Tiefe***N*  
Begrenzen der Tiefe von rekursiven `constexpr` Funktionsaufruf auf *N* Ebenen. Der Standardwert ist 512.  
  
**Backtrace***N*  
Anzeigen von bis zu *N* `constexpr` auswertungen in der Diagnose. Der Standard ist 10.  
  
**Schritte***N*  
Beenden `constexpr` Auswertung nach *N* Schritte. Der Standardwert ist 100.000.  
  
## <a name="remarks"></a>Hinweise  
  
Die **/constexpr** Compileroptionen steuern kompilierzeitauswertung von `constexpr` Ausdrücke. Auswertung Schritte, Rekursionsebenen und Backtrace Tiefe werden gesteuert, um zu verhindern, dass den Compiler die Ausgaben zu viel Zeit für `constexpr` Auswertung. Weitere Informationen zu den `constexpr` Language-Element finden Sie unter [Constexpr (C++)](../../cpp/constexpr-cpp.md).  

Die **/constexpr** Optionen sind ab Visual Studio 2015.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie das Projekt **Eigenschaftenseiten** (Dialogfeld).   
  
2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
3. Geben Sie ein beliebiges **/constexpr** Compileroptionen die **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
  
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)