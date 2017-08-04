---
title: Windows Store-Apps, die Windows-Runtime und die C Run-Time | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 0eb057f9d229c659f339f996d1ff38f65fd2e018
ms.openlocfilehash: fc0ed4b45e04357fae46fb1391d55d184440f12d
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Windows Store-Apps, die Windows-Runtime und die C-Laufzeit
[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-Apps sind in der Windows-Runtime ausgeführte Programme, die auf [!INCLUDE[win8](../build/reference/includes/win8_md.md)] ausgeführt werden.  Bei der Windows-Runtime handelt es sich um eine vertrauenswürdige Umgebung, die die Funktionen, Variablen und Ressourcen steuert, die für eine [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-App verfügbar sind. Standardmäßig verhindern Windows-Runtime-Einschränkungen jedoch die Verwendung der meisten CRT-Bibliotheksfunktionen (C Run-Time) in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-Apps.  
  
 Die folgenden CRT-Funktionen werden durch die Windows-Runtime nicht unterstützt:  
  
-   Die meisten CRT-Funktionen, die mit nicht unterstützten Funktionen in Zusammenhang stehen.  
  
     Beispielsweise kann eine [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-App mithilfe der `exec`- und `spawn`-Serie von Routinen keinen Prozess erstellen.  
  
     Wenn eine CRT-Funktion in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-App nicht unterstützt wird, findet sich diese Tatsache im entsprechenden Referenzartikel.  
  
-   Die meisten Zeichen- und Mehrbytefunktionen.  
  
     Allerdings werden Unicode und ANSI-Text unterstützt.  
  
-   Konsolen-App- und Befehlszeilenargumente.  
  
     Herkömmliche Desktop-Apps unterstützen jedoch weiterhin Konsolen- und Befehlszeilenargumente.  
  
-   Umgebungsvariablen.  
  
-   Das Konzept eines aktuellen Arbeitsverzeichnisses.  
  
-   [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-Apps und DLL-Dateien, die mit der CRT statisch verknüpft sind und mithilfe der [/MT](../build/reference/md-mt-ld-use-run-time-library.md)- oder `/MTd`-Compileroptionen erstellt werden.  
  
     Also eine App, die eine statische Multithread-Version der CRT verwendet.  
  
-   Eine mithilfe der Compileroption [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) erstellte App.  
  
     Also eine Debug-, Multithread- und DLL-spezifische Version der CRT. Eine solche Anwendung wird in [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] nicht unterstützt.  
  
 Eine vollständige Liste der CRT-Funktionen, die in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-App nicht verfügbar sind, und Vorschläge für alternative Funktionen finden Sie unter [Von /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="see-also"></a>Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)   
 [Von der Windows-Runtime nicht unterstützte CRT-Funktionen](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
