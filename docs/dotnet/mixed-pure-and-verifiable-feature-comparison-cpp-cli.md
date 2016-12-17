---
title: "Featurevergleich zwischen &quot;gemischt&quot;, &quot;rein&quot; und &quot;&#252;berpr&#252;fbar&quot; (C++/CLI)"
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
  - "Gemischte Assemblys [C++]"
  - "Gemischte Assemblys [C++], Im Vergleich zu reinen"
  - "Gemischte Assemblys [C++], Im Vergleich zu sicheren"
  - "Reine Assemblys [C++]"
  - "Reine MSIL [C++]"
  - "Reine MSIL [C++], Verglichen mit gemischter und sicherer"
  - "Reine MSIL [C++], Im Vergleich zu gemischten"
  - "Reine MSIL [C++], Im Vergleich zu sicheren"
  - "Sichere Assemblys [C++]"
  - "Sichere Assemblys [C++], Im Vergleich zu gemischten"
  - "Sichere Assemblys [C++], Im Vergleich zu reinen"
  - "Überprüfbare Assemblys [C++]"
  - "Überprüfbare Assemblys [C++], Im Vergleich zu gemischten"
  - "Überprüfbare Assemblys [C++], Im Vergleich zu reinen"
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Featurevergleich zwischen &quot;gemischt&quot;, &quot;rein&quot; und &quot;&#252;berpr&#252;fbar&quot; (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unter diesem Thema werden Features anhand der unterschiedlichen **\/clr**\-Kompilierungsmodi verglichen.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Featurevergleich  
  
|Feature|Gemischt \(\/clr\)|Rein \(\/clr:pure\)|Sicher \(\/clr:safe\)|Verwandte Informationen|  
|-------------|------------------------|-------------------------|---------------------------|-----------------------------|  
|CRT\-Bibliothek|unterstützt|unterstützt||[Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC\/ATL|unterstützt|||[MFC\-Desktopanwendungen](../mfc/mfc-desktop-applications.md) &#124; [Class Overview](../atl/atl-class-overview.md)|  
|Nicht verwaltete Funktionen|unterstützt|||[Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)|  
|Nicht verwaltete Daten|unterstützt|unterstützt||[Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|Aufrufbar von nicht verwalteten Funktionen|unterstützt|||[Gewusst wie: Migrieren auf \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|Unterstützt das Aufrufen nicht verwalteter Funktionen|unterstützt|Nur Funktionen im C\-Format|Nur P\/Invoke|[Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|Unterstützt Reflektion|Nur DLLs|unterstützt|unterstützt|[Reflektion](../dotnet/reflection-cpp-cli.md)|  
  
## Siehe auch  
 [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)