---
title: "Manifestgenerierung &#252;ber die Befehlszeile"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Manifesttool (mt.exe)"
  - "Manifeste [C++]"
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Manifestgenerierung &#252;ber die Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Erstellen von C\/C\+\+\-Anwendungen über die Befehlszeile – mithilfe von nmake oder einem ähnlichen Tool – wird das Manifest generiert, nachdem der Linker alle Objektdateien verarbeitet und die endgültige Binärdatei erstellt hat.  Der Linker sammelt die in den Objektdateien gespeicherten Assemblyinformationen und kombiniert diese Informationen zu einer endgültigen Manifestdatei.  Standardmäßig generiert der Linker eine Datei, die binary\_name.extension.manifest \<, um\>die\>endgültige\<Binärdatei zu beschreiben genannt wird.  Der Linker ist nicht in der Lage, eine Manifestdatei in die Binärdatei einzubetten, sondern kann ein Manifest nur als externe Datei generieren.  Es gibt verschiedene Möglichkeiten, ein Manifest in die endgültige Binärdatei einzubetten, z. B. die Verwendung des [Manifesttools \(mt.exe\)](http://msdn.microsoft.com/library/aa375649) oder das Kompilieren des Manifests in eine Ressourcendatei.  Beachten Sie, dass beim Einbetten eines Manifests in die endgültige Binärdatei spezielle Regeln befolgt werden müssen, damit Features wie inkrementelles Verknüpfen, Signierung und Bearbeiten und Fortfahren funktionieren.  Diese und weitere Optionen beim Erstellen über die Befehlszeile werden in [Gewusst wie: Einbetten eines Manifests in eine C\/C\+\+\-Anwendung](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) beschrieben.  
  
## Siehe auch  
 [Manifeste](http://msdn.microsoft.com/library/aa375365)   
 [\/INCREMENTAL \(inkrementell verknüpfen\)](../build/reference/incremental-link-incrementally.md)   
 [Assemblys mit starken Namen \(Assemblysignierung\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 ["Bearbeiten und Fortfahren"](../Topic/Edit%20and%20Continue.md)   
 [Manifestgenerierung für C\/C\+\+\-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)