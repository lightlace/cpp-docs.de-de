---
title: "LINK-Optionen, die &#252;ber den Compiler gesteuert werden | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler [C++], Steuern des Linkers"
  - "cl.exe-Compiler [C++], Features mit Auswirkungen auf die Verknüpfung"
  - "LINK-Tool [C++], Compilergesteuerte Optionen"
  - "Linker [C++], CL-Compilersteuerelement"
  - "Verknüpfen [C++], Auswirkungen von CL-Features"
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LINK-Optionen, die &#252;ber den Compiler gesteuert werden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der CL\-Compiler ruft automatisch LINK auf, es sei denn, Sie geben die Option **\/c** ein.  CL bietet durch Optionen und Argumente auf Befehlszeilenebene ein gewisses Maß an Steuerung für den Linker.  Die nachfolgende Tabelle fasst die Features in CL zusammen, die eine Auswirkung auf das Verknüpfen haben.  
  
|CL\-Spezifikation|CL\-Aktion, die sich auf "LINK" auswirkt|  
|-----------------------|----------------------------------------------|  
|Jede Dateierweiterung außer **.c**, **.cxx**, **.cpp** oder **.def**|Übergibt einen Dateinamen als Eingabe an **LINK**|  
|Dateiname**.def**|Übergibt **\/DEF**:*Dateiname.def*|  
|\/F`number`|Übergibt **\/STACK**:*Nummer*|  
|\/Fd*Dateiname*|Übergibt **\/PDB**:*Dateiname*|  
|\/Fe*Dateiname*|Übergibt **\/OUT**:*Dateiname*|  
|\/Fm*Dateiname*|Übergibt **\/MAP**:*Dateiname*|  
|\/Gy|Erstellt Paketfunktionen \(COMDATs\); aktiviert das Verknüpfen auf Funktionsebene|  
|\/LD|Übergibt **\/DLL**|  
|\/LDd|Übergibt **\/DLL**|  
|\/link|Übergibt den Rest der Befehlszeile an **LINK**|  
|\/MD oder \/MT|Speichert einen Standardbibliotheksnamen in der OBJ\-Datei|  
|\/MDd oder \/MTd|Speichert einen Standardbibliotheksnamen in der OBJ\-Datei.  Definiert das Symbol \_DEBUG|  
|\/nologo|Übergibt **\/NOLOGO**|  
|\/Zd|Übergibt **\/DEBUG**|  
|\/Zi oder \/Z7|Übergibt **\/DEBUG**|  
|\/Zl|Übergeht den Standardbibliotheksnamen in der OBJ\-Datei|  
  
 Weitere Informationen finden Sie unter [Compileroptionen](../../build/reference/compiler-options.md).  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)