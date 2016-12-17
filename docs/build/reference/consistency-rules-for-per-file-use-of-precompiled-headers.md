---
title: "Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei"
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
  - ".pch-Dateien, Konsistenzregeln"
  - "PCH-Dateien, Konsistenzregeln"
  - "Vorkompilierte Headerdateien, Konsistenzregeln"
ms.assetid: afd49365-48bc-41f4-b700-fe8297b944a1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe der [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\-Compileroption können Sie festlegen, welche vorkompilierte Headerdatei \(PCH\) verwendet werden soll.  
  
 Bei Verwendung einer PCH geht der Compiler davon aus, dass dieselbe Kompilierungsumgebung, d. h., konsistente Compileroptionen, Pragmas usw., verwendet wird, die bei der Erstellung der PCH gültig war, es sei denn, Sie ändern diese Einstellungen.  Wenn der Compiler eine Inkonsistenz entdeckt, gibt er eine Warnung aus und kennzeichnet, wenn möglich, die Inkonsistenz.  Solche Warnungen weisen nicht notwendigerweise auf ein Problem mit der PCH hin; sie warnen lediglich vor möglichen Konflikten.  Die Konsistenzanforderungen für PCH\-Dateien werden in den folgenden Abschnitten erläutert.  
  
## Konsistenz von Compileroptionen  
 Die folgenden Compileroptionen können bei Verwendung einer PCH eine Inkonsistenzwarnung auslösen:  
  
-   Mit der Präprozessoroption \(**\/D**\) erstellte Makros müssen in der Kompilierung, durch die die PCH erstellt wurde, und in der aktuellen Kompilierung identisch sein.  Der Zustand definierter Konstanten wird nicht geprüft, ihre Änderung kann jedoch zu unvorhersehbaren Ergebnissen führen.  
  
-   PCHs können nicht zusammen mit den Optionen **\/E** und **\/EP** eingesetzt werden.  
  
-   PCHs müssen entweder mit der **\/FR**\-Option \(Browserinformationen erzeugen\) oder mit der **\\Fr**\-Option \(Lokale Variablen ausschließen\) erstellt werden, bevor Kompilierungen, die diese PCH verwenden, mit diesen Optionen durchgeführt werden können.  
  
## C 7.0\-kompatibel \(\/Z7\)  
 Wenn diese Option beim Erstellen der PCH\-Datei aktiviert ist, kann bei nachfolgenden Kompilierungen, die die PCH verwenden, auf die Debuginformationen zugegriffen werden.  
  
 Wenn die **\/Z7**\-Option \(C 7.0\-Kompatibel\) beim Erstellen der PCH nicht aktiviert ist, wird bei nachfolgenden Kompilierungen, die die PCH und diese Option verwenden, eine Warnung ausgelöst.  Die Debuginformationen werden in der aktuellen OBJ\-Datei abgelegt, und lokale Symbole, die in der PCH definiert sind, sind für den Debugger nicht verfügbar.  
  
## Includepfadkonsistenz  
 Eine PCH enthält keine Informationen über den bei der Erstellung gültigen Includepfad.  Wenn Sie eine PCH\-Datei einsetzen, verwendet der Compiler immer den bei der aktuellen Kompilierung angegebenen Includepfad.  
  
## Quelldateikonsistenz  
 Wenn Sie die **\/Yu**\-Option \(Vorkompilierte Headerdatei verwenden\) festlegen, ignoriert der Compiler alle Präprozessordirektiven \(einschließlich Pragmas\) im Quellcode, der vorkompiliert werden soll.  Die durch solche Präprozessordirektiven festgelegte Kompilierung muss mit der Kompilierung identisch sein, die für die **\/Yc**\-Option \(Vorkompilierte Headerdatei erstellen\) verwendet wird.  
  
## Pragmakonsistenz  
 Pragmas, die während der Erstellung einer PCH verarbeitet werden, wirken sich normalerweise auf die Datei aus, mit der die PCH später verwendet wird.  Die Pragmas **comment** und **message** haben keinen Einfluss auf den Rest der Kompilierung.  
  
 Die folgenden Pragmas werden als Teil einer PCH beibehalten und beeinflussen die verbleibende Kompilierung, in der die PCH verwendet wird.  
  
||||  
|-|-|-|  
|alloc\_text|include\_alias|pack|  
|auto\_inline|init\_seg|pointers\_to\_members|  
|check\_stack|inline\_depth|setlocale|  
|code\_seg|inline\_recursion|vtordisp|  
|data\_seg|intrinsic|warning|  
|function|optimize||  
  
## Siehe auch  
 [Konsistenzregeln für vorkompilierte Header](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)