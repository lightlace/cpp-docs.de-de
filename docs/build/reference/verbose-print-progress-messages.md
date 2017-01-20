---
title: "/VERBOSE (Statusmeldungen ausgeben)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/verbose"
  - "VC.Project.VCLinkerTool.ShowProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERBOSE (Linkeroption)"
  - "Abhängigkeiten [C++], Abhängigkeitsinformationen in Linkerausgabe"
  - "Linker [C++], Ausgabeabhängigkeitsinformationen"
  - "Verknüpfen [C++], Sitzungsverlaufsinformationen"
  - "Druckfortschrittsmeldungen (Linkeroption)"
  - "VERBOSE (Linkeroption)"
  - "-VERBOSE (Linkeroption)"
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /VERBOSE (Statusmeldungen ausgeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## Hinweise  
 Der Linker sendet Informationen über den Status des Verknüpfungsvorgangs an das **Ausgabe**fenster.  Auf Befehlszeilenebene werden die Informationen an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|\/VERBOSE|Zeigt Einzelheiten über den Verknüpfungsvorgang an.|  
|\/VERBOSE:ICF|Zeigt Informationen über die Linkeraktivität an, die sich aus der Verwendung von [\/OPT:ICF](../../build/reference/opt-optimizations.md) ergibt.|  
|\/VERBOSE:INCR|Zeigt Informationen über den inkrementellen Verknüpfungsvorgang an.|  
|\/VERBOSE:LIB|Zeigt Statusmeldungen an, die sich nur auf die durchsuchten Bibliotheken beziehen.<br /><br /> Die angezeigten Informationen schließen das Durchsuchen von Bibliotheken ein und führen jeden Bibliotheks\- und Objektnamen \(mit vollständigem Pfad\), das Symbol, das durch die Bibliothek aufgelöst wird, und eine Liste der Objekte auf, die auf das Symbol verweisen.|  
|\/VERBOSE:REF|Zeigt Informationen über die Linkeraktivität an, die sich aus der Verwendung von [\/OPT:REF](../../build/reference/opt-optimizations.md) ergibt.|  
|\/VERBOSE:SAFESEH|Zeigt Informationen zu Modulen an, die nicht mit der sicheren Ausnahmebehandlung kompatibel sind, wenn [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) nicht angegeben wird.|  
|\/VERBOSE:UNUSEDLIBS|Zeigt Informationen über alle Bibliotheksdateien an, die nicht verwendet werden, wenn das Image erstellt wird.|  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie den Ordner **Linker**.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Fügen Sie die Option dem Feld **Zusätzliche Optionen** hinzu.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)