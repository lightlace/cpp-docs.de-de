---
title: "C-Schl&#252;sselw&#246;rter"
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
  - "C"
helpviewer_keywords: 
  - "Schlüsselwörter [C]"
  - "Microsoft-spezifische Schlüsselwörter"
  - "Neudefinieren von Schlüsselwörtern"
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# C-Schl&#252;sselw&#246;rter
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"Schlüsselwörter" sind Wörter, die eine besondere Bedeutung für den C\-Compiler haben.  In den Übersetzungsphasen 7 und 8 kann ein Bezeichner nicht dieselbe Schreibweise und Groß\-\/Kleinschreibung haben wie ein C\-Schlüsselwort. \(Eine Beschreibung der [Übersetzungsphasen](../preprocessor/phases-of-translation.md) finden Sie in der *Präprozessorreferenz*. Informationen zu Bezeichnern finden Sie unter [Bezeichner](../c-language/c-identifiers.md).\) Die Programmiersprache C verwendet die folgenden Schlüsselwörter:  
  
|||||  
|-|-|-|-|  
|**auto**|**double**|`int`|`struct`|  
|**break**|**else**|**long**|`switch`|  
|**case**|`enum`|**register**|`typedef`|  
|`char`|`extern`|`return`|**union**|  
|**const**|**float**|**short**|`unsigned`|  
|**continue**|**for**|**signed**|`void`|  
|**default**|`goto`|`sizeof`|`volatile`|  
|**do**|**if**|**static**|`while`|  
  
 Sie können Schlüsselwörter nicht neu definieren.  Sie können jedoch, bevor Sie mit C [preprocessor directives](../preprocessor/preprocessor-directives.md) kompilieren, Ersatztext für Schlüsselwörter angeben.  
  
 **Microsoft\-spezifisch**  
  
 Der ANSI C\-Standard ermöglicht, dass Bezeichner mit zwei vorangestellten Unterstrichen für Compilerimplementierungen reserviert werden können.  Daher werden gemäß Microsoft\-Konvention Microsoft\-spezifischen Schlüsselwortnamen doppelte Unterstriche vorangestellt.  Diese Wörter können nicht als Bezeichnernamen verwendet werden.  Eine Beschreibung der ANSI\-Regeln für die Benennung von Bezeichnern, einschließlich der Verwendung von doppelten Unterstrichen, finden Sie unter [Bezeichner](../c-language/c-identifiers.md).  
  
 Die folgenden Schlüsselwörter und speziellen Bezeichner werden vom Microsoft C\-Compiler erkannt:  
  
|||||  
|-|-|-|-|  
|`__asm`|**dllimport**2|`__int8`|`naked`2|  
|`__based`1|`__except`|`__int16`|`__stdcall`|  
|`__cdecl`|`__fastcall`|`__int32`|**thread**2|  
|`__declspec`|`__finally`|`__int64`|`__try`|  
|`dllexport`2|`__inline`|`__leave`||  
  
 1.  Das `__based`\-Schlüsselwort weist eingeschränkte Verwendung für 32\-Bit\- und 64\-Bit\-Zielkompilierungen auf.  
  
 2.  Dies sind spezielle Bezeichner, wenn sie mit `__declspec` verwendet werden. Ihre Verwendung in anderen Kontexten ist nicht eingeschränkt.  
  
 Standardmäßig sind Microsoft\-Erweiterungen aktiviert.  Um sicherzustellen, dass die Programme vollständig übertragbar sind, können Sie Microsoft\-Erweiterungen durch Angeben der Option "\/Za" \(Kompilieren für ANSI\-Kompatibilität\) während der Kompilierung deaktivieren.  Dabei werden Microsoft\-spezifische Schlüsselwörter deaktiviert.  
  
 Wenn Microsoft\-Erweiterungen aktiviert sind, können Sie in den Programmen die oben aufgeführten Schlüsselwörter verwenden.  Bei Einhaltung der ANSI\-Kompatibilität werden den meisten dieser Schlüsselwörter ein doppelten Unterstrich vorangestellt.  Die vier Ausnahmen `dllexport`, **dllimport**, `naked` und **thread** werden nur mit `__declspec` verwendet und erfordern deshalb keinen vorangestellten doppelten Unterstrich.  Für die Abwärtskompatibilität werden die restlichen Schlüsselwörter mit Versionen mit einem Unterstrich unterstützt.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Elemente von C](../c-language/elements-of-c.md)