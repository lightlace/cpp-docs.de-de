---
title: "/DLL (DLL erstellen)"
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
  - "/dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DLL-Linkeroption [C++]"
  - "-DLL (Linkeroption)"
  - "DLL-Linkeroption [C++]"
  - "DLLs [C++], Erstellen"
  - "Exportieren von DLLs [C++], Angeben von Exporten"
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /DLL (DLL erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DLL  
```  
  
## Hinweise  
 Die Option **\/DLL** erstellt eine DLL als Hauptausgabedatei.  Eine DLL enthält in der Regel Exporte, die von einem anderen Programm verwendet werden können.  Um Exporte anzugeben, stehen Ihnen die folgenden drei Methoden zur Verfügung. Es wird empfohlen, sie in der angegebenen Reihenfolge zu verwenden:  
  
1.  [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) im Quellcode  
  
2.  Eine [EXPORTS](../../build/reference/exports.md)\-Anweisung in einer DEF\-Datei  
  
3.  Eine [\/EXPORT](../../build/reference/export-exports-a-function.md)\-Spezifikation in einem **LINK**\-Befehl  
  
 Ein Programm kann mehrere Methoden verwenden.  
  
 Eine weitere Möglichkeit, eine DLL zu erstellen, bietet die **LIBRARY**\-Anweisung für die Moduldefinition.  Die Optionen **\/BASE** und **\/DLL** sind zusammen das Äquivalent der **LIBRARY**\-Anweisung.  
  
 Verwenden Sie diese Option nicht in der Entwicklungsumgebung; sie darf nur in der Befehlszeile verwendet werden.  Die Option wird beim Erstellen eines DLL\-Projekts mit einem Anwendungs\-Assistenten eingestellt.  
  
 Wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, muss vor der Erstellung der DLL derselbe Satz von Objektdateien zur Erstellung der DLL übergeben werden wie bei der Erstellung der Importbibliothek.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Konfigurationseigenschaften**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Konfigurationstyp**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)