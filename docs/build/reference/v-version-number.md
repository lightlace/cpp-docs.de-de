---
title: "/V (Versionsnummer) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/v"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/V (Compileroption) [C++]"
  - "Einbetten von Versionszeichenfolgen"
  - "V (Compileroption) [C++]"
  - "-V (Compileroption) [C++]"
  - "Versionsnummern, Angeben für .obj"
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /V (Versionsnummer)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bettet eine Textzeichenfolgein die OBJ\-Datei ein.  Veraltet.  
  
## Syntax  
  
```  
/Vstring  
```  
  
## Argumente  
 `string`  
 eine Zeichenfolge, die die Versionsnummer oder den Copyrightvermerk angibt, der in eine OBJ\-Datei eingebettet werden soll.  
  
## Hinweise  
 Die Zeichenfolgekann eine OBJ\-Datei mit einer Versionsnummer oder einem Copyrightvermerk versehen.  Leerzeichen und Tabulatoren, die Teil der Zeichenfolge sind, müssen in doppelte Anführungszeichen \("\) eingeschlossen werden.  Ein umgekehrter Schrägstrich \(\\\) muss allen doppelten Anführungszeichen vorangehen, die Teil der Zeichenfolge sind.  Ein Leerzeichen zwischen **\/V** und `string` ist optional.  
  
 Sie können auch [Kommentar](../../preprocessor/comment-c-cpp.md) mit dem compiler\-Kommentartypargument verwenden, um den Namen und die Versionsnummer des Compilers in der OBJ\-Datei abzulegen.  
  
 **\/V** ist veraltet. **\/V** wurde hauptsächlich verwendet, um die Erstellung virtueller Gerätetreiber \(VxDs\) zu unterstützen. Die Erstellung von VxDs wird vom [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]\-Toolset nicht länger unterstützt.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)