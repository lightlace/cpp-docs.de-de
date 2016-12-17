---
title: "/J (Standardm&#228;&#223;ig &quot;unsigned char&quot;)"
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
  - "VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned"
  - "VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned"
  - "/j"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/J (Compileroption) [C++]"
  - "char-Datentyp"
  - "Standardzeichentyp ist vorzeichenlos"
  - "Standardwerte, Zeichentyp"
  - "J (Compileroption) [C++]"
  - "-J (Compileroption) [C++]"
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# /J (Standardm&#228;&#223;ig &quot;unsigned char&quot;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert den Standard\- `char`\-Typ von `signed char` auf `unsigned char`, und der `char`\-Typ wird null\-erweitert, wenn ein `int` vom Typ erweitert wird.  
  
## Syntax  
  
```  
/J  
```  
  
## Hinweise  
 Wenn ein `char`\-Wert explizit als `signed` deklariert wird, hat die **\/J** \- Option nicht, und der Wert ist signaturerweitert, wenn ein `int` vom Typ erweitert wird.  
  
 Die Option **\/J** definiert `_CHAR_UNSIGNED`, das zusammen mit `#ifndef` in der Datei LIMITS.h verwendet wird, um den Bereich des Standardtyps `char` zu definieren.  
  
 Weder ANSI C noch C\+\+ erfordern eine spezifische Implementierung des Typs `char`.  Diese Option ist nützlich, wenn Sie mit Zeichendaten arbeiten, die schließlich in eine andere Sprache als Englisch übersetzt werden sollen.  
  
> [!NOTE]
>  Wenn Sie diese Compileroption mit ATL\/MFC verwenden, wird ein Fehler generiert werden.  Obwohl Sie diesen Fehler deaktivieren konnten, indem Sie `_ATL_ALLOW_CHAR_UNSIGNED` definiert haben, funktioniert diese Problemumgehung wird nicht unterstützt und nicht angezeigt.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für das Projekt und dann **Eigenschaften** aus.  
  
2.  Im Dialogfeld ent15ent im linken Bereich unter **Konfigurationseigenschaften**, erweitern Sie **C\/C\+\+** und wählen Sie dann **Befehlszeile** aus.  
  
3.  Geben Sie die **\/J**\-Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md)