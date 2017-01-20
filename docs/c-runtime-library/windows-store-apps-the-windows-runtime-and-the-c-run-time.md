---
title: "Windows Store-Apps, die Windows-Runtime und die C-Laufzeit"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Windows Store-Apps, die Windows-Runtime und die C-Laufzeit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps sind in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ausgeführte Programme, die auf [!INCLUDE[win8](../build/includes/win8_md.md)] ausgeführt werden.  Bei [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] handelt es sich um eine vertrauenswürdige Umgebung, die die Funktionen, Variablen und Ressourcen steuert, die für eine [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App verfügbar sind.  Standardmäßig verhindern [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Einschränkungen jedoch die Verwendung der meisten C Run\-Time\-Bibliotheksfeatures \(CRT\) in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps.  
  
 Die folgenden CRT\-Features werden durch [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] nicht unterstützt:  
  
-   Die meisten CRT\-Funktionen, die mit nicht unterstützten Funktionen in Zusammenhang stehen.  
  
     Beispielsweise kann eine [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App mithilfe der `exec`\- und `spawn`\-Serie von Routinen keinen Prozess erstellen.  
  
     Wenn eine CRT\-Funktion in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App nicht unterstützt wird, findet sich diese Tatsache im entsprechenden Referenzartikel.  
  
-   Die meisten Zeichen\- und Mehrbytefunktionen.  
  
     Allerdings werden Unicode und ANSI\-Text unterstützt.  
  
-   Konsolen\-App\- und Befehlszeilenargumente.  
  
     Herkömmliche Desktop\-Apps unterstützen jedoch weiterhin Konsolen\- und Befehlszeilenargumente.  
  
-   Umgebungsvariablen.  
  
-   Das Konzept eines aktuellen Arbeitsverzeichnisses.  
  
-   [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps und DLL\-Dateien, die mit der CRT statisch verknüpft sind und mithilfe der [\/MT](../build/reference/md-mt-ld-use-run-time-library.md)\- oder `/MTd`\-Compileroptionen erstellt werden.  
  
     Also eine App, die eine statische Multithread\-Version der CRT verwendet.  
  
-   Eine mithilfe der Compileroption [\/MDd](../build/reference/md-mt-ld-use-run-time-library.md) erstellte App.  
  
     Also eine Debug\-, Multithread\- und DLL\-spezifische Version der CRT.  Eine solche Anwendung wird in [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] nicht unterstützt.  
  
 Eine vollständige Liste der CRT\-Funktionen, die in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App nicht verfügbar sind, und Vorschläge für alternative Funktionen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)   
 [CRT\-Funktionen, die nicht von Windows\-Runtime unterstützt werden](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)