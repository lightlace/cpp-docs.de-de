---
title: -vd (Konstruktionsverschiebungen deaktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e983da4521db077235c2b879e0d1277b9505e94
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605867"
---
# <a name="vd-disable-construction-displacements"></a>/vd (Konstruktionsverschiebungen deaktivieren)
## <a name="syntax"></a>Syntax  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>Argumente  
 `0`  
 Unterdrückt die Vtordisp Konstruktor-/Destruktorverschiebung. Wählen Sie diese Option nur, wenn Sie sicher sind, rufen Sie alle-Klasse, Konstruktoren und Destruktoren virtuelle Funktionen virtuell.  
  
 `1`  
 Ermöglicht die Erstellung des ausgeblendeten Vtordisp Konstruktor-/Destruktorverschiebung. Diese Option ist die Standardeinstellung.  
  
 `2`  
 Können Sie mit [Dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md) für ein Objekt erstellt wird. Beispiel: ein Dynamic_cast von einer virtuellen Basisklasse für eine abgeleitete Klasse.  
  
 **"/ vd2"** Fügt ein Vtordisp-Feld hinzu, wenn Sie eine virtuelle Basisklasse mit virtuellen Funktionen verfügen. **/ vd1** sollten ausreichend sein. Die am häufigsten verwendeten Fall, in dem **"/ vd2"** ist erforderlich, ist die einzige virtuelle Funktion in der virtuellen Basisklasse einen Destruktor.  
  
## <a name="remarks"></a>Hinweise  
 Diese Optionen gelten nur für C++-Code, der virtuelle Basen verwendet.  
  
 Visual C++ implementiert den C++-Erstellung Verschiebung-Unterstützung in Situationen, in dem virtuelle Vererbung verwendet wird. Konstruktionsverschiebungen das Problem erstellt, wenn eine virtuelle Funktion, in eine virtuelle Basisklasse deklariert und in einer abgeleiteten Klasse überschrieben, während der Erstellung einer weiteren abgeleiteten Klasse von einem Konstruktor aufgerufen.  
  
 Das Problem besteht darin, dass die virtuelle Funktion eines falschen übergeben werden möglicherweise `this` daher Zeiger von Diskrepanzen zwischen der Verschiebungen mit der virtuellen Basisklassen, einer Klasse und die Verschiebungen abgeleiteten Klassen. Die Lösung bietet eine einzelne Konstruktion Verschiebung Anpassung, die ein Vtordisp-Feld, für jede virtuelle Basis einer Klasse aufgerufen.  
  
 Vtordisp-Felder werden standardmäßig eingeführt, wenn der Code eine benutzerdefinierte Konstruktoren und Destruktoren definiert und überschreibt auch die virtuelle Funktionen von virtuellen Basen.  
  
 Diese Optionen wirken sich auf ganze Quelldateien. Verwendung [Vtordisp](../../preprocessor/vtordisp.md) unterdrücken und dann wieder Vtordisp-Felder auf Basis einer Klasse-von-Klasse zu aktivieren.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)