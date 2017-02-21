---
title: "/vmm, /vms, /vmv (Immer allgemeiner Zweck) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vms"
  - "/vmm"
  - "/vmv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmm (Compileroption) [C++]"
  - "/vms (Compileroption) [C++]"
  - "/vmv (Compileroption) [C++]"
  - "Immer allgemeiner Zweck (Compileroptionen)"
  - "Einzelne Vererbung (Compileroption)"
  - "Virtuelle Vererbung (Compileroption)"
  - "vmm (Compileroption) [C++]"
  - "-vmm (Compileroption) [C++]"
  - "vms (Compileroption) [C++]"
  - "-vms (Compileroption) [C++]"
  - "vmv (Compileroption) [C++]"
  - "-vmv (Compileroption) [C++]"
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /vmm, /vms, /vmv (Immer allgemeiner Zweck)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird verwendet, wenn [\/vmb, \/vmg \(Darstellungsmethode\)](../../build/reference/vmb-vmg-representation-method.md) als [Darstellungsmethode](../../build/reference/vmb-vmg-representation-method.md) ausgewählt ist.  Diese Optionen legen das Vererbungsmodell der bis jetzt noch nicht verarbeiteten Klassendefinition fest.  
  
## Syntax  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## Hinweise  
 Die Optionen werden in der folgenden Tabelle beschrieben.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**\/vmm**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse an, das mehrfache Vererbung verwendet.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument für [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) ist **multiple\_inheritance**.<br /><br /> Diese Darstellung ist größer als die, die für einfache Vererbung erforderlich ist.<br /><br /> Hat eine Klassendefinition, für die ein Zeiger auf einen Member definiert ist, ein virtuelles Vererbungsmodell, generiert der Compiler einen Fehler.|  
|**\/vms**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse an, das einen Member mit einfacher bzw. ohne Vererbung verwendet.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument für [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) ist **single\_inheritance**.<br /><br /> Dieses ist die kleinstmögliche Darstellung eines Zeigers auf einen Member einer Klasse.<br /><br /> Hat eine Klassendefinition, für die ein Zeiger auf einen Member definiert ist, ein mehrfaches oder virtuelles Vererbungsmodell, generiert der Compiler einen Fehler.|  
|**\/vmv**|Gibt die allgemeinste Darstellung eines Zeigers auf einen Member einer Klasse an, das einen Member mit virtueller Vererbung verwendet.  Die Option generiert keinen Fehler. Sie ist die Standardeinstellung.<br /><br /> Das entsprechende [Vererbungsschlüsselwort](../../cpp/inheritance-keywords.md) und das Argument für [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) ist **virtual\_inheritance**.<br /><br /> Im Vergleich zu den anderen Optionen erfordert diese Option einen größeren Zeiger und zusätzlichen Code zu dessen Interpretation.|  
  
 Wenn Sie eine dieser Optionen für Vererbungsmodelle angeben, wird das entsprechende Modell für alle Zeiger auf Klassenmember verwendet, unabhängig von deren Vererbungstyp oder davon, ob der Zeiger vor oder nach der Klasse deklariert wird.  Daher können Sie bei ausschließlicher Verwendung von einfach geerbten Klassen die Codegröße durch das Kompilieren mit **\/vms** reduzieren. Wenn Sie jedoch mit der Standardeinstellung vorgehen möchten \(die allerdings die größte Datendarstellung bedeutet\), kompilieren Sie mit  **\/vmv**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/vmb, \/vmg \(Darstellungsmethode\)](../../build/reference/vmb-vmg-representation-method.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)