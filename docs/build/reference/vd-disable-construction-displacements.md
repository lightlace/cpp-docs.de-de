---
title: -vd (Konstruktionsverschiebungen deaktivieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vd
dev_langs:
- C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b945c4a3191554d5299522ff376772d6362a616c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vd-disable-construction-displacements"></a>/vd (Konstruktionsverschiebungen deaktivieren)
## <a name="syntax"></a>Syntax  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>Argumente  
 `0`  
 Unterdrückt die Vtordisp Konstruktor-/Destruktorverschiebung. Wählen Sie diese Option nur, wenn Sie sicher sind, dass alle Klassenkonstruktoren und -Destruktoren virtuelle Aufruf Funktionen virtuell.  
  
 `1`  
 Ermöglicht die Erstellung des ausgeblendeten Vtordisp Konstruktor-/Destruktorverschiebung. Diese Option ist die Standardeinstellung.  
  
 `2`  
 Ermöglicht Ihnen die Verwendung [Dynamic_cast Operator](../../cpp/dynamic-cast-operator.md) für ein Objekt erstellt wird. Beispiel: eine Dynamic_cast von einer virtuellen Basisklasse in eine abgeleitete Klasse.  
  
 **/ vd2** Fügt ein Vtordisp-Feld hinzu, wenn Sie eine virtuelle Basisklasse mit virtuellen Funktionen haben. **/ vd1** sollten ausreichen. Im häufigsten Fall, in dem **/vd2** ist erforderlich, ist die einzige virtuelle Funktion in der virtuellen Basisklasse ein Destruktor.  
  
## <a name="remarks"></a>Hinweise  
 Diese Optionen gelten nur für C++-Code, der virtuelle Basen verwendet.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]implementiert die Unterstützung von C++ zur Erstellung Verschiebung in Situationen, in denen virtueller Vererbung verwendet wird. Konstruktionsverschiebungen lösen des Problems erstellt, wenn eine virtuelle Funktion, die in eine virtuelle Basisklasse deklariert und in einer abgeleiteten Klasse überschrieben, während der Erstellung einer weiteren abgeleiteten Klasse von einem Konstruktor aufgerufen.  
  
 Das Problem besteht darin, dass die virtuelle Funktion eine falsche weitergeleitet werden möglicherweise `this` daher Zeiger von Diskrepanzen zwischen der Verschiebungen mit der virtuellen Basen, einer Klasse und die Verschiebungen abgeleiteten Klassen. Die Lösung bietet eine einzelne Konstruktion Verschiebung Anpassung, die ein Vtordisp-Feld für jede virtuelle Basis einer Klasse aufgerufen.  
  
 Standardmäßig werden Vtordisp-Felder eingeführt, wenn der Code eine benutzerdefinierte Konstruktoren und Destruktoren definiert und auch virtuelle Funktionen des virtuellen Basen überschreibt.  
  
 Diese Optionen beeinflussen ganze Quelldateien. Verwendung [Vtordisp](../../preprocessor/vtordisp.md) unterdrücken und dann wieder Vtordisp-Felder auf Basis einer Klasse von Klasse zu aktivieren.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)