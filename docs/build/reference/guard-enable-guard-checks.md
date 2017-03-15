---
title: "/GUARD (Schutzpr&#252;fungen aktivieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /GUARD (Schutzpr&#252;fungen aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt Unterstützung für die Überprüfung des Ablaufsteuerungsschutzes im ausführbaren Image an.  
  
## Syntax  
  
```  
/GUARD:{CF|NO}  
```  
  
## Hinweise  
 Wenn \/GUARD:CF angegeben wird, ändert der Linker den Header einer DLL\- oder EXE\-Datei, um Unterstützung für CFG\-Laufzeitüberprüfungen \(Control Flow Guard, Ablaufsteuerungsschutz\) anzugeben.  Der Linker fügt dem Header auch die erforderlichen Ablaufsteuerungs\-Zieladressdaten hinzu.  Standardmäßig ist \/GUARD:CF deaktiviert.  Es kann explizit mithilfe von \/GUARD:NO deaktiviert werden.  Um effektiv zu sein, benötigt \/GUARD:CF auch die [\/DYNAMICBASE \(Address Space Layout Randomization verwenden\)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)\-Linkeroption, die standardmäßig aktiviert ist.  
  
 Wenn Quellcode mithilfe der [\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)\-Option kompiliert wird, analysiert der Compiler die Ablaufsteuerung durch Untersuchen aller indirekter Aufrufe der möglichen Zieladressen.  Der Compiler fügt Code ein, um zu überprüfen, ob sich die Zieladresse einer indirekten Aufrufanweisung zur Laufzeit in der Liste der bekannten Zieladressen befindet.  Betriebssysteme, die CFG unterstützen, beenden ein Programm, das bei einer CFG\-Laufzeitüberprüfung einen Fehler ausgibt.  Dies erschwert es einem Angreifer, schädlichen Code mithilfe von Datenbeschädigung auszuführen, um ein Aufrufziel zu ändern.  
  
 Die \/GUARD:CF\-Option muss dem Compiler und dem Linker angegeben werden, um CFG\-fähige ausführbare Images zu erstellen.  Code, der kompiliert, aber nicht mit \/GUARD:CF verknüpft wurde, verursacht Kosten für Überprüfungen zur Laufzeit, aktiviert aber nicht den CFG\-Schutz.  Wenn die \/GUARD:CF\-Option für den `cl`\-Befehl angegeben wird, um in einem Schritt zu kompilieren und zu verknüpfen, übergibt der Compiler das Flag an den Linker.  Wenn die **Ablaufsteuerungsschutz**\-Eigenschaft in Visual Studio festgelegt ist, wird die \/GUARD:CF\-Option dem Compiler und dem Linker übergeben.  Wenn Objektdateien oder Bibliotheken separat kompiliert wurden, muss die Option im `Link`\-Befehl explizit angegeben werden.  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie **Konfigurationseigenschaften**, **Linker**, **Befehlszeile**.  
  
3.  Geben Sie in **Zusätzliche Optionen** `/GUARD:CF` ein.  
  
## Siehe auch  
 [\/guard \(Ablaufsteuerungsschutz aktivieren\)](../../build/reference/guard-enable-control-flow-guard.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)