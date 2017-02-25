---
title: "Konsistenzregeln f&#252;r &quot;/Yc&quot; und &quot;/Yu&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yc"
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yc (Compileroption) [C++]"
  - "/Yu (Compileroption) [C++]"
  - "Yc (Compileroption) [C++]"
  - "-Yc (Compileroption) [C++]"
  - "Yu (Compileroption) [C++]"
  - "-Yu (Compileroption) [C++]"
ms.assetid: 9dfb0e32-ec9b-4a36-9355-27a0e5fba512
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Konsistenzregeln f&#252;r &quot;/Yc&quot; und &quot;/Yu&quot;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einen mit **\/Yc** oder **\/Yu** erstellten vorkompilierten Header verwenden, vergleicht der Compiler die aktuelle Kompilierungsumgebung mit der, die beim Erstellen der PCH\-Datei vorhanden war.  Stellen Sie sicher, dass für die aktuelle Kompilierung eine mit der vorherigen Umgebung konsistente Umgebung \(mit identischen Compileroptionen, Pragmas usw.\) verwendet wird.  Wenn der Compiler eine Inkonsistenz entdeckt, gibt er eine Warnung aus und kennzeichnet, wenn möglich, die Inkonsistenz.  Solche Warnungen weisen nicht notwendigerweise auf ein Problem mit der PCH\-Datei hin; sie warnen lediglich vor möglichen Konflikten.  In den folgenden Abschnitten werden die Konsistenzanforderungen für vorkompilierte Header erläutert.  
  
## Konsistenz von Compileroptionen  
 In der folgenden Tabelle sind Compileroptionen aufgeführt, die bei Verwendung eines vorkompilierten Headers eine Inkonsistenzwarnung auslösen können.  
  
|Option|Name|Regel|  
|------------|----------|-----------|  
|\/D|Konstanten und Makros definieren|Müssen in der Kompilierung, in der der vorkompilierte Header erstellt wurde, und in der aktuellen Kompilierung übereinstimmen.  Der Zustand von definierten Konstanten wird nicht überprüft, es können jedoch unvorhersehbare Ergebnisse auftreten, wenn Dateien von Werten geänderter Konstanten abhängig sind.|  
|**\/E oder \/EP**|Präprozessorausgabe in Standardausgabe kopieren|Vorkompilierte Header können nicht mit den Optionen **\/E** oder **\/EP** verwendet werden.|  
|**\/Fr oder \/FR**|Informationen für Microsoft\-Quellcodebrowser generieren|Damit die Optionen **\/Fr** und **\/FR** in Verbindung mit der **\/Yu**\-Option gültig sind, müssen sie bereits beim Erstellen des vorkompilierten Headers aktiviert gewesen sein.  Nachfolgende Kompilierungen, in denen der vorkompilierte Header verwendet wird, generieren ebenfalls Quellcode\-Browserinformationen.  Diese werden in einer einzelnen SBR\-Datei gespeichert und von anderen Dateien in derselben Weise referenziert wie Informationen in der Codeansicht.  Die Speicherung von Quellcode\-Browserinformationen kann nicht überschrieben werden.|  
|**\/GA**, **\/GD**, **\/GE**, **\/Gwoder\/GW**|Windows\-Protokolloptionen|Müssen in der Kompilierung, in der der vorkompilierte Header erstellt wurde, und in der aktuellen Kompilierung übereinstimmen.  Wenn diese Optionen sich unterscheiden, wird eine Warnmeldung ausgegeben.|  
|\/Zi|Vollständige Debuginformationen erzeugen|Wenn diese Option beim Erstellen des vorkompilierten Headers aktiviert ist, können nachfolgende Kompilierungen, die die Vorkompilierung verwenden, auf die Debuginformationen zugreifen.  Wenn **\/Zi** beim Erstellen des vorkompilierten Headers nicht aktiviert ist, wird bei nachfolgenden Kompilierungen, die die Vorkompilierung sowie **\/Zi** verwenden, eine Warnung ausgelöst.  Die Debuginformationen werden in der aktuellen Objektdatei gespeichert, und in dem vorkompilierten Header definierte lokale Symbole stehen dem Debugger nicht zur Verfügung.|  
  
> [!NOTE]
>  Die Funktion für vorkompilierte Header ist nur für die Verwendung einer Datei in Verbindung mit C\- und C\+\+\-Quelldateien geeignet.  
  
## Includepfadkonsistenz  
 Ein mit der **\/Yc**\-Option erstellter vorkompilierter Header enthält keine Informationen über den Includepfad, der beim Erstellen der PCH\-Datei gültig war.  Wenn Sie eine PCH\-Datei einsetzen, verwendet der Compiler immer den bei der aktuellen Kompilierung angegebenen Includepfad.  
  
## Quelldateikonsistenz  
 Bei Verwendung eines vorkompilierten Headers ignoriert der Compiler alle Präprozessordirektiven \(einschließlich Pragmas\), die vor dem hdrstop\-Pragma angezeigt werden.  Die durch diese Präprozessordirektiven festgelegte Kompilierung muss mit der Kompilierung identisch sein, die beim Erstellen der vorkompilierten Headerdatei verwendet wurde.  
  
## Pragmakonsistenz  
 Pragmas, die während der Kompilierung eines vorkompilierten Headers verarbeitet werden, wirken sich gewöhnlich auf die Datei aus, in der der vorkompilierte Header später verwendet wird.  Die folgenden Pragmas haben lediglich Einfluss auf den Code innerhalb der PCH\-Datei, jedoch nicht auf den Code, der die PCH\-Datei später verwendet:  
  
||||  
|-|-|-|  
|Kommentar|page|subtitle|  
|Linesize|pagesize|Titel|  
|Meldung|skip||  
  
 Die folgenden Pragmas werden als Teil eines vorkompilierten Headers beibehalten und beeinflussen die verbleibende Kompilierung, in der der vorkompilierte Header verwendet wird.  
  
||||  
|-|-|-|  
|alloc\_text|function|optimize|  
|auto\_inline|inline\_depth|Pack|  
|check\_pointer|inline\_recursion|same\_seg|  
|check\_stack|intrinsic|warning|  
|code\_seg|loop\_opt||  
|data\_seg|native\_caller||  
  
## Siehe auch  
 [Konsistenzregeln für vorkompilierte Header](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md)   
 [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md)