---
title: "Komponente"
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
  - "vc-pragma.component"
  - "component_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "component-Pragma"
  - "Pragmas, Komponente"
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Komponente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuert das Sammeln von Browserinformationen oder Abhängigkeitsinformationen aus Quelldateien.  
  
## Syntax  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## Hinweise  
  
## Browser  
 Sie können das Sammeln aktivieren oder deaktivieren, und Sie können angeben, dass bestimmte Namen beim Sammeln von Informationen ignoriert werden.  
  
 Die Aktivierung oder Deaktivierung steuert das Sammeln von Browserinformationen ab dem nächsten Pragma.  Beispiel:  
  
```  
#pragma component(browser, off)  
```  
  
 Dieser Code stoppt das Sammeln von Browserinformationen durch den Compiler.  
  
> [!NOTE]
>  Um das Sammeln von Browserinformationen mit diesem Pragma zu aktivieren, [müssen zuerst die Browserinformationen aktiviert werden](../build/reference/building-browse-information-files-overview.md).  
  
 Die **references**\-Option kann mit oder ohne das *name*\-Argument verwendet werden.  Mit **references** ohne *name* wird das Sammeln von Verweisen aktiviert oder deaktiviert \(andere Browserinformationen werden allerdings weiterhin gesammelt\).  Beispiel:  
  
```  
#pragma component(browser, off, references)  
```  
  
 Dieser Code stoppt das Sammeln von Verweisinformationen durch den Compiler.  
  
 Verwenden Sie **references** mit *name* und **off** , um zu verhindern, dass Verweise auf *name* im Fenster zum Durchsuchen von Informationen angezeigt werden.  Verwenden Sie die folgende Syntax, um Namen und Typen zu ignorieren, die für Sie nicht relevant sind, und die Größe von Browserinformationsdateien zu reduzieren.  Beispiel:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 ignoriert Verweise auf **DWORD** ab diesem Punkt.  Sie können das Sammeln von Verweisen auf `DWORD` wieder aktivieren, indem Sie **on** verwenden:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 Dies ist die einzige Möglichkeit, das Sammeln von Verweisen auf *name* erneut aufzunehmen. Sie müssen alle *name*\-Argumente, die Sie deaktiviert haben, explizit aktivieren.  
  
 Um zu verhindern, dass der Präprozessor *name* erweitert \(beispielsweise bei der Erweiterung von **NULL** auf **0**\), umgeben Sie "name" mit Anführungszeichen:  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## Minimale Neuerstellung  
 Die minimale Wiederaufbaufunktion in Visual C\+\+ erfordert, dass der Compiler C\+\+\-Klassenabhängigkeitsinformationen erstellt und speichert, wofür Speicherplatz benötigt wird.  Um Speicherplatz zu sparen, können Sie immer dann `#pragma component( minrebuild, off )` verwenden, wenn es nicht erforderlich ist, Abhängigkeitsinformationen z. B. in unveränderlichen Headerdateien zu sammeln.  Fügen Sie `#pragma component(minrebuild, on)` nach der unveränderlichen Klasse hinzu, um das Sammeln von Abhängigkeiten erneut zu aktivieren.  
  
## Reduzieren von Typinformationen  
 Die **mintypeinfo**\-Option reduziert die Debuginformationen für den angegebenen Bereich.  Diese Informationen haben einen beträchtlichen Umfang und wirken sich auf PDB\- und OBJ\-Dateien aus.  Sie können Klassen und Strukturen im mintypeinfo\-Bereich nicht debuggen.  Die Verwendung der mintypeinfo\-Option kann hilfreich sein, um die folgende Warnung zu vermeiden:  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Weitere Informationen zur \/GM\-Compileroption finden Sie unter [Minimale Neuerstellung aktivieren](../build/reference/gm-enable-minimal-rebuild.md).  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)