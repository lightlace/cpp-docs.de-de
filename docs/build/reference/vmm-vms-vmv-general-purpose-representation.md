---
title: -Vmm - Vms, - Vmv (allgemeine Darstellung) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vms
- /vmm
- /vmv
dev_langs:
- C++
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d54ea3cabbbe631006cc22a80fdbf500585ff20f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv (Immer allgemeiner Zweck)
Wird verwendet, wenn [/vmb, / vmg (Darstellungsmethode)](../../build/reference/vmb-vmg-representation-method.md) ausgewählt ist, als die [Darstellungsmethode](../../build/reference/vmb-vmg-representation-method.md). Diese Optionen geben an, das Vererbungsmodell der Definition der Klasse noch nicht gefunden werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Optionen werden in der folgenden Tabelle beschrieben.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/ VMM**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse zu, die mehrfache Vererbung verwendet.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument zu [#pragma Pointers_to_members](../../preprocessor/pointers-to-members.md) ist **Multiple_inheritance**.<br /><br /> Diese Darstellung ist größer als die, die für einfache Vererbung erforderlich.<br /><br /> Wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, virtuell ist, generiert der Compiler einen Fehler aus.|  
|**/ VMs**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse zu, die keine Vererbung oder die einfache Vererbung verwendet.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument zu [#pragma Pointers_to_members](../../preprocessor/pointers-to-members.md) ist **Single_inheritance**.<br /><br /> Dies ist die kleinstmögliche Darstellung eines Zeigers auf einen Member einer Klasse.<br /><br /> Wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert ist, mehrfach vorhanden ist oder virtuell ist, generiert der Compiler einen Fehler.|  
|**/vmv**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse zu, die virtuellen Vererbung verwendet. Er nie verursacht einen Fehler, und ist die Standardeinstellung.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument zu [#pragma Pointers_to_members](../../preprocessor/pointers-to-members.md) ist **virtuelle Vererbung**.<br /><br /> Diese Option erfordert einen größeren Zeiger und zusätzlichen Code zum Interpretieren des Zeigers als die anderen Optionen.|  
  
 Wenn Sie eine der folgenden Vererbungsmodell Optionen angeben, wird das Modell für alle Zeiger auf Klassenmember, unabhängig von deren Vererbungstyp oder gibt an, ob der Zeiger deklariert ist vor oder nach der Klasse verwendet. Aus diesem Grund, wenn Sie immer mit einfacher Vererbung von Klassen verwenden, können Sie Codegröße verringern durch die Kompilierung mit **/VMs**, aber wenn Sie den allgemeinsten Fall (auf Kosten der größten datendarstellung) verwenden möchten, kompilieren Sie mit **/vmv**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ vmb, / vmg (Darstellungsmethode)](../../build/reference/vmb-vmg-representation-method.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)