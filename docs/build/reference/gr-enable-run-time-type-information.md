---
title: -GR (Laufzeit-Typeninformation aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e91f11fa6397d2ba8279998726249182c541d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374976"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Laufzeit-Typeninformation aktivieren)
Fügt Code aus, um Objekte des Typs zur Laufzeit zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GR[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn **/Gr** ist, definiert der Compiler die `_CPPRTTI` Präprozessormakro. Standardmäßig **/Gr** befindet sich auf. **/ Gr-verwendet** Laufzeit-Typeninformation deaktiviert.  
  
 Verwendung **/Gr** Wenn der Compiler einen Objekttyp in Ihrem Code nicht statisch auflösen kann. In der Regel müssen Sie die **/Gr** option, wenn der Code verwendet [Dynamic_cast Operator](../../cpp/dynamic-cast-operator.md) oder [Typeid](../../cpp/typeid-operator.md). Allerdings **/Gr** vergrößert sich die .rdata-Abschnitte des Bilds. Wenn Ihr Code keine verwendet **Dynamic_cast** oder **Typeid**, **/GR-verwendet** ein kleineres Image erzielt werden kann.  
  
 Weitere Informationen zum Laufzeittyp zu überprüfen, finden Sie unter [-Laufzeit-Typinformationen](../../cpp/run-time-type-information.md) in der *C++-Sprachreferenz*.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Sprache** Eigenschaftenseite.  
  
4.  Ändern der **Laufzeit-Typeninformation aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)